---
title: 通知转发
id: forward_notifications
---

## 通知转发
### 通过AppWheel转发
为了实时同步订阅的变化，AppWheel需要接收来自iOS/Google应用商店和Stripe服务的通知，这些通知一般只能配置一个通知地址， 如果您想要将通知发送到您的服务器，则可以配置AppWheel将其转发到您指定的URL。

在AppWheel仪表板中，导航到[Project](https://dashboard.beta.appwheel.com/projects)>选择对应的项目>选择需要转发的App。向下滚动到`Push To Server URL`部分，在`Push To Server URL`中输入您服务器的URL，点击`Test`测试AppWheel能访问您的服务接口，点击右上角的“保存更改”。

![Push To Server URL](/img/tutorial/forward_notifications.png)


### Stripe配置多个通知地址
Stripe支持配置多个通知地址，因此除了通过AppWheel转发通知外，还可以在Stripe后台配置自定义通知类型到您的服务。

打开Stripe后台[Webhooks配置](https://dashboard.stripe.com/test/webhooks)。

添加新端
![Webhooks配置](/img/tutorial/stripe_webhooks.png)


填写接收通知地址，和选择需要接收的通知类型。

![Webhooks配置地址](/img/tutorial/stripe_webhook_url.png)


复制对应的通知密钥签名，保存到你的服务中用来校验通知是Stripe发出的

![Webhooks配置地址](/img/tutorial/stripe_webhook_sec.png)
