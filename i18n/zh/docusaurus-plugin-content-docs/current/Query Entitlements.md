---
sidebar_position: 8
title: 请求Stripe订单
id: Query Stripe Orders
---

当有需要使用到跨端支付功能的时候，可以通过该接口来获取跨端支付的订单

 
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

<Tabs>
  <TabItem value="Java" label="Java" default>

```Java
        Market.getInstance().getStripePurchaseInfo(new StripeQueryOrderListener() {
            @Override
            public void onSuccess(StripePurchaseInfo info) {
              //拿到权益
              List<StripeOrderModel> list = info.entitlement;
            }

            @Override
            public void onError(String msg) {

            }
        });
```
  </TabItem>
  <TabItem value="Kotlin" label="Kotlin">

```Kotlin
      
      Market.getInstance().getStripePurchaseInfo(object : StripeQueryOrderListener{
            override fun onSuccess(info: StripePurchaseInfo?) {
                //获取权益
                info?.entitlement
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
        //获取权益
        if (info.entitlement) {
        }
    }];
```
  </TabItem>
  <TabItem value="Swift" label="Swift">

```Swift
    AWPurchaseKit.queryStripeOrders { success, info, error in
                            //获取权益
                            info?.entitlement
                        }
```
  </TabItem>
</Tabs>