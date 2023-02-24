---
sidebar_position: 1
title: Api
id: api
---
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

AppWheel支持Stripe支付，支持Api接口，并以Web形式的页面支付，提供JS SDK。

<Tabs>
  <TabItem value="Javascript" label="Javascript">

```Javascript
let CryptoJS = require("crypto-js")

function AppWheel(appid, platform, accessKey) {
    if (!(this instanceof AppWheel)) {
        return new (AppWheel)(appid, platform, accessKey);
    }
    this.appid = appid
    this.platform = platform
    this.accessKey = accessKey
    this.baseUrl = "https://sdk.api.appwheel.com"


    this.sign = function (method, uri, body) {
        let date = new Date();
        let tm = Math.floor(date.getTime() / 1000).toString();
        let nonce = date.getTime().toString();
        let strToSign = tm + "\n" + nonce + "\n" + method + " " + uri + "\n"
        if (method !== "GET" && Object.keys(body).length !== 0) {
            let payloadHash = CryptoJS.MD5(body).toString()
            strToSign += payloadHash;
        }
        strToSign = strToSign.toLowerCase()
        let app_id = this.appid
        let secret = this.accessKey
        let platform = this.platform
        let sign = CryptoJS.HmacSHA256(strToSign.toLowerCase(), secret);
        sign = "Signature " + CryptoJS.enc.Hex.stringify(sign);

        return {
            "X-Request-AppId": app_id.toString(), "X-Request-Platform": platform, "X-Request-Nonce": nonce, "X-Request-Uri": uri, "X-Request-Timestamp": tm, "Authorization": sign,
        }
    }

    this.initUser = function (appuserid, body) {
        body = JSON.stringify(body)
        let url = "/v1/users"
        if (appuserid && appuserid !== "") {
            url = url + "/" + appuserid
        }
        return fetch(this.baseUrl + url, {
            method: "POST", body: body, headers: Object.assign(this.sign("POST", url, body), {"Content-Type": "application/json"})
        })

    }
    this.skus = function () {
        let url = "/v1/purchase/skus"
        return fetch(this.baseUrl + url, {
            headers: this.sign("GET", url)
        })
    }
    this.createPurchase = function (body) {
        body = JSON.stringify(body)
        let url = "/v1/stripe/purchase/create"
        return fetch(this.baseUrl + url, {
            method: "POST", body: body, headers: Object.assign(this.sign("POST", url, body), {"Content-Type": "application/json"})
        })
    }
    this.updatePurchase = function (body) {
        body = JSON.stringify(body)
        let url = "/v1/stripe/purchase/update"
        return fetch(this.baseUrl + url, {
            method: "POST", body: body, headers: Object.assign(this.sign("POST", url, body), {"Content-Type": "application/json"})
        })
    }

    this.cancelPurchase = function (body) {
        body = JSON.stringify(body)
        let url = "/v1/stripe/purchase/cancel"
        return fetch(this.baseUrl + url, {
            method: "POST", body: body, headers: Object.assign(this.sign("POST", url, body), {"Content-Type": "application/json"})
        })
    }

    this.customPortal = function (body) {
        body = JSON.stringify(body)
        let url = "/v1/stripe/customPortal"
        return fetch(this.baseUrl + url, {
            method: "POST", body: body, headers: Object.assign(this.sign("POST", url, body), {"Content-Type": "application/json"})
        })
    }
    this.renewPurchase = function (body) {
        body = JSON.stringify(body)
        let url = "/v1/stripe/purchase/renew"
        return fetch(this.baseUrl + url, {
            method: "POST", body: body, headers: Object.assign(this.sign("POST", url, body), {"Content-Type": "application/json"})
        })
    }
    this.entitlement = function (appuserid) {
        let url = `/v1/subscriber/${appuserid}/entitlement`
        return fetch(this.baseUrl + url, {
            headers: this.sign("GET", url)
        })
    }
}


module.exports = AppWheel;
module.exports.AppWheel = AppWheel;

module.exports.default = AppWheel;

```

</TabItem>
</Tabs>

# 全部接口和定义如下

## 获取sku列表

作用：获取Sku列表 ，如果是Stripe 商品，会透传Stripe价格信息给客户端， Stripe价格信息源文档请参考https://stripe.com/docs/api/prices/object

