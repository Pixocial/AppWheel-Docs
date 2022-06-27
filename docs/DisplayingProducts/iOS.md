

 This method is used to acquire product information. The product information should be loaded before displaying product page.


import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

<Tabs>
  <TabItem value="Objective-C" label="Objective-C">

```Objective-C 
[AWPurchaseKit getProductsInfoWithProductIdentifiers:productSet
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
  </TabItem>
  <TabItem value="Swift" label="Swift">

```Swift
  AWPurchaseKit.getProductsInfo(withProductIdentifiers: productSet) { retrievedProducts in
              if let error = retrievedProducts.error {
                //request error,check error msg
                return
              }
                
              if retrievedProducts.validProducts.count > 0 {
                    let productList = retrievedProducts.validProducts
              }
              //request success, updateUI

  }
```
  </TabItem>
</Tabs>
  


### Parameters:

 productSet: Set of SKU IDs.
### Return:
 The RetrievedProducts returned includes AWProduct array of successfully obtained products, SKU array of products failed to be obtained and AWError objects.



### Next Steps

[Making Purchases](/MakingPurchases/iOS.md)