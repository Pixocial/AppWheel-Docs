

 This method should be called to complete a purchase when a user has selected a product. The developers should tell the product type before calling this method and then pass the productType to complete the purchase.

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

<Tabs>
  <TabItem value="Java" label="Java" default>

```Java
Market.getInstance().purchaseProduct(ProductDetailActivity.this, mProduct, new InitiatePurchaseListener() {
    @Override
    public void onVerifying(boolean isVerifying) {
       // Callback of onging verification in the backend
    }

    @Override
    public void onPurchaseSuccess(MTGPurchase purchase) {
       //Purchase success callback
   }

    @Override
    public void onOwnedGoods(MTGPurchase purchase) {
       //Purchased status callback
    }

    @Override
    public void onPurchaseError(int errorCode) {
       //Callback of abnormal purchases
    }
});
```
  </TabItem>
  <TabItem value="Kotlin" label="Kotlin">

```Kotlin
Market.getInstance().purchaseProduct(activity, mProduct, object : InitiatePurchaseListener {
    override fun onVerifying(isVerifying: Boolean) {
        //Callback of ongoing backend verification
    }

    override fun onPurchaseSuccess(purchase: MTGPurchase) {
        //Purchase success callback
    }

    override fun onOwnedGoods(purchase: MTGPurchase) {
        //Purchased status callback
    }

    override fun onPurchaseError(errorCode: Int) {
        //Callback of abnormal purchases
    }
})
```
  </TabItem>

</Tabs>

### Parameters:
- product: Products to be purchased

### Consumption

#### Description:
 The paymentType for INAPP products is 2 and there is no need to use this interface for subscription products. If the purchased INAPP products are not consumed, then cannot be purchased again until they are consumed.

<Tabs>
  <TabItem value="Java" label="Java" default>

```Java
Market.getInstance().consumePurchaseFlow(purchase, new ConsumeResponseListener() {
    @Override
    public void onConsumeResponse(int resultCode) {
        if(resultCode == Types.BillingResponseCode.OK){
            BillingLog.i(TAG , "consumeMembership Success -" + purchase.getProductId());
        }
    }
});
```
  </TabItem>
  <TabItem value="Kotlin" label="Kotlin">

```Kotlin
Market.getInstance().consumePurchaseFlow(purchase, object : ConsumeResponseListener() {
    fun onConsumeResponse(resultCode: Int) {
        if (resultCode == Types.BillingResponseCode.OK) {
            BillingLog.i(TAG, "consumeMembership Success -" + purchase.getProductId())
        }
    }
})
```
  </TabItem>
</Tabs>

#### Parameters:
- purchase: MTGPurchase type. Please choose the corresponding purchase value according to the products you need.

### Next Steps

[Restoring Purchases](/Restoring_Purchases)