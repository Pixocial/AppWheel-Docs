

 The following method is used to check a user's existing purchased products.

### Telling if there is an ongoing subscription service
#### Description:
 Tell if a user has an ongoing subscription service. If yes, this method can be used to tell the benefits the user enjoys.


import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

<Tabs>
  <TabItem value="Objective-C" label="Objective-C">

```Objective-C 
[[AWPurchaseKit getPurchaseInfo] isSubscriptionUnlockedUser]
```
  </TabItem>
  <TabItem value="Swift" label="Swift">

```Swift
AWPurchaseKit.getPurchaseInfo().isSubscriptionUnlockedUser()
```
  </TabItem>
</Tabs>

### Obtain the existing valid subscriptions
#### Description:
 It is used to tell a user's existing valid subscription.


<Tabs>
  <TabItem value="Objective-C" label="Objective-C">

```Objective-C 
[[AWPurchaseKit getPurchaseInfo] getCurrentValidSubscriptions]
```
  </TabItem>
  <TabItem value="Swift" label="Swift">

```Swift
AWPurchaseKit.getPurchaseInfo().getCurrentValidSubscriptions()
```
  </TabItem>
</Tabs>

### Obtain the currently owned non-consumable and non-renewable subscription products.
#### Description:
 It is used to obtain the consumable, non-consumable, and non-renewable subscription items currently owned by the user.


<Tabs>
  <TabItem value="Objective-C" label="Objective-C">

```Objective-C 
[[AWPurchaseKit getPurchaseInfo] purchasedArray]
```
  </TabItem>
  <TabItem value="Swift" label="Swift">

```Swift
AWPurchaseKit.getPurchaseInfo().purchasedArray()
```
  </TabItem>
</Tabs>

### Next Steps

[Adding a Global Listener](/Adding_a_Global_Listener)