# iOS

## 添加全局监听
### 说明：
添加全局的监听，在发生购买、续期订阅、恢复购买之后全局监听都会被调用。开发者应该在初始化之后尽早的设置监听，以便及时的监听回调

Objective-C:

```Objective-C
///添加监听
[AWPurchaseKit addPurchaseObserver:AWPurchaseObserver];
///移除监听
[AWPurchaseKit removePurchaseObserver:self]
```

Swift:

```Swift
/// 添加监听
AWPurchaseKit.add(AWPurchaseObserver)
///移除监听
AWPurchaseKit.remove(AWPurchaseObserver)
```
