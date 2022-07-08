# iOS

## 查看用户权益
### 判断是否处于订阅中
#### 说明：
判断用户是否处于订阅中，当用户有了有效订阅后，开发者可以调用该方法来判断用户的权益

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

<Tabs>
  <TabItem value="Objective-C" label="Objective-C">

```Objective-C
[[AWPurchaseKit getPurchaseInfo] isSubscriptionUnlockedUser];
```

  </TabItem>
  <TabItem value="Swift" label="Swift">

```Swift
AWPurchaseKit.getPurchaseInfo().isSubscriptionUnlockedUser()
```
  </TabItem>
</Tabs>

### 获取当前最新的订阅
#### 说明：
获取当前最新的订阅，如果同时有多个订阅的话，会返回订阅到期时间最长的那个

<Tabs>
  <TabItem value="Objective-C" label="Objective-C">

```Objective-C
[[AWPurchaseKit getPurchaseInfo] getLatestSubscriptionInfo];
```

  </TabItem>
  <TabItem value="Swift" label="Swift">

```Swift
AWPurchaseKit.getPurchaseInfo().getLatestSubscriptionInfo()
```
  </TabItem>
</Tabs>

### 获取当前有效的订阅
#### 说明：
获取用户当前有效的订阅，开发者可以用该方法判断用户当前拥有的有效订阅


<Tabs>
  <TabItem value="Objective-C" label="Objective-C">

```Objective-C
[[AWPurchaseKit getPurchaseInfo] getCurrentValidSubscriptions];
```

  </TabItem>
  <TabItem value="Swift" label="Swift">


```Swift
AWPurchaseKit.getPurchaseInfo().getCurrentValidSubscriptions()
```
  </TabItem>
</Tabs>

### 获取当前拥有的非消耗性商品、非续期订阅商品
#### 说明：
获取用户当前拥有的消耗型、非消耗型、非续期订阅商品


<Tabs>
  <TabItem value="Objective-C" label="Objective-C">

```Objective-C
[[AWPurchaseKit getPurchaseInfo] purchasedArray];
```

  </TabItem>
  <TabItem value="Swift" label="Swift">


```Swift
AWPurchaseKit.getPurchaseInfo().purchasedArray()
```
  </TabItem>
</Tabs>

### 下一步

[添加全局监听](/Adding_a_Global_Listener)