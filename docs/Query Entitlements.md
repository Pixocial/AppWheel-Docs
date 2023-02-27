---
sidebar_position: 8
title: Query Entitlements
id: Query Entitlements
---

当有需要使用到跨端支付功能的时候，可以通过该接口来获取跨端支付的订单

 
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

<Tabs>
  <TabItem value="Java" label="Java" default>

```Java
        Market.getInstance().getEntitlementPurchaseInfo(new StripeQueryOrderListener() {
            @Override
            public void onSuccess(EntitlementPurchaseInfo info) {
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
      
      Market.getInstance().getEntitlementPurchaseInfo(object : StripeQueryOrderListener{
            override fun onSuccess(info: EntitlementPurchaseInfo?) {
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
    [AWPurchaseKit queryEntitlementOrdersWithCompletion:^(BOOL success, AWEntitlementPurchaseInfo * _Nullable info, AWError * _Nullable error) {
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
    AWPurchaseKit.queryEntitlementOrders { success, info, error in
                            //获取权益
                            info?.entitlement
                        }
```
  </TabItem>
</Tabs>