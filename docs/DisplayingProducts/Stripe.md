
This method is used to acquire product information. The product information should be loaded before displaying product page.


import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

<Tabs>
  <TabItem value="javascript" label="javascript">

```javascript
var axios = require('axios');

var config = {
    method: 'get',
    maxBodyLength: Infinity,
    url: 'https://sdk.api.appwheel.com/v1/purchase/skus',
    headers: {
        'Content-Type': 'application/json',
        'Accept': 'application/json'
    }
};

axios(config)
    .then(function (response) {
        console.log(JSON.stringify(response.data));
    })
    .catch(function (error) {
        console.log(error);
    });

```
  </TabItem>
</Tabs>

### 参数：
`productSet`:sku的id的set集合
### 返回：
`RetrievedProducts`结构包含成功获取的商品`AWProduct`数组，获取失败的商品SKU数组，以及`AWError`对象

### 下一步

[购买](/MakingPurchases/stripe.md)