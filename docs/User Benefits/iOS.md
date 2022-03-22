# iOS

## View User Benefits
 The following method is used to check a user's existing purchased products.
### Obtain the current valid orders
#### Description:
 The following method is used to check a user's existing valid orders, including valid subscription and unconsumed INAPP products.

```java
UserOrderManager.getProvider().getOrders()
```

```kotlin
UserOrderManager.getProvider().getOrders()
```

### Obtain current subscription
#### Description:
 This method is used to obtain a user's existing valid subscription. If there is no valid subscription, an empty result will be returned.

```java
SubsPurchase recentSubsPurchase = UserOrderManager.getProvider().getRecentSubsPurchase();
```

```kotlin
val recentSubsPurchase = UserOrderManager.getProvider().recentSubsPurchase