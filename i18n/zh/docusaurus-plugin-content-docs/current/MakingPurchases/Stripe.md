---
sidebar_position: 3
title: Stripe
id: stripe
---

用户选择商品后，可以开始购买流程，接入方需要准备好回调地址，在用户付款成功后会回调到`successUrl`或者`cancelUrl`，接收到该回调后可以展示支付成功、跳转回订阅前的Web页面或者打开客户端程序。

![购买历程图](/img/stripePayments/sub_buy.jpg)

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

<Tabs>
 <TabItem value="javascript" label="javascript">

```javascript
// See your keys here: https://dashboard.appwheel.com/projects/ and select app
const appwheel = new AppWheel({AppID}, {platfrom}, {AppSecret})
appwheel.createPurchase({
    "appUserId": {appuserid},
    "productId": {productId},
    "successUrl": {successUrl},
    "cancelUrl": {cancelUrl}
}).then(res => res.json()).then(json => window.open(json.data.checkoutUrl))
```

  </TabItem>
</Tabs>

### 参数

| 字段 | 类型 | 必须 | 说明 |
|:----------------|:-------------:|:--:|-------------------------------:|
| appUserId | string | 是 | 用户唯一标识，如果使用[Athena](https://docs.pixocial.io/athena/docs/intro)登录，建议传入openid |
| productId | string | 是 | 从获取商品接口获取到的productId |
| successUrl | string | 是 | 支付成功后的回调地址 |
| cancelUrl | string | 是 | 取消支付的回调地址 |
| trialPeriodDays | int | 否 | 免费试用天数 |
|promotionCode| array &lt;string&gt; | 否 |优惠码，选填，目前只支持一个优惠码|
更多Api接口[点击此处](/Installation/api)

### 下一步

[订单和权益查询](/UserBenefits/api)