- path: /v1/purchase/skus
- Method: get
- Body:
- Request:

```json
{
  "code": 0,
  "data": {
    "skus": [
      {
        "productId": "price_1LGLc9HedDJPunHoY5LZlOJy",
        // 保存在aw的productid，对应的是stripe 的 pricing_id
        "referenceName": "订阅测试",
        // product别名
        "pricingInfo": {
          // 通过 stripe 获取到的价格信息 源文档请参考https://stripe.com/docs/api/prices/object
          "active": true,
          // 价格是否可用于新购买。
          "billing_scheme": "per_unit",
          "created": 1656588773,
          "currency": "usd",
          //三字母 ISO 货币代码，小写。
          "deleted": false,
          "id": "price_1LGLc9HedDJPunHoY5LZlOJy",
          // 价格id
          "livemode": false,
          //对应stripe的真实模式和测试模式，如果对象以实时模式存在，则值为 true；如果对象以测试模式存在，则值为 false。
          "lookup_key": "",
          //用于从静态字符串中动态检索价格的查找键。
          "metadata": {
            //附加到对象的一组键值对。可以在stripe针对每个价格添加专属信息
            "project": "appwheel",
            "自定义键": "自定义信息"
          },
          "nickname": "测试价格",
          //价格简要说明。
          "object": "price",
          "product": {
            // stripe的产品信息，stripe订阅的是 pricing。只是stripe的pricing是归属于product的。
            "active": false,
            "attributes": null,
            "caption": "",
            "created": 0,
            "deactivate_on": null,
            "default_price": null,
            "deleted": false,
            "description": "",
            "id": "prod_LyICgaBvZP0mz2",
            "images": null,
            "livemode": false,
            "metadata": null,
            "name": "",
            "object": "",
            "package_dimensions": null,
            "shippable": false,
            "statement_descriptor": "",
            "tax_code": null,
            "type": "",
            "unit_label": "",
            "updated": 0,
            "url": ""
          },
          "recurring": {
            //周期性订阅商品的周期信息
            "aggregate_usage": "",
            "interval": "day",
            //订阅计费的频率。day、week、month或year之一。
            "interval_count": 1,
            // 订阅账单之间的间隔数（在 interval 属性中指定）。例如，interval=month 和 interval_count=3表示收费周期是3个月一次。
            "trial_period_days": 3,
            //可以在stripe价格配置的免费试用天数，但是实际stripe不用自动使用该配置。需要在创建订阅的时候另外传参
            "usage_type": "licensed"
          },
          "tax_behavior": "exclusive",
          //指定价格被视为含税还是不含税。inclusive, exclusive, or unspecified之一。一旦指定为inclusive或exclusive，就不能更改。
          "tiers": null,
          "tiers_mode": "",
          "transform_quantity": null,
          "type": "recurring",
          //one_time 或 recurring 之一，具体取决于价格是一次性购买还是重复（订阅）购买。
          "unit_amount": 100,
          "unit_amount_decimal": "100"
          //以美分计的单位金额。仅在 billing_scheme=per_unit 时设置。
        }
      }
    ]
  },
  "message": "success"
}
```

## 取消续订

作用：取消续订，不会产生退款，当前周期仍继续提供服务，当前计费周期结束后结束订阅，不再产生收费。

- path: /v1/stripe/purchase/cancel
- Method: post
- Body:

```json
{
  "appUserId": "stripe-test",
  //  必填 app用户
  "purchaseId": "sub_1LAAmLHedDJPunHoGG8ohGBA"
  //必填 订阅订单id ，通过获取当前订阅权益 接口获取到的originalTransactionId
}
```

- Reposne:

```
{
"code":0
}
```

## 恢复续订(2022-08-15 新增)

作用：恢复续订，将取消续订，但未结束的订单恢复续订状态

- path: /v1/stripe/purchase/renew
- Method: post
- Body:

```json
{
  "appUserId": "stripe-test",
  //  必填 app用户
  "purchaseId": "sub_1LAAmLHedDJPunHoGG8ohGBA"
  //必填 订阅订单id ，通过获取当前订阅权益 接口获取到的originalTransactionId
}
```

- Reposne:

