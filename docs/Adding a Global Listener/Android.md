# Android

## Adding a global listener
### Description:
 This method is used to add a global listener, which will be called after purchase, subscription renewal, and/or restoring purchases. Developers should set up listeners as soon as possible after initialization for callbacks in a timely manner.

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

```kotlin
///Adding a listener
UserOrderManager.getProvider().addPurchaseObserver {
    //Monitoring order changes
} 
///Remove listener
UserOrderManager.getProvider().removePurchaseObserver(orderObserver)
```
