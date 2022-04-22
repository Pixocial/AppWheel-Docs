---
sidebar_position: 8
title: Stripe支付
id: Query Stripe Orders
---

本文档将引导如何在AppWheel管理后台添加Stripe配置，以及实现Web/iOS/Android订单互通的使用。

## 配置Stripe应用资料

要支持Stripe支付，需要有自己的Stripe账号，同时需要填写相关信息到AppWheel中。

### 1.1 在Stripe后台获取密钥

![1-1](/img/stripePayments/1-1.png)

### 1.2 在AppWheel新建Stripe App
将从stripe后台获取的秘钥填写到aw中。

![1-2](/img/stripePayments/1-2.png)

### 1.3 Stripe通知配置

![1-3](/img/stripePayments/1-3.png)
复制 Webhook URL  在Stripe创建一个Webhook，然后将秘钥签名回填到AW，WebHook中。

![1-4](/img/stripePayments/1-4.png)

## Sku配置
### 2.1 在Stripe增加产品和价格
在Stripe增加一个产品价格，并复制价格代码

![2-1](/img/stripePayments/2-1.png)

### 2.2 在AppWheel增加Group 
Group 有两个作用：
- 用于控制那些Sku不能同时购买，如 年付产品 和 月付产品 ，不能同时购买，应该分配在同一个Group里。
- 控制不同SKU之间的升降级关系，如 白银会员 到 黄金会员，不能同时购买，同时也属于升级套餐的操作。

![2-2](/img/stripePayments/2-2.png)

### 2.3 在AppWheel增加Sku
要通过AppWheel完成购买，需要先添加Sku。
需要将在Stripe复制的价格填入到 Price ID 处，否则下一步购买订阅无法进行，如果多个SKU不允许同时购买，还需要配置Group。

![2-3](/img/stripePayments/2-3.png)

### 2.4 在AppWheel添加Entitlements
AW建议使用Entitlements来映射SKU和用户权益的关系，如 月付套餐 和 年付套餐 对应到同一个会员权益。
同时在同一个Entitlements下的APP，可以交叉查询订单，实现跨端购买的需要。

![2-4](/img/stripePayments/2-4.png)

## 订阅管理接口
订阅的购买需要通过接口实现，接口调用前请了解接口签名相关事项
签名规则 
Host:https://sdk-api.appwheel.com
### 3.1 创建订阅
作用：用户通过该接口创建订阅，并完成付款操作
path：/v1/purchase/create
method: Post
Body:

```json
{
    "appUserId":"{{appuserid}}",  //  必填，业务方自定义的订阅者ID
    "productId":"{{productId}}",  // 必填，2.3填写的SKU ID
    "successUrl":"{{SucessUrl}}", // 必填，购买成功后跳转回业务方的地址
    "cancelUrl":"{{CancelUrl}}", // 必填，取消购买跳转回业务方的地址
    "trialPeriodDays": 3  // 选填，免费天数
}
```

Response
```json
{
    "code": 0,
    "message": "success",
    "data": {
        "checkoutUrl": "https://checkout.stripe.com/pay/cs_test_b1w30tabJbJnX8GMOoZVvLef1ReZ1phM6N7aRceXwezIGKa8gKFOWTakhA#fidkdWxOYHwnPyd1blpxYHZxWjA0Tlc8XXBNYGFBT1Vwa01qQFNGdmA9TmlTTnU1SkZnNWJBfFZWX0tPQjBqalc0TU9yY0xMalZAfXFSbHJqX2REPEFBNGRBbkRKMGxXc2xjcUxiaHxKPUtmNTVRRkN%2FSnBmMCcpJ2N3amhWYHdzYHcnP3F3cGApJ2lkfGpwcVF8dWAnPydocGlxbFpscWBoJyknYGtkZ2lgVWlkZmBtamlhYHd2Jz9xd3BgeCUl" //付款页面
    }
}
```


### 3.2 用户订阅管理页面
作用：用户可以通过该页面取消和修改订阅套餐
path：/v1/purchase/customPortal
method：Post
Body:
```json
{
    "appUserId":"{{appuserid}}", // 订阅者ID
    "returnUrl":"{{returnRul}}" // 跳转回业务方页面
}
```


```json

Response:
{
    "code": 0,
    "message": "success",
    "data": {
        "sessionUrl": "https://billing.stripe.com/session/test_YWNjdF8xS1I5WHVIZWRESlB1bkhvLF9MTmVTZUVSaXhMVW1YZDEyU3ZZNktTT1Zyb2U1NzVy01005iaVqmkS"//管理页面
    }
}
```

### 3.3 获取当前订阅权益和订单
作用：获取用户购买的订单和对应的权益，如果在2.4配置了多个app在同一个权益下，可以跨APP返回订单。
path: /v1/subscriber/{{appuserid}}
Method: Get
Body: 无
Response:

```json
{
    "code": 0,
    "message": "success",
    "data": {
        "entitlement": { // 权益
            "abc": { // 权益标识
                "orderId": "2000000015808544", // 订单id
                "appId": 329386269, // appid
                "productId": "com.stripe.s", // 商品id
                "productType": 2, // 商品类别
                "isAutoRenew": true, // 是否自动续订
                "isTrialPeriod": false, // 试用期
                "platform": "ios", // 平台
                "purchaseDateMs": 1647960466000, // 购买时间
                "expiresDateMs": 1648964066000, // 过期时间
                "originalPurchaseDateMs": 1647942348000, // 首次购买时间
                "gracePeriodExpiresDateMs": 0, // 宽限期过期时间
                "status": 0 // 状态 订单状态：0 未付款 1 付款正常使用 2 取消 3 过期 4 宽限期 5 暂停',
            }
        },
        "subscriberOrders": [
            {
                "orderId": "2000000015808544",
                "appId": 329386269,
                "productId": "com.stripe.s",
                "productType": 2,
                "isAutoRenew": true,
                "isTrialPeriod": false,
                "platform": "ios",
                "purchaseDateMs": 1647960466000,
                "expiresDateMs": 1648964066000,
                "originalPurchaseDateMs": 1647942348000,
                "gracePeriodExpiresDateMs": 0,
                "status": 0
            }
        ]
    }
}
```

## 在SDK中获取订单
以下是通过SDK获取跨端支付订单的方法

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

<Tabs>
  <TabItem value="Java" label="Java" default>

```Java
        Market.getInstance().getStripePurchaseInfo(new StripeQueryOrderListener() {
            @Override
            public void onSuccess(StripePurchaseInfo info) {
              //拿到订单数据
              List<StripeOrderModel> list = info.subscriberOrders;
            }

            @Override
            public void onError(String msg) {

            }
        });
```
  </TabItem>
  <TabItem value="Kotlin" label="Kotlin">

```Kotlin

Market.getInstance().getStripePurchaseInfo(object :StripeQueryOrderListener{
            override fun onSuccess(info: StripePurchaseInfo?) {
            }

            override fun onError(msg: String?) {
            }
})

```
  </TabItem>
  <TabItem value="Objective-C" label="Objective-C">

```Objective-C 
    [AWPurchaseKit queryStripeOrdersWithCompletion:^(BOOL success, AWStripePurchaseInfo * _Nullable info, AWError * _Nullable error) {
        [self hideLoading];
        if (error) {
          //do something
            return;
        }
        if (info.orders && info.orders.count > 0) {
            //get orders
        }
    }];
```
  </TabItem>
  <TabItem value="Swift" label="Swift">

```Swift
AWPurchaseKit.queryStripeOrders { success, stripePurchaseInfo, error in
                
}
```
  </TabItem>
</Tabs>