```json
{
  "code": 0
}
```

## 更新订阅

作用：更新订阅套餐，传入新的套餐进行订阅升级，如果扣费成功，新套餐会立即生效，否则需要打开接口返回的支付地址进行操作。
如果支付失败，订阅套餐不会有改变。

- path: /v1/stripe/purchase/update
- Method: post
- Body:

```json
{
  "appUserId": "tempor deserunt laborum eiusmo",
  // 必填 app用户
  "productId": "in ipsum elit Excepteur ut",
  // 选填 ，新的 project id
  "purchaseId": "amet non est dolor sunt"
  //必填 订阅订单id ，通过获取当前订阅权益 接口获取到的originalTransactionId
}
```

- Reponse:

```json
{
  "code": 200,
  "data": {
    "hostedInvoiceUrl": "http://payment.stripe.com/******"
    // 升级如果需要补尾款，那么就会有值，否则自动升级成功
  }
}
```

## 创建订阅

作用：用户通过该接口创建订阅，并完成付款操作。目前只支持订阅类型商品购买，不支持一次性付费商品。

- path：/v1/stripe/purchase/create
- method: Post
- Body:

```json
 {
  "appUserId": "{{appuserid}}",
  // 必填，业务方自定义的订阅者ID
  "productId": "{{productId}}",
  // 必填，2.3填写的SKU ID
  "successUrl": "{{SucessUrl}}",
  // 必填，购买成功后跳转回业务方的地址
  "cancelUrl": "{{CancelUrl}}",
  // 必填，取消购买跳转回业务方的地址
  "trialPeriodDays": 3,
  // 选填，免费天数
  "promotionCode": [
    "DDD"
  ]
  // 优惠码，选填，目前只支持一个优惠码
}
```

- Response

```json
{
  "code": 0,
  "message": "success",
  "data": {
    "
    checkoutUrl
    ": "
    https: //checkout.stripe.com/pay/cs_test_b1w30tabJbJnX8GMOoZVvLef1ReZ1phM6N7aRceXwezIGKa8gKFOWTakhA#fidkdWxOYHwnPyd1blpxYHZxWjA0Tlc8XXBNYGFBT1Vwa01qQFNGdmA9TmlTTnU1SkZnNWJBfFZWX0tPQjBqalc0TU9yY0xMalZAfXFSbHJqX2REPEFBNGRBbkRKMGxXc2xjcUxiaHxKPUtmNTVRRkN%2FSnBmMCcpJ2N3amhWYHdzYHcnP3F3cGApJ2lkfGpwcVF8dWAnPydocGlxbFpscWBoJyknYGtkZ2lgVWlkZmBtamlhYHd2Jz9xd3BgeCUl"，
    //付款页面
    "awTransId"
    :
    ""
    //aw 本身的交易id
  }
}
```

## 用户订阅管理页面

作用：Stripe提供的托管页面，展示用户订阅信息、支付方式、账单等信息，可以允许客户直接管理订阅套餐。
通过 https://dashboard.stripe.com/test/settings/billing/portal 进行配置。

- path：/v1/stripe/customPortal
- method：Post
- Body:

```json
{
  "appUserId": "{{appuserid}}",
  // 订阅者ID
  "returnUrl": "{{returnRul}}"
  // 跳转回业务方页面
}
```

- Response:

```json
{
  "code": 0,
  "message": "success",
  "data": {
    "sessionUrl": "https://billing.stripe.com/session/test_YWNjdF8xS1I5WHVIZWRESlB1bkhvLF9MTmVTZUVSaXhMVW1YZDEyU3ZZNktTT1Zyb2U1NzVy01005iaVqmkS"
    //管理页面
  }
}
```

## 获取当前订阅权益

作用：获取用户购买的订单和对应的权益，如果在2.4配置了多个app在同一个权益下，可以跨APP返回订单。
调用接口前请确认已经在AppWheel添加Entitlements并关联了商品

- path: /v1/subscriber/{{appuserid}}/entitlement
- Method: Get
- Body: 无
- Response:

