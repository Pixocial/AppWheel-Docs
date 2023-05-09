---
sidebar_position: 11
title: ProductHasPaied
id: ProductHasPaied
---


查询商品是否被购买过的状态

 
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

<Tabs>
  <TabItem value="Java" label="Java" default>

```Java

Market.getInstance().getProductHasPaid(productId, new AWHttpCallback<ProductPurchaseState>() {
    @Override
    public void onSuccess(ProductPurchaseState response) {

    }

    @Override
    public void onError(String errorCode, String errorMsg) {

    }
});
```

  </TabItem>
  <TabItem value="Kotlin" label="Kotlin">

```Kotlin

Market.getInstance().getProductHasPaid(productid,object : AWHttpCallback<ProductPurchaseState>{
    override fun onSuccess(response: ProductPurchaseState?) {
    }

    override fun onError(errorCode: String?, errorMsg: String?) {
    }
})
```

  </TabItem>
  <TabItem value="Objective-C" label="Objective-C">

```Objective-C 

[AWPurchaseKit getProductHasPaiedWithProductId:productId withcompletion:^(BOOL success, AWProductPurchaseState * _Nullable state, AWError * _Nullable error) {
}];
```
  </TabItem>
  <TabItem value="Swift" label="Swift">

```Swift

AWPurchaseKit.getProductHasPaied(withProductId: String) { Bool, AWProductPurchaseState?, AWError? in
    
}
```
 </TabItem>
</Tabs>

### Parameters:
- productId:需要查询的商品ID
