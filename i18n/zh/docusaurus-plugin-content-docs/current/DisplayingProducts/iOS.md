
调用该方法获取商品信息，应在展示商品页面前提前加载商品信息，完成商品的展示


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
              if let error = result.error {
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

### 参数：
`productSet`:sku的id的set集合
### 返回：
`RetrievedProducts`结构包含成功获取的商品`AWProduct`数组，获取失败的商品SKU数组，以及`AWError`对象

### 下一步

[购买](/MakingPurchases/iOS.md)