```json
{
  "code": 0,
  "data": {
    // 有效的权益
    "entitlement": {
      // 权益标识，权益生效商品为，过期时间大的优先，非宽限期商品优先
      "vip": {
        // 权益生效时间，毫秒
        "originalPurchaseDateMs": "1654081486000",
        // 过期时间，毫秒
        "expiresDateMs": "1654167886000",
        // 宽限期时间，毫秒
        "gracePeriodExpiresDateMs": "0",
        // 未过期，满足权益的所有订单详细，续订订单只有最后生效的一笔，同一个商品仅存在最后购买的一笔（规则：正常订单>宽限期订单>其他状态，同状态下，过期时间大的优先，宽限期为宽限期时间大的优先）
        "orders": [
          {
            "productPeriod": "P1D",
            // 商品订阅周期间隔只。有Stripe商品有返回，ios/google为空；P1D表示订阅周期是天 P3D每三天一个周期，P1W每周,P2M每两月，P1Y每一年
            "appId": 331058835,
            // appid
            "platform": "Stripe",
            // 平台 iOS，Android，Stripe
            "productId": "price_1LGLc9HedDJPunHoY5LZlOJy",
            // 商品id
            "isAutoRenew": true,
            // 是否自动续订
            "productType": 2,
            // 商品类别 0消耗商品，1非消耗商品，2自动续订商品，3非自动续订商品
            "originalTransactionId": "sub_1LIVkBHedDJPunHoaPhGer95",
            // 原始交易id，订阅id
            "transactionId": "in_1LIVkBHedDJPunHozzGmnWyo",
            // 交易id
            "originalPurchaseDateMs": "1657104367000",
            // 首次购买时间
            "purchaseDateMs": "1657104367000",
            // 非必须（android时不存在），购买时间
            "gracePeriodExpiresDateMs": "0",
            // 宽限期过期时间，续订扣款失败后尝试重复扣款的时间，宽限期时有效。 针对ios android 是准确的 ，stripe订单是当前周期的结束时间，不准确
            "expiresDateMs": "1659782767000",
            // 过期时间
            "isTrialPeriod": false,
            // 非必须（android时不存在），试用期
            "status": 1
            // 状态 订单状态：0 未付款 1 付款正常使用 2 过期 3 宽限期 4 暂停 5 保留期',
          }
        ]
      }
    },
    // 失效的权益，字段说明参考有效的权益
    "invalidEntitlement": {
      "viper1": {
        "originalPurchaseDateMs": "1674107040000",
        "expiresDateMs": "1677044640000",
        "gracePeriodExpiresDateMs": "0",
        // 失效的订单，仅包含失效的订单，既非正常宽限期的订单，续订订单只有最后的一笔，同一个商品仅存在最后购买的一笔（规则：过期时间大的>过期时间小的）
        "orders": [
          {
            "productPeriod": "P1D",
            // 商品订阅周期间隔只有Stripe商品有返回，ios/google为空；P1D表示订阅周期是天 P3D每三天一个周期，P1W每周,P2M每两月，P1Y每一年
            "appId": 330953806,
            "platform": "Android",
            "productId": "com.miraclevision.fotoart.month",
            "isAutoRenew": false,
            "productType": 2,
            "originalTransactionId": "GPA.3383-1285-3830-92920",
            "transactionId": "GPA.3383-1285-3830-92920..5",
            "originalPurchaseDateMs": "1658126998922",
            "purchaseDateMs": "0",
            "gracePeriodExpiresDateMs": "0",
            "expiresDateMs": "1658129099459",
            "status": 2
          }
        ]
      }
    }
  },
  "message": "操作成功"
}
```

## 获取stripe支付方式

作用：获取stripe支付方式，目前只支持Stripe card 类型 ，Stripe支付方式字段说明请参考https://stripe.com/docs/api/payment_methods/object

- path: /v1/stripe/paymentMethod
- Method: Post
- Body:

```json
{
  "appUserId": "{{appuserid}}"
  // 订阅者ID
}
```

- Response:

