---
sidebar_position: 8
title: Query Stripe Orders
id: Query Stripe Orders
---


When cross-platform payment is needed, use this interface to query orders.

 
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

<Tabs>
  <TabItem value="Java" label="Java" default>

```Java
        Market.getInstance().getStripePurchaseInfo(new StripeQueryOrderListener() {
            @Override
            public void onSuccess(StripePurchaseInfo info) {
              //Get order information
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
              //Get order information
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