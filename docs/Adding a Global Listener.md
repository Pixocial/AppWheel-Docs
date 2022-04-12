---
sidebar_position: 7
title: Adding a Global Listener
id: Adding_a_Global_Listener
---


This method is used to add a global listener, which will be called after purchase, subscription renewal, and/or restoring purchases. Developers should set up listeners as soon as possible after initialization for callbacks in a timely manner.



import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

<Tabs>
  <TabItem value="Java" label="Java" default>

```Java
///Adding a listener
UserOrderManager.getProvider().addPurchaseObserver(new OrderObserver() {
    @Override
    public void onUpdateOrders(List<MTGPurchase> purchases) {
        // Monitor order changes
    }
});
///Remove listener
UserOrderManager.getProvider().removePurchaseObserver(orderObserver);
```
  </TabItem>
  <TabItem value="Kotlin" label="Kotlin">

```Kotlin
///Adding a listener
UserOrderManager.getProvider().addPurchaseObserver {
    //Monitoring order changes
} 
///Remove listener
UserOrderManager.getProvider().removePurchaseObserver(orderObserver)
```
  </TabItem>
  <TabItem value="Objective-C" label="Objective-C">

```Objective-C 
///Adding a listener
[AWPurchaseKit addPurchaseObserver:AWPurchaseObserver];
///Remove listener
[AWPurchaseKit removePurchaseObserver:self];
```
  </TabItem>
  <TabItem value="Swift" label="Swift">

```Swift
///Adding a listener
AWPurchaseKit.add(AWPurchaseObserver)
///Remove listener
AWPurchaseKit.remove(AWPurchaseObserver)
```
  </TabItem>
</Tabs>