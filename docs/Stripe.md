import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

## 支付方式管理

### 增加支付方式

<Tabs>
  <TabItem value="Javascript" label="Javascript">

```Javascript
const appwheel = new AppWheel({AppID}, {platfrom}, {AppSecret})
appwheel.createPaymentMethod({
    "appUserId": "appuserid",
    "type": "checkout",
    "successUrl": "http://www.baidu.com?success",
    "cancelUrl": "http://www.baidu.com?cancel"
}).then(res => res.json()).then(json => console.log)
```

</TabItem>
</Tabs>

### 参数

| 字段 | 类型 | 必须 | 说明 |
|:----------------|:-------------:|:--:|:-------------------------------|
| appUserId | string | 是 | 用户唯一标识，如果使用[Athena](https://docs.pixocial.io/athena/docs/intro)登录，建议传入openid |
| type | string | 是 | 支持 checkout / setupIntent |
| successUrl | string | 是 | 添加成功后的回调地址 |
| cancelUrl | string | 是 | 取消添加的回调地址 |

### 返回

```json
{
  "code": 0,
  "data": {
    "checkoutUrl": "https://checkout.stripe.com/pay/cs_test_xxx",
    //checkout模式下才有值 ，需要跳转页面
    "checkoutId": "cs_test_c1RgAVGryEHuAkgCp7uu5vRPjB5tx0kQz8OMc663ZRqYwCmtmV6nWSDE0E",
    "setupIntentId": "seti_1LQne5HedDJPunHoLNgozUjU",
    "clientSecret": "seti_1LQne5HedDJPunHoLNgozUjU_secret_M95pS4k3ATxviQuFZrW8aPY60FrAR4p"
    //setupIntent模式下才有值 ，需要用户前端调用js sdk 确认
  },
  "message": "success"
}

```

### 获取支付方式


<Tabs>
  <TabItem value="Javascript" label="Javascript">

```Javascript
const appwheel = new AppWheel({AppID}, {platfrom}, {AppSecret})
appwheel.paymentMethod({
    "appUserId": "appuserid"
}).then(res => res.json()).then(json => console.log)
```

</TabItem>
</Tabs>

### 参数

| 字段 | 类型 | 必须 | 说明 |
|:----------------|:-------------:|:--:|:-------------------------------|
| appUserId | string | 是 | 用户唯一标识 |
### 返回

```json
{
  "code": 0,
  "data": {
    "methods": [
      {
        "billing_details": { //与特定类型的支付方式可能使用或需要的 PaymentMethod 相关的账单信息。
          "address": {
          },
          "email": "xx@pixocial.com",
          "name": "xx",
          "phone": ""
        },
        "card": {
          "brand": "visa", //可以是 amex、diners、discover、jcb、mastercard、unionpay、visa 或 unknown。
          "checks": { //检查卡地址和 CVC（如果提供）。
            "address_line1_check": "",
            "address_postal_code_check": "",
            "cvc_check": "pass"
          },
          "country": "US",//代表卡所在国家/地区的两个字母 ISO 代码。
          "description": "",
          "exp_month": 3, //代表卡到期月份的两位数。
          "exp_year": 2033, //代表卡到期年份的四位数字。
          "fingerprint": "yyqfTDrZqoDLBhCJ",
          "funding": "credit", //卡资金类型。可以是credit, debit, prepaid, or unknown
          "iin": "",
          "issuer": "",
          "last4": "4242",//卡的最后四位数字。
          "networks": {
            "available": [
              "visa"
            ],
            "preferred": ""
          },
          "three_d_secure_usage": {
            "supported": true
          },
          "wallet": null
        },
        "created": 1657022195,
        "id": "pm_1LIAMpHedDJPunHopnXVhytz",//支付方式id
        "object": "payment_method",
        "type": "card" //PaymentMethod 的类型。https://stripe.com/docs/payments/payment-methods/overview#cards

      }
    ]
  },
  "message": "success"
}

```

### 删除支付方式

***注意：不建议删除所有用户支付方式，否则会影响订阅扣费。***

<Tabs>
  <TabItem value="Javascript" label="Javascript">

```Javascript
const appwheel = new AppWheel({AppID}, {platfrom}, {AppSecret})
appwheel.removePaymentMethod({
    "appUserId": "stripe_test",
    "methodId" :"pm_1LQnxxxx"
}).then(res => res.json()).then(json => console.log)
```

</TabItem>
</Tabs>

### 参数

| 字段 | 类型 | 必须 | 说明 |
|:----------------|:-------------:|:--:|:-------------------------------|
| appUserId | string | 是 | 用户唯一标识 |
| methodId |stripe|是|支付方式id,通过支付方式列表获取。
### 返回

```json
{
  "code": 0,
  "data": {
    "methodId": "pm_1LQneqHedDJPunHoLCaQBcWM"
  },
  "message": "success"
}
```

### Stripe账单接口
通过Api接口获取用户支付账单列表。

<Tabs>
  <TabItem value="Javascript" label="Javascript">

```Javascript
const appwheel = new AppWheel({AppID}, {platfrom}, {AppSecret})
appwheel.invoices({
    "appUserId": "stripe_test"
}).then(res => res.json()).then(json => console.log)
```

</TabItem>
</Tabs>

### 参数

| 字段 | 类型 | 必须 | 说明 |
|:----------------|:-------------:|:--:|:-------------------------------|
| appUserId | string | 是 | 用户唯一标识 |
### 返回

```json
{
  "code": 0,
  "data": {
    "invoices": [
      {
        "originOrderId": "sub_1LNX9zHedDJPunHoLEuMu7y7", // 订阅id
        "orderId": "in_1LNX9zHedDJPunHoTK37GPVK", // 账单id
        "productId": "price_1LGe1wHedDJPunHob19JriJl",// 购买商品
        "productPeriod": "P1D", // 订阅商品的周期,可能值 P1D P3D P1M P1Y  
        "billingCycleAnchor": "0", // 订阅的下次收款时间
        "customerEmail": "", //账单邮箱
        "invoicePdf": "https://pay.stripe.com/invoice/acct_1KR9XuHedDJPunHo/test_YWNjdF8xS1I5WHVIZWRESlB1bkhvLF9NNWliVXhSaUFrQWdUNlFnMklIQXpzdWJtQWhseVQ0LDQ4ODQyMjU50200imH1r5z6/pdf?s=ap",//账单pdf下载地址
        "hostedInvoiceUrl": "https://invoice.stripe.com/i/acct_1KR9XuHedDJPunHo/test_YWNjdF8xS1I5WHVIZWRESlB1bkhvLF9NNWliVXhSaUFrQWdUNlFnMklIQXpzdWJtQWhseVQ0LDQ4ODQyMjU50200imH1r5z6?s=ap", // 账单详细页面
        "paidAt": "0", //涨到支付时间
        "invoiceStatus": "", // 账单支付状态
        "orderStatus": 1 // 账单期间订阅的状态
      }
    ]
  },
  "message": "success"
}
```