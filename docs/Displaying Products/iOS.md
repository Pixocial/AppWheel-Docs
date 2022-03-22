# iOS

## Get Products
### Description:
 This method is used to acquire product information. The product information should be loaded before displaying product page.

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
  
### Parameters:
 productIdentifiers: Collection of SKU IDs.
### Return:
 The RetrievedProducts returned includes AWProduct array of successfully obtained products, SKU array of products failed to be obtained and AWError objects.