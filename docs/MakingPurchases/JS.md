---
sidebar_position: 3
title: JS
id: JS
---

用户选择商品后，可以开始购买流程，接入方需要准备好回调地址，在用户付款成功后会回调到`successUrl`或者`cancelUrl`，接收到该回调后可以展示支付成功、跳转回订阅前的Web页面或者打开客户端程序。

![购买历程图](/img/stripePayments/sub_buy.jpg)

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

## 创建订阅
用户通过该接口创建订阅，并完成付款操作。

<Tabs>
 <TabItem value="javascript" label="javascript">

```javascript
// See your keys here: https://dashboard.appwheel.com/projects/ and select app
const appwheel = new AppWheel({AppID}, {platfrom}, {AppSecret})
appwheel.createPurchase({
    "appUserId": {appuserid},
    "productId": {productId},
    "successUrl": {successUrl},
    "cancelUrl": {cancelUrl}
}).then(res => res.json()).then(json => window.open(json.data.checkoutUrl))
```

  </TabItem>
</Tabs>

### 参数

| 字段 | 类型 | 必须 | 说明 |
|----------------|-------------|--|-------------------------------|
| appUserId | string | 是 | 用户唯一标识，如果使用[Athena](https://docs.pixocial.io/athena/docs/intro)登录，建议传入openid |
| productId | string | 是 | 从获取商品接口获取到的productId |
| successUrl | string | 是 | 支付成功后的回调地址 |
| cancelUrl | string | 是 | 取消支付的回调地址 |
| trialPeriodDays | int | 否 | 免费试用天数 |
|promotionCode| array &lt;string&gt; | 否 |优惠码，选填，目前只支持一个优惠码|

### 返回

```json lines
{
    "code": 0,
    "message": "success",
    "data": {
        "checkoutUrl": "https://checkout.stripe.com/pay/cs_test_b1w30tabJbJnX8GMOoZVvLef1ReZ1phM6N7aRceXwezIGKa8gKFOWTakhA#fidkdWxOYHwnPyd1blpxYHZxWjA0Tlc8XXBNYGFBT1Vwa01qQFNGdmA9TmlTTnU1SkZnNWJBfFZWX0tPQjBqalc0TU9yY0xMalZAfXFSbHJqX2REPEFBNGRBbkRKMGxXc2xjcUxiaHxKPUtmNTVRRkN%2FSnBmMCcpJ2N3amhWYHdzYHcnP3F3cGApJ2lkfGpwcVF8dWAnPydocGlxbFpscWBoJyknYGtkZ2lgVWlkZmBtamlhYHd2Jz9xd3BgeCUl"， //付款页面
        "awTransId":""//aw 本身的交易id
    }
}
```


## 一次性购买-Stripe配置商品
stripe配置好一次性付款商品，通过该接口发起购买

<Tabs>
 <TabItem value="javascript" label="javascript">

```javascript
// See your keys here: https://dashboard.appwheel.com/projects/ and select app
const appwheel = new AppWheel({AppID}, {platfrom}, {AppSecret})
appwheel.createPurchase({
    "appUserId": {appuserid},
    "productId": {productId},
    "successUrl": {successUrl},
    "cancelUrl": {cancelUrl},
    "mode": "sku_payment", //  必填
    "quantity": 1, // 购买数量
}).then(res => res.json()).then(json => window.open(json.data.checkoutUrl))
```

  </TabItem>
</Tabs>

### 参数

| 字段 | 类型 | 必须 | 说明 |
|----------------|-------------|--|-------------------------------|
| appUserId | string | 是 | 用户唯一标识，如果使用[Athena](https://docs.pixocial.io/athena/docs/intro)登录，建议传入openid |
| productId | string | 是 | 从获取商品接口获取到的productId |
| successUrl | string | 是 | 支付成功后的回调地址 |
| cancelUrl | string | 是 | 取消支付的回调地址 |
| mode | string | 是 | sku_payment  |
|quantity| int | 是 |购买数量|

### 返回

```json lines
{
    "code": 0,
    "message": "success",
    "data": {
        "checkoutUrl": "https://checkout.stripe.com/pay/cs_test_b1w30tabJbJnX8GMOoZVvLef1ReZ1phM6N7aRceXwezIGKa8gKFOWTakhA#fidkdWxOYHwnPyd1blpxYHZxWjA0Tlc8XXBNYGFBT1Vwa01qQFNGdmA9TmlTTnU1SkZnNWJBfFZWX0tPQjBqalc0TU9yY0xMalZAfXFSbHJqX2REPEFBNGRBbkRKMGxXc2xjcUxiaHxKPUtmNTVRRkN%2FSnBmMCcpJ2N3amhWYHdzYHcnP3F3cGApJ2lkfGpwcVF8dWAnPydocGlxbFpscWBoJyknYGtkZ2lgVWlkZmBtamlhYHd2Jz9xd3BgeCUl"， //付款页面
        "awTransId":""//aw 本身的交易id
    }
}
```

## 一次性购买-自定义价格

无需在stripe配置价格，自定义商品信息（价格、名称），直接创建一次性付款

<Tabs>
<TabItem value="javascript" label="javascript">

```javascript
// See your keys here: https://dashboard.appwheel.com/projects/ and select app
const appwheel = new AppWheel({AppID}, {platfrom}, {AppSecret})
appwheel.createPurchase({
    "appUserId": {appuserid},
    "productId": {productId},
    "successUrl": {successUrl},
    "cancelUrl": {cancelUrl},
    "mode": "payment", //  必填
    "quantity": 1, // 购买数量
    "payPrice": 1000,
    "productName": "test",
    "currency": "usd"
}).then(res => res.json()).then(json => window.open(json.data.checkoutUrl))
```

  </TabItem>
</Tabs>

### 参数

| 字段 | 类型 | 必须 | 说明 |
|----------------|-------------|--|-------------------------------|
| appUserId | string | 是 | 用户唯一标识，如果使用[Athena](https://docs.pixocial.io/athena/docs/intro)登录，建议传入openid |
| productId | string | 是 | 从获取商品接口获取到的productId |
| successUrl | string | 是 | 支付成功后的回调地址 |
| cancelUrl | string | 是 | 取消支付的回调地址 |
| mode | string | 是 | payment  |
|quantity| int | 是 |购买数量|
|payPrice| int | 是 |直接付款的价格，单位是 分|
|productName| stripe | 是 |付款页面显示的商品名称|

### 返回

```json lines
{
    "code": 0,
    "message": "success",
    "data": {
        "checkoutUrl": "https://checkout.stripe.com/pay/cs_test_b1w30tabJbJnX8GMOoZVvLef1ReZ1phM6N7aRceXwezIGKa8gKFOWTakhA#fidkdWxOYHwnPyd1blpxYHZxWjA0Tlc8XXBNYGFBT1Vwa01qQFNGdmA9TmlTTnU1SkZnNWJBfFZWX0tPQjBqalc0TU9yY0xMalZAfXFSbHJqX2REPEFBNGRBbkRKMGxXc2xjcUxiaHxKPUtmNTVRRkN%2FSnBmMCcpJ2N3amhWYHdzYHcnP3F3cGApJ2lkfGpwcVF8dWAnPydocGlxbFpscWBoJyknYGtkZ2lgVWlkZmBtamlhYHd2Jz9xd3BgeCUl"， //付款页面
        "awTransId":""//aw 本身的交易id
    }
}
```

更多Api接口[点击此处](/Installation/JS)

## 订单和权益查询

[订单和权益查询](/UserBenefits/js)