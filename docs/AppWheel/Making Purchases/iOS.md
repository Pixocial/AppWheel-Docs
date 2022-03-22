# iOS

## Purchase Products
### Description:
 This method should be called to complete a purchase when a user has selected a product. The developers should tell the product type before calling this method and then pass the productType to complete the purchase.

Objective-C:

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
Swift:

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

### Parameters:
- product: Products
- paymentDiscount: Discounts. Only for subscription products and can be acquired through Product.discounts. No transferable nil. 
- quantity: The quantity of purchases. The quantity of subscription products is 1, as is other product types.
- productType: Product types, which can be determined according to the SKU. There are four product types: (0: Consumable product, 1: Non-consumable product, 2: Auto-renewal subscription, and 3: Non-automatic renewal subscription) Please refer to the AWProductType in [AppWheel SDK Integration Document - Introduction to iOS Classes]().

