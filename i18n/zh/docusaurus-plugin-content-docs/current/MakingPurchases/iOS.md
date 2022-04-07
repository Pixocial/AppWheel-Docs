
用户选择商品后，调用该方法完成在appStore的购买，需要注意开发者应该在调用该方法前判断商品类型，然后传入该方法的`productType`参数中完成购买。

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

<Tabs>
  <TabItem value="Objective-C" label="Objective-C">

```Objective-C 
[AWPurchaseKit purchaseProduct:product 
                      quantity:quantity 
                   AWProducts 
               paymentDiscount:paymentDiscount completion:^(BOOL success, AWError * _Nonnull error) {
                if (!success) {
                  //purchase failed, check error
                }else {
                  //purchase success
                }
          }];
```
  </TabItem>
  <TabItem value="Swift" label="Swift">

```Swift
AWPurchaseKit.purchaseProduct(product, 
                     quantity: 1, 
                  productType: AWProductType, 
              paymentDiscount: nil) { success, error in
        if success {
          //purchase success
        } else {
          //purchase failed, check error
        }
      }
```
  </TabItem>
</Tabs>

### 参数：
*  `product:` 商品
* `paymentDiscount`：折扣，只有订阅商品有,通过Product.discounts获取，没有可传nil
*  `quantity`: 购买数量，订阅商品的数量是1，其他类型的商品通常也都是1
*  `productType`:商品类型：用户自己根据sku来判断类型，类型有四种：(0:消耗型商品   、1:非消耗型商品  、2:自动续期订阅 、3:非自动学期订阅)


### 下一步

[恢复购买](/Restoring_Purchases)