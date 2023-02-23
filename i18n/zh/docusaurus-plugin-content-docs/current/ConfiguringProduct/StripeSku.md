---
sidebar_position: 1
title: Stripe商品配置
id: stripe-sku
---

# Stripe 商品配置

## 在Stripe后台配置产品和价格

在Stripe中添加产品价格并复制价格代码

![2-1](/img/stripePayments/pricing-en.png)

## 在AppWheel中添加Sku

要通过AppWheel完成购买，必须首先添加SKU。
您必须使用从Stripe复制的价格填写价格ID，否则您将无法继续下一步购买订阅。

![2-3](/img/stripePayments/create_sku.png)

## 在AppWheel中添加权利

对于AppWheel，建议使用权限映射SKU和用户权限之间的关系；例如，按月付款的计划和按年付款的计划对应于相同的会员权益。
**同时，您可以在相同权限下在应用程序中交叉查询订单，从而可以根据需要进行跨终端购买。**

[Read More](/ConfiguringProduct/entitlements)
