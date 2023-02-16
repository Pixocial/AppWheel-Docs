主要介绍AW从Google Billing 3 迁移到Google Billing 5的修改部分。AW在版本：1.1.0.0的时候从Google Billing 3（以下简称V3）迁移到了Google Billing 5（以下简称V5），也对相关的接口进行了修改

## 删除类：Product、SubsProduct，使用ProductDetails代替商品信息。
由于V5的数据结构已经完全和V3的不一致了，所以弃用了之前的商品详情类，使用谷歌V5提供的 [ProductDetails](https://developer.android.com/reference/com/android/billingclient/api/ProductDetails)

## 初始化修改
appId由String类型改为Int类型

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

<Tabs>
  <TabItem value="Java" label="Java" default>

```Java

Billing.configure(context,appId,"secret")
                .build();
```
  </TabItem>
  <TabItem value="Kotlin" label="Kotlin">

```Kotlin
Billing.configure(context ,appid , “secret”).build()
```
  </TabItem>

</Tabs>

## 购买方法修改

### 旧版：


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

### 新版



<Tabs>
<TabItem value="Java" label="Java" default>

```Java
PurchaseProductInfo purchaseProductInfo = new PurchaseProductInfo();
purchaseProductInfo.productDetails = mProduct;
purchaseProductInfo.offerDetails = offerDetails;
purchaseProductInfo.upgradeInfo = upgradeInfo;
Market.getInstance().purchaseProduct(ProductDetailActivity.this ,purchaseProductInfo , new InitiatePurchaseListener() {
    @Override
    public void onVerifying(boolean isVerifying) {
        if(isVerifying){
            ToastUtil.show(Cxt.get(), "后台验证收据中...");
        }
    }

    @Override
    public void onPurchaseSuccess(MTGPurchase purchase) {
        // 购买成功
    }

    @Override
    public void onOwnedGoods(MTGPurchase purchase) {
        ToastUtil.show(Cxt.get(), "已经拥有该商品");
    }

    @Override
    public void onPurchaseError(int errorCode) {
        ToastUtil.show(Cxt.get(), "购买失败");
        ToastUtil.show(Cxt.get(), "errorCode = " + errorCode);
    }
});
```
</TabItem>
<TabItem value="Kotlin" label="Kotlin">

```Kotlin

val purchaseProductInfo = PurchaseProductInfo();
purchaseProductInfo.productDetails = mProduct;
purchaseProductInfo.offerDetails = offerDetails;
purchaseProductInfo.upgradeInfo = upgradeInfo;

Market.getInstance().purchaseProduct(activity, purchaseProductInfo, object : InitiatePurchaseListener {
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

#### 新增类：PurchaseProductInfo

```Java
public class PurchaseProductInfo {
    /**
     * 需要购买的商品：必传参数
     */
    public ProductDetails productDetails;
    /**
     * 使用的优惠：subs商品必传，inApp类型商品不用传
     */
    @Nullable
    public ProductDetails.SubscriptionOfferDetails offerDetails;

    /**
     * 升降级：如有用到升降级，可传改参数，没有用到不用传
     */
    @Nullable
    public UpgradeInfo upgradeInfo;
    /**
     * aw生成的订单id：app不用处理，SDK内部使用的参数
     */
    @Nullable
    public String awOrderId;
}

```

### MTGPurchase添加属性productType

MTGPurchase添加属性productType，productType的含义，inApp：0、续期订阅:2、预付费:3
