import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';
# iOS

## Adding a global listener
### Description:
 This method is used to add a global listener, which will be called after purchase, subscription renewal, and/or restoring purchases. Developers should set up listeners as soon as possible after initialization for callbacks in a timely manner.

<Tabs>
  <TabItem value="apple" label="java" default>
  
```java
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
  <TabItem value="orange" label="kotlin">
  
```kotlin
///Adding a listener
UserOrderManager.getProvider().addPurchaseObserver {
    //Monitoring order changes
} 
///Remove listener
UserOrderManager.getProvider().removePurchaseObserver(orderObserver)
```
  </TabItem>
  <TabItem value="banana" label="Objective-C">
  
```Objective-C 
///Adding a listener
[AWPurchaseKit addPurchaseObserver:AWPurchaseObserver];
///Remove listener
[AWPurchaseKit removePurchaseObserver:self]
```
  </TabItem>
  
  <TabItem value="banana" label="Swift">
  
```Swift
///Adding a listener
AWPurchaseKit.add(AWPurchaseObserver)
///Remove listener
AWPurchaseKit.remove(AWPurchaseObserver)
```
  </TabItem>
</Tabs>



