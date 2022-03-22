# iOS

## Restore Purchase

### Description:
 This is used to restore valid subscriptions, non-consumable products, and non-renewable products for a user. When there is no valid subscription, the 'success' in the block will return a false value. Calling this interface will directly call the AppleService verification interface and there is a quota restriction for this interface for each app. <font color="red"> **It is strictly prohibited to call when starting the app and to call it too frequently. **</font> It is recommended to call it only when the purchase information fails to be inquired because the user changed their phone or reinstalled the app.

Objective-C:

```Objective-C 
[AWPurchaseKit restorePurchaseWithCompletion:^(BOOL success, 
                                            NSArray * validSubscriptions, 
                                            NSArray * purchasedItems, 
                                            AWError * error) {
    //do something
  }];
```

Swift:

```Swift
AWPurchaseKit.restorePurchase { (success, validSubscriptions, productIds, error) in
      //do something
      }
```