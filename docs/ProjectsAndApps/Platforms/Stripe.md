---
sidebar_position: 2
title: Stripe
id: stripe
---

本文档指引如何在AppWheel管理后端添加Stripe配置。

## 获取Stripe配置

**为了支持Stripe支付，您必须拥有自己的Stripe账户，并在AppWheel中填写相关信息。**

**创建Stripe账号参考[Stripe 账户](https://stripe.com/docs/account)。**

### 1.1 从[Stripe管理后台](https://dashboard.stripe.com/apikeys)获取API秘钥

![1-1](/img/stripePayments/apikey-en.png)

### 1.2 在AppWheel后台添加Stripe应用。

App ID 填写参考[文档](https://meitu.feishu.cn/docs/doccnYsh95qRWxMee5F2CyACC2f)。

使用从Stripe后端获得的密钥填充AppWheel。

![1-2](/img/stripePayments/create_apps_02.png)

### 1.3  Stripe 通知配置

![1-3](/img/stripePayments/create_apps_03.png)

复制WebHook URL，在Stripe中创建WebHook，并在AppWheel和WebHook中回填密钥签名。

![create_webhook](/img/stripePayments/create_webhook.png)

![1-4](/img/stripePayments/webhooks-en.png)
至少勾选以下事件：

- charge.refunded
- customer.subscription.created
- customer.subscription.deleted
- customer.subscription.updated
- invoice.finalized
- invoice.payment_succeeded

**为了完成购买，需要配置SKU和权益，请参考[权益和产品](/ProjectsAndApps/Entitlements/)**