```json
{
  "code": 0,
  "data": {
    "methods": [
      {
        "billing_details": {
          //与特定类型的支付方式可能使用或需要的 PaymentMethod 相关的账单信息。
          "address": {
            "city": "",
            "country": "SG",
            "line1": "",
            "line2": "",
            "postal_code": "",
            "state": ""
          },
          "email": "shengrong.wu@pixocial.com",
          "name": "wsr",
          "phone": ""
        },
        "card": {
          "brand": "visa",
          //可以是 amex、diners、discover、jcb、mastercard、unionpay、visa 或 unknown。
          "checks": {
            //检查卡地址和 CVC（如果提供）。
            "address_line1_check": "",
            "address_postal_code_check": "",
            "cvc_check": "pass"
          },
          "country": "US",
          //代表卡所在国家/地区的两个字母 ISO 代码。
          "description": "",
          "exp_month": 3,
          //代表卡到期月份的两位数。
          "exp_year": 2033,
          //代表卡到期年份的四位数字。
          "fingerprint": "yyqfTDrZqoDLBhCJ",
          "funding": "credit",
          //卡资金类型。可以是credit, debit, prepaid, or unknown
          "iin": "",
          "issuer": "",
          "last4": "4242",
          //卡的最后四位数字。
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
        "id": "pm_1LIAMpHedDJPunHopnXVhytz",
        //支付方式id
        "object": "payment_method",
        "type": "card"
        //PaymentMethod 的类型。https://stripe.com/docs/payments/payment-methods/overview#cards
      }
    ]
  },
  "message": "success"
}
```

## Stripe 账单接口

作用：获取stripe订单账单方式，目前与用户订阅管理页面保持一致，只返回支付账单。

- path: v1/stripe/invoices
- Method: Post
- Body:

```json
{
  "appUserId": "{{appuserid}}"
  // 订阅者ID
}
```

- Response:

```json
{
  "code": 0,
  "data": {
    "invoices": [
      {
        "originOrderId": "sub_1LPPDPHedDJPunHoLCJOdzsJ",
        //账单关联的订阅id
        "orderId": "in_1LPPDPHedDJPunHoVPJrjHxp",
        // 账单id
        "productId": "price_1LGe1wHedDJPunHob19JriJl",
        // 订阅商品
        "productPeriod": "P1D",
        // 商品周期
        "productReferenceName": "dd",
        // 在aw配置的商品别名
        "customerEmail": "shengrong.wu@pixocial.com",
        // 客户的电子邮件。在发票最终确定之前，此字段将等于 customer.email。发票完成后，该字段将不再更新。
        "invoicePdf": "https://pay.stripe.com/invoice/acct_1KR9XuHedDJPunHo/test_YWNjdF8xS1I5WHVIZWRESlB1bkhvLF9NN2VXa2Q1cGxqcXdhNTduRXF1SnJlYzMyOUNUOGNBLDQ5Mjg4Mzgw0200o00gnh81/pdf?s=ap",
        // 账单的pdf下载地址
        "hostedInvoiceUrl": "https://invoice.stripe.com/i/acct_1KR9XuHedDJPunHo/test_YWNjdF8xS1I5WHVIZWRESlB1bkhvLF9NN2VXa2Q1cGxqcXdhNTduRXF1SnJlYzMyOUNUOGNBLDQ5Mjg4Mzgw0200o00gnh81?s=ap",
        // stripe账单管理页面，对于未完成的订单，可以通过这页面让用户完成支付
        "paidAt": "1658739686000",
        // 账单支付时间
        "invoiceStatus": "paid",
        //账单状态，open, paid, uncollectible, or void open状态的订单，可以 通过 hostedInvoiceUrl 打开账单地址完成支付
        "payPrice": "1000",
        // 支付金额，在原价格上 *1000,使用需要自己换算
        "payCurrency": "USD",
        // 支付货币
        "invoiceCreatedAt": "1658739686000"
        // 账单创建时间
      },
      {
        "originOrderId": "sub_1LPPDPHedDJPunHoLCJOdzsJ",
        "orderId": "in_1LPPGJHedDJPunHoiTJsFajA",
        "productId": "price_1LGe1wHedDJPunHob19JriJl",
        "productPeriod": "P1D",
        "productReferenceName": "dd",
        "customerEmail": "shengrong.wu@pixocial.com",
        "invoicePdf": "https://pay.stripe.com/invoice/acct_1KR9XuHedDJPunHo/test_YWNjdF8xS1I5WHVIZWRESlB1bkhvLF9NN2VaeWF0cXlDUEs0VlFBeTk4OWF2UGQ3SElKYkJPLDQ5Mjg4NTg00200QyhUdZ9F/pdf?s=ap",
        "hostedInvoiceUrl": "https://invoice.stripe.com/i/acct_1KR9XuHedDJPunHo/test_YWNjdF8xS1I5WHVIZWRESlB1bkhvLF9NN2VaeWF0cXlDUEs0VlFBeTk4OWF2UGQ3SElKYkJPLDQ5Mjg4NTg00200QyhUdZ9F?s=ap",
        "paidAt": "0",
        "invoiceStatus": "open",
        // open状态的订单，可以 通过 hostedInvoiceUrl 打开账单地址完成支付
        "payPrice": "0",
        "payCurrency": "USD",
        "invoiceCreatedAt": "1658826086000"
      }
    ]
  },
  "message": "success"
}

```

