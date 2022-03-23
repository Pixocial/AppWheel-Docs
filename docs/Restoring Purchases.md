---
sidebar_position: 5
title: Restoring Purchases
id: Restoring Purchases
---

 This is used to restore valid subscriptions, non-consumable products, and non-renewable products for a user. When there is no valid subscription, the 'success' in the block will return a false value. Calling this interface will directly call the AppleService verification interface. There is a quota restriction for this interface for each app, <font color="red"> **so it is strictly prohibited to call when starting the app and to call it too frequently.**</font> It is recommended to call it only when the purchase information fails to be inquired because the user changed their phone or reinstalled the app.

 
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

<Tabs>
  <TabItem value="Java" label="Java" default>

```Java
Market.getInstance().restorePurchase(new OnRestorePurchaseListener() {
    @Override
    public void onSuccess(List<MTGPurchase> purchases) {
    }

    @Override
    public void onError(int resultCode) {
    }
});
```
  </TabItem>
  <TabItem value="Kotlin" label="Kotlin">

```Kotlin
Market.getInstance().restorePurchase(object : OnRestorePurchaseListener {
    override fun onSuccess(purchases: List<MTGPurchase>) {
    }
    override fun onError(resultCode: Int) {
    }
})
```
  </TabItem>
  <TabItem value="Objective-C" label="Objective-C">

```Objective-C 
[AWPurchaseKit restorePurchaseWithCompletion:^(BOOL success, 
                                            NSArray * validSubscriptions, 
                                            NSArray * purchasedItems, 
                                            AWError * error) {
    //do something
  }];
```
  </TabItem>
  <TabItem value="Swift" label="Swift">

```Swift
AWPurchaseKit.restorePurchase { (success, validSubscriptions, productIds, error) in
      //do something
      }
```
  </TabItem>
</Tabs>