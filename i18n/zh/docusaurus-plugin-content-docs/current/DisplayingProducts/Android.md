
调用该方法获取商品信息，应在展示商品页面前提前加载商品信息，完成商品的展示

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

<Tabs>
  <TabItem value="Java" label="Java" default>

```Java
Market.getInstance().getProductsInfo(itemType, skuList, new OnQueryProductListener() {
    @Override
    public void onSuccess(List<Product> productInfo) {
    }

    @Override
    public void onError(int resultCode) {

    }
});
```
  </TabItem>
  <TabItem value="Kotlin" label="Kotlin">

```Kotlin
Market.getInstance().getProductsInfo(itemType, skuList, object : OnQueryProductListener {
    override fun onSuccess(productInfo: List<Product>) {
        
    }
    override fun onError(resultCode: Int) {
        
    }
})
```
  </TabItem>

</Tabs>

### 参数：
- itemType：sku类型，INAPP、SUBS两种类型
- skuList ：sku的id的set集合
返回：
当请求成功时会通过`onSuccess`方法返回Product的集合