
用户选择商品后，调用该方法完成在appStore的购买，需要注意开发者应该在调用该方法前判断商品类型，然后传入该方法的productType参数中完成购买。


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

### 参数：
- product：需要购买的商品

### 消耗
#### 说明：
仅限INAPP类型的商品paymentType为2，订阅商品无需使用该接口，如果购买了INAPP商品没有消耗掉的话是不能再次购买的，需要消耗掉才能在下次购买。
java:

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

#### 参数：
- purchase: MTGPurchase类型，开发者应该根据自己需要消耗的商品选择对应的purchase



### 下一步

[恢复购买](/Restoring_Purchases)