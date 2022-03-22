# Android

## 查看用户权益
通过以下的方法可以查看用户当前购买的商品来保证用户的权益
### 获取当前有效的订单
#### 说明：
获取用户当前有效的订单，开发者可以用该方法判断用户当前拥有的有效订单，仅限用户拥有的非过期的订阅和未被消耗的INAPP商品

java:

```java
UserOrderManager.getProvider().getOrders()
```

kotlin:

```kotlin
UserOrderManager.getProvider().getOrders()
```

### 获取当前的订阅
#### 说明：
通过该方法获取用户当前生效的订阅，如果用户没有有效订阅，会返回空

java:

```java
SubsPurchase recentSubsPurchase = UserOrderManager.getProvider().getRecentSubsPurchase();
```
kotlin:

```kotlin
val recentSubsPurchase = UserOrderManager.getProvider().recentSubsPurchase
```

