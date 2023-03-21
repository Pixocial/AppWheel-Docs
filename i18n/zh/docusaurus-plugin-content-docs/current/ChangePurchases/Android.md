---
sidebar_position: 0
title: Android
id: Android
---

## 升降级
您可为用户提供不同的订阅层级，例如基本层级和高级层级。详情请参阅【[升级、降级](https://developer.android.com/google/play/billing/subscriptions?hl=zh-cn#change)】



import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

<Tabs>
  <TabItem value="Java" label="Java" default>

```Java
UpgradeInfo upgradeInfo = new UpgradeInfo(oldSubsPurchase , prorationMode);

Market.getInstance().purchaseProduct(ProductDetailActivity.this, mProduct, upgradeInfo, new InitiatePurchaseListener() {
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
val info = UpgradeInfo(oldSubsPurchase, prorationMode)

Market.getInstance().purchaseProduct(activity, mProduct, info, object : InitiatePurchaseListener {
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
- oldSubsPurchase: 需要被升级的订单
- prorationMode: 计费模式
- product: 需要新买的商品

## 退款
开发者可以主动调用接口来为用户退款并[取消订阅](https://developer.android.com/google/play/billing/subscriptions?hl=zh-cn#revoke),被取消的订阅用户将不再享受权益



<Tabs>
  <TabItem value="Java" label="Java" default>

```Java
 Market.getInstance().revoke(productId, new RevokeResponseListener() {
    @Override
    public void onSuccess(int resultCode) {
        .....
    }

    @Override
    public void onFail(String resultCode, String msg) {
        .....
    }
});
```
  </TabItem>
  <TabItem value="Kotlin" label="Kotlin">

```Kotlin
Market.getInstance().revoke(productId,object : RevokeResponseListener{
    override fun onSuccess(resultCode: Int) {
        TODO("Not yet implemented")
    }

    override fun onFail(resultCode: String?, msg: String?) {
        TODO("Not yet implemented")
    }
})
```
  </TabItem>

</Tabs>

### Parameters:
- productId: 需要取消的商品ID