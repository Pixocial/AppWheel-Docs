# Android

## 购买商品
### 说明：
用户选择商品后，调用该方法完成在appStore的购买，需要注意开发者应该在调用该方法前判断商品类型，然后传入该方法的productType参数中完成购买。

java:

```java
Market.getInstance().purchaseProduct(ProductDetailActivity.this, mProduct, new InitiatePurchaseListener() {
    @Override
    public void onVerifying(boolean isVerifying) {
       // 后台验证中的回调
    }

    @Override
    public void onPurchaseSuccess(MTGPurchase purchase) {
       // 购买成功回调
   }

    @Override
    public void onOwnedGoods(MTGPurchase purchase) {
       // 已购买状态回调
    }

    @Override
    public void onPurchaseError(int errorCode) {
       // 购买异常回调
    }
});
```
kotlin:

```kotlin
Market.getInstance().purchaseProduct(activity, mProduct, object : InitiatePurchaseListener {
    override fun onVerifying(isVerifying: Boolean) {
        // 切换后台验证状态回调
    }

    override fun onPurchaseSuccess(purchase: MTGPurchase) {
        // 购买成功回调
    }

    override fun onOwnedGoods(purchase: MTGPurchase) {
        // 已购买状态回调
    }

    override fun onPurchaseError(errorCode: Int) {
        // 购买异常回调
    }
})
```

### 参数：
- product：需要购买的商品
### 消耗
#### 说明：
仅限INAPP类型的商品paymentType为2，订阅商品无需使用该接口，如果购买了INAPP商品没有消耗掉的话是不能再次购买的，需要消耗掉才能在下次购买。
java:

```java
Market.getInstance().consumePurchaseFlow(purchase, new ConsumeResponseListener() {
    @Override
    public void onConsumeResponse(int resultCode) {
        if(resultCode == Types.BillingResponseCode.OK){
            BillingLog.i(TAG , "consumeMembership Success -" + purchase.getProductId());
        }
    }
});
```
kotlin:

```kotlin
Market.getInstance().consumePurchaseFlow(purchase, object : ConsumeResponseListener() {
    fun onConsumeResponse(resultCode: Int) {
        if (resultCode == Types.BillingResponseCode.OK) {
            BillingLog.i(TAG, "consumeMembership Success -" + purchase.getProductId())
        }
    }
})
```

#### 参数：
- purchase: MTGPurchase类型，开发者应该根据自己需要消耗的商品选择对应的purchase