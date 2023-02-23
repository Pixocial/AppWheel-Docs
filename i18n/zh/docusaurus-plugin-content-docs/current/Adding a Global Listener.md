---
sidebar_position: 8
title: 添加全局监听
id: Adding_a_Global_Listener
---

添加全局的监听，在发生购买、续期订阅、恢复购买之后全局监听都会被调用。开发者应该在初始化之后尽早的设置监听，以便及时的监听回调



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