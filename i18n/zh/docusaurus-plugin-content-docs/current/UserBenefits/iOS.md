# iOS

## 查看用户权益
### 判断是否处于订阅中
#### 说明：
判断用户是否处于订阅中，当用户有了有效订阅后，开发者可以调用该方法来判断用户的权益

Objective-C:

```Objective-C
[[AWPurchaseKit getPurchaseInfo] isSubscriptionUnlockedUser]
```

Swift:

```Swift
AWPurchaseKit.getPurchaseInfo().isSubscriptionUnlockedUser()
```

### 获取当前有效的订阅
#### 说明：
获取用户当前有效的订阅，开发者可以用该方法判断用户当前拥有的有效订阅

Objective-C:

```Objective-C
[[AWPurchaseKit getPurchaseInfo] getCurrentValidSubscriptions]
```

Swift:

```Swift
AWPurchaseKit.getPurchaseInfo().getCurrentValidSubscriptions()
```

### 获取当前拥有的非消耗性商品、非续期订阅商品
#### 说明：
获取用户当前拥有的消耗型、非消耗型、非续期订阅商品

Objective-C:

```Objective-C
[[AWPurchaseKit getPurchaseInfo] purchasedArray]
```

Swift:

```Swift
AWPurchaseKit.getPurchaseInfo().purchasedArray()
```
