# iOS

## 获取商品
### 说明：
调用该方法获取商品信息，应在展示商品页面前提前加载商品信息，完成商品的展示

Objective-C:

```Objective-C
[AWPurchaseKit getProductsInfoWithProductIdentifiers:self.skuSet 
                                          completion:^(RetrievedProducts * _Nonnull retrievedProducts) {
      if (retrievedProducts.error) {
       // request error,check error msg
        return;
      }
      if (retrievedProducts.validProducts.count){
        dispatch_async(dispatch_get_main_queue(), ^{
        // request success, updateUI
        //  [self updateUI];
        });
      }
      if (retrievedProducts.invalidProductIdentifiers.count) {
        //find invalid sku, check your sku
      }
    }];
```

Swift:

```Swift
AWPurchaseKit.getProductsInfo(withProductIdentifiers: productIds) { [weak self] (result) in
          if let error = result.error {
            //request error,check error msg
          } else {
            let valid_products = result.validProducts
            //request success, updateUI
          }
  }
```

### 参数：
`productIdentifiers`:sku的id的set集合
### 返回：
`RetrievedProducts`结构包含成功获取的商品`AWProduct`数组，获取失败的商品SKU数组，以及`AWError`对象
`AWProduct`数据结构：[AppWheel SDK接入文档 - iOS 类的介绍]()
