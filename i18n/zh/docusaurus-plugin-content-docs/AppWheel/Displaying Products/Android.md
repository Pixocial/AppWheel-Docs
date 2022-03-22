# Android

## 获取商品
### 说明：
调用该方法获取商品信息，应在展示商品页面前提前加载商品信息，完成商品的展示

java:

```java
Market.getInstance().getProductsInfo(itemType, skuList, new OnQueryProductListener() {
    @Override
    public void onSuccess(List<Product> productInfo) {
    }

    @Override
    public void onError(int resultCode) {

    }
});
```
kotlin:

```kotlin
Market.getInstance().getProductsInfo(itemType, skuList, object : OnQueryProductListener {
    override fun onSuccess(productInfo: List<Product>) {
        
    }
    override fun onError(resultCode: Int) {
        
    }
})
```

### 参数：
- itemType：sku类型，INAPP、SUBS两种类型
- skuList ：sku的id的set集合
返回：
当请求成功时会通过`onSuccess`方法返回Product的集合