---
sidebar_position: 7
title: 跨平台和App共享订阅指引
id: sharing_subscriptions
---

同一AppWheel项目中的应用程序共享相同的登录用户ID命名空间，这意味着它们也共享订阅。在同一项目的不同应用程序中登录同一用户ID的用户将有权访问相同的权利。这允许在不同应用程序之间共享订阅状态，甚至在不同平台上也是如此。

**请注意，匿名应用用户ID无法跨应用和平台共享订阅状态，因此您需要通过自己的身份验证系统使用自定义应用用户ID进行标识。**

# 前置条件

要在应用实现跨平台和App共享订阅，需要您先了解一下内容

- [项目和应用]("/Projects")
- [权益和产品配置]("/ConfiguringProduct/entitlements")
- [用户身份识别]("/UserBenefits/user-ids")
- [购买]("/MakingPurchases/stripe")

## 在SDK中获取订单

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
</Tabs>