---
sidebar_position: 3
title: Api接口
id: stripe
---

完成订阅的支付后，可以通过Api获取当前订阅权益,配置在[权益和商品配置](/ConfiguringProduct/entitlements) 中将多个App商品与同一个权益关联，该接口还会返回其他端App的订阅状态。

### 请求

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

<Tabs>
  <TabItem value="javascript" label="javascript">

```javascript
const appwheel = new AppWheel({AppID}, {platfrom}, {AppSecret})
appwheel.entitlement(this.appuserid).then(res => res.json()).then((json) => {
    console.log("当前有效权益", Object.keys(json.data.entitlement))
    console.log("当前已失效权益", Object.keys(json.data.invalidEntitlement))
})

```

</TabItem>
</Tabs>

### 返回

```json
{
  "code": 0,
  "data": {
    // 有效的权益
    "entitlement": {// 权益标识，权益生效商品为，过期时间大的优先，非宽限期商品优先
      "vip": {
        "originalPurchaseDateMs": "1654081486000", // 权益生效时间，毫秒
        "expiresDateMs": "1654167886000",  // 过期时间，毫秒
        "gracePeriodExpiresDateMs": "0",// 宽限期时间，毫秒 
        // 未过期，满足权益的所有订单详细，续订订单只有最后生效的一笔，同一个商品仅存在最后购买的一笔（规则：正常订单>宽限期订单>其他状态，同状态下，过期时间大的优先，宽限期为宽限期时间大的优先）
        "orders": [
          {
            "productPeriod": "P1D", // 商品订阅周期间隔只。有Stripe商品有返回，ios/google为空；P1D表示订阅周期是天 P3D每三天一个周期，P1W每周,P2M每两月，P1Y每一年
            "appId": 331058835, // appid
            "platform": "Stripe", // 平台 iOS，Android，Stripe
            "productId": "price_1LGLc9HedDJPunHoY5LZlOJy", // 商品id
            "isAutoRenew": true, // 是否自动续订
            "productType": 2, // 商品类别 0消耗商品，1非消耗商品，2自动续订商品，3非自动续订商品
            "originalTransactionId": "sub_1LIVkBHedDJPunHoaPhGer95", // 原始交易id，订阅id
            "transactionId": "in_1LIVkBHedDJPunHozzGmnWyo", // 交易id
            "originalPurchaseDateMs": "1657104367000", // 首次购买时间
            "purchaseDateMs": "1657104367000", // 非必须（android时不存在），购买时间
            "gracePeriodExpiresDateMs": "0", // 宽限期过期时间，续订扣款失败后尝试重复扣款的时间，宽限期时有效。 针对ios android 是准确的 ，stripe订单是当前周期的结束时间，不准确
            "expiresDateMs": "1659782767000", // 过期时间
            "isTrialPeriod": false, // 非必须（android时不存在），试用期
            "status": 1 // 状态 订单状态：0 未付款 1 付款正常使用 2 过期 3 宽限期 4 暂停 5 保留期',
          }
        ]
      }
    },
    // 失效的权益，字段说明参考有效的权益
    "invalidEntitlement": {}
  },
  "message": "操作成功"
}
```


