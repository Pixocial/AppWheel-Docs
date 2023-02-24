---
sidebar_position: 7
title: 跨平台和App共享订阅指引
id: sharing_subscriptions
---

同一AppWheel项目中的应用程序共享相同的登录用户ID命名空间，这意味着它们也共享订阅。在同一项目的不同应用程序中登录同一用户ID的用户将有权访问相同的权利。这允许在不同应用程序之间共享订阅状态，甚至在不同平台上也是如此。

**请注意，匿名应用用户ID无法跨应用和平台共享订阅状态，因此您需要通过自己的身份验证系统使用自定义应用用户ID进行标识。**

# 前置条件

要在应用实现跨平台和App共享订阅，需要您先了解以下内容

- [项目和应用](/Projects)
- [权益和产品配置](/ConfiguringProduct/entitlements)
- [用户身份识别](/UserBenefits/user-ids)
- [购买](/MakingPurchases/stripe)
- [权益查询](/UserBenefits/api)

需要明确的是，应用商店或者支付平台间的壁垒是存在的，商品是不能跨支付平台购买的，比如在Google应用商店添加的商品，不可能用苹果应用商店账号支付；同理苹果应用商店的服务也不能通过Stripe购买。

AppWheel支持的跨平台和App共享订阅，其本质是通过识别用户身份，将同一用户在不同App中的订阅状态查询并展示的过程，在熟悉前置条件中列举的内容和明确共享的实现方式后，按照以下步骤既可以实现订阅共享：

- 1.在同一个项目下创建至少两个需要共享订阅的app，

- 2.商品添加到AppWheel，并配置到同一个Entitlements中

- 3.安装SDK，并用相同的用户ID初始化SDK

- 4.购买订阅

- 5.在另一个APP查询权益

以下是通过SDK获取跨端支付订单的方法

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

<Tabs>
  <TabItem value="Java" label="Java" default>

```Java
        Market.getInstance().getStripePurchaseInfo(new StripeQueryOrderListener(){
@Override
public void onSuccess(StripePurchaseInfo info){
        //拿到订单数据
        List<StripeOrderModel> list=info.subscriberOrders;
        }

@Override
public void onError(String msg){

        }
        });
```

  </TabItem>
  <TabItem value="Kotlin" label="Kotlin">

```Kotlin

Market.getInstance().getStripePurchaseInfo(object : StripeQueryOrderListener {
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

 <TabItem value="javascript" label="javascript">

```javascript
const appwheel = new AppWheel({AppID}, {platfrom}, {AppSecret})
appwheel.entitlement(this.appuserid).then(res => res.json()).then((json) => {
    console.log("当前有效权益", Object.keys(json.data.entitlement))
    console.log("当前已失效权益", Object.keys(json.data.invalidEntitlement))
})

```

</TabItem>
</Tabs>