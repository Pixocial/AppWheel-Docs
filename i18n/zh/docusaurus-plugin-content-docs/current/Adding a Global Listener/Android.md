# Android

## 添加全局监听
### 说明：
添加全局的监听，在发生购买、续期订阅、恢复购买之后全局监听都会被调用。开发者应该在初始化之后尽早的设置监听，以便及时的监听回调

java:

```java
/// 添加监听
UserOrderManager.getProvider().addPurchaseObserver(new OrderObserver() {
    @Override
    public void onUpdateOrders(List<MTGPurchase> purchases) {
        // 在这里监听订单变化情况
    }
});
///移除监听
UserOrderManager.getProvider().removePurchaseObserver(orderObserver);
```

kotlin:

```kotlin
/// 添加监听
UserOrderManager.getProvider().addPurchaseObserver {
    // 客户端在这里监听中台的订单变化情况
} 
///移除监听
UserOrderManager.getProvider().removePurchaseObserver(orderObserver)
```
