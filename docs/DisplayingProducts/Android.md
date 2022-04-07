

 This method is used to acquire product information. The product information should be loaded before displaying product page.


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


### Parameters:
- itemType: SKU types, including INAPP and SUBS.
- skuList : Collection of SKU IDs.
 Return:
When the request is successful, the collection of Products will be returned through the onSuccess method.