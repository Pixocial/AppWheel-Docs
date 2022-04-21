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
</Tabs>