## 获取用户商品购买优惠历史

作用：获取用户指定商品历史是否免费试用、是否付费过，当前是否处于宽限期。

- path: /v1/subscriber/{appuserid}/product/{productid}/history
- pathParam:
- Appuserid:  app用户id
- productid:  商品id
- Method: get
- Body: 无
- Response:

```json

{
  "code": 0,
  "data": {
    "productId": "price_1LGe1wHedDJPunHob19JriJl",
    "hasTrialed": 1,
    // 是否试用过
    "hasPaid": 1,
    // 是否付费过
    "inGracePeriod": 0
    // 当前是否在宽限期
  },
  "message": "success"
}

```

## 增加支付方式

作用：用于无支付添加支付方式，参考文档添加stripe支付方式

- path:/v1/stripe/paymentMethod/create
- Method: post
- Body:

```json
 {
  "appUserId": "{{appuserid}}",
  // 订阅者ID
  "type": "setupIntent",
  // 支持checkout和setupIntent模式，checkout返回跳转URL，需要跳转页面添加，setupIntent返回clientSecret,需要对接stripe js sdk
  "successUrl": "http://www.baidu.com?success",
  //如果是checkout模式，必填
  "cancelUrl": "http://www.baidu.com?cancel"
  //如果是checkout模式，必填
}
```

- Response:

```json
{
  "code": 0,
  "data": {
    "
    checkoutUrl
    ": "
    https:
    //checkout.stripe.com/pay/cs_test_c1RgAVGryEHuAkgCp7uu5vRPjB5tx0kQz8OMc663ZRqYwCmtmV6nWSDE0E#fidkdWxOYHwnPyd1blpxYHZxWjA0Tlc8XXBNYGFBT1Vwa01qQFNGdmA9TmlTTnU1SkZnNWJBfFZWX0tPQjBqalc0TU9yY0xMalZAfXFSbHJqX2REPEFBNGRBbkRKMGxXc2xjcUxiaHxKPUtmNTVRRkN%2FSnBmMCcpJ2N3amhWYHdzYHcnP3F3cGApJ2lkfGpwcVF8dWAnPyd2bGtiaWBaZmppcGhrJyknYGtkZ2lgVWlkZmBtamlhYHd2Jz9xd3BgeCUl",//如果是checkout模式，才有值
    ，
    需要跳转页面
    "checkoutId": "cs_test_c1RgAVGryEHuAkgCp7uu5vRPjB5tx0kQz8OMc663ZRqYwCmtmV6nWSDE0E",
    "setupIntentId": "seti_1LQne5HedDJPunHoLNgozUjU",
    "clientSecret": "seti_1LQne5HedDJPunHoLNgozUjU_secret_M95pS4k3ATxviQuFZrW8aPY60FrAR4p"
    //如果是setupIntent模式，才有值 ，需要用户前端调用js sdk 确认
  },
  "message": "success"
}
```

## 移除支付方式

作用：移除用户支付方式

- path:/v1/stripe/paymentMethod/remove
- Method: post
- Body:

```json
{
  "appUserId": "{{appuserid}}",
  // 订阅者ID
  "methodId": "pm_1LQneqHedDJPunHoLCaQBcWM"
  // 获取stripe支付方式 接口 列表的Id
}
```

- Response:

```json
 {
  "code": 0,
  "data": {
    "methodId": "pm_1LQneqHedDJPunHoLCaQBcWM"
  },
  "message": "success"
}
```
