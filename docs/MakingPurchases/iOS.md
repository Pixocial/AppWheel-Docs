

 This method should be called to complete a purchase when a user has selected a product. The developers should tell the product type before calling this method and then pass the productType to complete the purchase.


import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

<Tabs>
  <TabItem value="Objective-C" label="Objective-C">

```Objective-C 
[AWPurchaseKit purchaseProduct:product 
                      quantity:quantity 
                   productType:productType 
               paymentDiscount:paymentDiscount 
                    completion:^(BOOL success, AWError * _Nonnull error) {
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
AWPurchaseKit.purchaseProduct(product, quantity: quantity, productType: productType, paymentDiscount: nil) { success, error in

    if (!success) {
      //purchase failed, check error
      return
    }
    //purchase success  
}
```
  </TabItem>
</Tabs>

### Parameters:
- product: Products
- paymentDiscount: Discounts. Only for subscription products and can be acquired through Product.discounts. No transferable nil. 
- quantity: The quantity of purchases. The quantity of subscription products is 1, as is other product types.
- productType: Product types, which can be determined according to the SKU. There are four product types: (AWProductTypeConsumable: Consumable product, AWProductTypeNonConsumable: Non-consumable product, AWProductTypeAutoRenewable: Auto-renewal subscription, AWProductTypeNonRenewable: Non-automatic renewal subscription)


### Next Steps

[Restoring Purchases](/Restoring_Purchases)