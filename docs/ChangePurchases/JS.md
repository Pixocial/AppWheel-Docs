---
sidebar_position: 1
title: Stripe
id: stripe_change
---

## 更换套餐

Stripe 支持更改现有订阅，而无需取消和重新创建它们。

## 关于计费
当更换套餐时，总是会重新计算收费决定用户是否需要立即补差价
- 从低级套餐升级到高级套餐时，需要立即扣费并补差价；
- 从不需要付费的订阅（例如，由于试用或免费订阅）到付费订阅；
- 当计费周期改变时，如从月订升级到年订，通常伴随着费用的增加；


import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

<Tabs>
  <TabItem value="javascript" label="javascript">

```javascript
// See your keys here: https://dashboard.appwheel.com/projects/ and select app
const appwheel = new AppWheel("{App ID}", "{platfrom}", "App Secret")
appwheel.updatePurchase({
    "appUserId": "appuserid", // 必填 app用户
    "productId": "price_xxx", // 选填 ，新的 project id
    "purchaseId": "sub_xxx" //必填 订阅订单id ，通过获取当前订阅权益 接口获取到的originalTransactionId
}).then(res => res.json()).then(json => console.log(json))

```
  </TabItem>
</Tabs>

### 参数

- appUserId: 必填， app用户id
- productId: 必填 ，新的 project id
- purchaseId: 必填， 订阅订单id ，通过获取当前订阅权益 接口获取到的originalTransactionId

### 返回

```json
{
  "code":200,
  "data":{
  "hostedInvoiceUrl": "https://payment.stripe.com/******" // 升级如果需要补差价，那么就会有值，否则升级成功
    }
}

```

### 升级付款页面

![升级](/img/stripePayments/update_sub_pay.png)


## 取消订阅
可以通过Api取消订阅的续订状态，订阅不会立即结束，而是在订阅当前计费周期到期时结束。
取消续订状态的订阅，将不会产生新的费用。

<Tabs>
<TabItem value="javascript" label="javascript">

```javascript
// See your keys here: https://dashboard.appwheel.com/projects/ and select app
const appwheel = new AppWheel("{App ID}", "{platfrom}", "App Secret")
appwheel.cancelPurchase({
    "appUserId": "appuserid", // 必填 app用户
    "purchaseId": "sub_xxx" //必填 订阅订单id ，通过获取当前订阅权益 接口获取到的originalTransactionId
}).then(res => res.json()).then(json => console.log(json))

```
  </TabItem>
</Tabs>

### 参数

- appUserId: 必填， app用户id
- purchaseId: 必填， 订阅订单id ，通过获取当前订阅权益 接口获取到的originalTransactionId

### 返回

```json
{
  "code":200,
  "data":{
    }
}

```


## 重新续订
对于已经取消续订状态但是当前计费周期未到期的订阅，可以重新续订，订阅将恢复，并在下个周期开始收费。

已经结束的订阅不支持重新续订，需要创建订阅。


<Tabs>
<TabItem value="javascript" label="javascript">

```javascript
// See your keys here: https://dashboard.appwheel.com/projects/ and select app
const appwheel = new AppWheel("{App ID}", "{platfrom}", "App Secret")
appwheel.renewPurchase({
    "appUserId": "appuserid", // 必填 app用户
    "purchaseId": "sub_xxx" //必填 订阅订单id ，通过获取当前订阅权益 接口获取到的originalTransactionId
}).then(res => res.json()).then(json => console.log(json))

```
  </TabItem>
</Tabs>

### 参数

- appUserId: 必填， app用户id
- purchaseId: 必填， 订阅订单id ，通过获取当前订阅权益 接口获取到的originalTransactionId

### 返回

```json
{
  "code":200,
  "data":{
    }
}

```


## 退款
目前AppWheel不支持直接通过Api退款，需要在Stripe后台操作。