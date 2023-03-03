调用该方法获取商品信息，应在展示商品页面前提前加载商品信息，完成商品的展示

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

<Tabs>
  <TabItem value="javascript" label="javascript">

```javascript
// See your keys here: https://dashboard.appwheel.com/projects/ and select app
const appwheel = new AppWheel("{App ID}", "{platfrom}", "App Secret")
appwheel.skus().then(res => res.json()).then(json => console.log(json.data.skus))
```

  </TabItem>
</Tabs>

### 参数

无

### 返回

```json

{
  "code": 0,
  "data": {
    "skus": [
      {
        "productId": "price_1LGLc9HedDJPunHoY5LZlOJy", // 保存在aw的productid
        "referenceName": "订阅测试", // 别名
        "pricingInfo": {// 通过 stripe 获取到的价格信息 源文档请参考https://stripe.com/docs/api/prices/object
          "active": true, // 价格是否可用于新购买。
          "billing_scheme": "per_unit",
          "created": 1656588773,
          "currency": "usd", //三字母 ISO 货币代码，小写。
          "deleted": false,
          "id": "price_1LGLc9HedDJPunHoY5LZlOJy", // 价格id
          "livemode": false, //对应stripe的真实模式和测试模式，如果对象以实时模式存在，则值为 true；如果对象以测试模式存在，则值为 false。
          "lookup_key": "", //用于从静态字符串中动态检索价格的查找键。
          "metadata": {//附加到对象的一组键值对。可以在stripe针对每个价格添加专属信息
            "project": "appwheel",
            "自定义键": "自定义信息"
          },
          "nickname": "测试价格", //价格简要说明。
          "object": "price",
          "recurring": {//周期性订阅商品的周期信息
            "aggregate_usage": "",
            "interval": "day", //订阅计费的频率。日、周、月或年之一。
            "interval_count": 1, // 订阅账单之间的间隔数（在 interval 属性中指定）。例如，interval=month 和 interval_count=3表示收费周期是3个月一次。
            "trial_period_days": 3, //可以在stripe价格配置的免费试用天数，但是实际stripe不用自动使用该配置。需要在创建订阅的时候另外传参
            "usage_type": "licensed"
          },
          "type": "recurring", //one_time 或 recurring 之一，具体取决于价格是一次性购买还是重复（订阅）购买。
          "unit_amount": 100,
          "unit_amount_decimal": "100"//以美分计的单位金额。仅在 billing_scheme=per_unit 时设置。
        }
      }
    ]
  },
  "message": "success"
}
```

### 下一步

[购买](/MakingPurchases/stripe)