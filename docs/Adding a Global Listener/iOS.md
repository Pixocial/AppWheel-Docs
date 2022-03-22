# iOS

## Adding a global listener

### Description:
 This method is used to add a global listener, which will be called after purchase, subscription renewal, and/or restoring purchases. Developers should set up listeners as soon as possible after initialization for callbacks in a timely manner.

```Objective-C 
///Adding a listener
[AWPurchaseKit addPurchaseObserver:AWPurchaseObserver];
///Remove listener
[AWPurchaseKit removePurchaseObserver:self]
```

```Swift
///Adding a listener
AWPurchaseKit.add(AWPurchaseObserver)
///Remove listener
AWPurchaseKit.remove(AWPurchaseObserver)
```