# iOS

## 恢复购买
### 说明：
恢复用户的有效订阅、非消耗型、非续期订阅商品，当无有效的时候block中的success会返回false值。调该接口会直接调用AppleService校验接口，该接口在AppleService那边对于每个应用会有配额限制，<font color="red"> **因此严禁APP启动时候调用，严禁高频率调用**。</font>  建议只是在查询购买信息失败后（例如：用户换机、卸载重装）点击恢复购买按钮的时候调用。

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
