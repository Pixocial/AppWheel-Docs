---
title: App Store Server API
id: ios-server-api
---

## App Store Server API
[官网](https://developer.apple.com/documentation/appstoreserverapi)
App Store Server API 是一种 REST API，您可以从服务器调用它来请求和提供有关客户应用内购买的信息。App Store 使用JSON Web 签名 (JWS)规范对该 API 返回的交易和订阅续订信息进行签名。

App Store Server API 独立于应用程序在客户设备上的安装状态。App Store 服务器根据客户的应用内购买历史记录返回信息，无论客户是否在其设备上安装、删除或重新安装该应用。

要使用此 API 请求交易和订阅状态信息，请提供属于客户的任何原始交易标识符。交易历史 API 以完整的交易列表响应，一次 20 个，从最早的开始。订阅状态 API 返回所有客户订阅的状态，按订阅组标识符组织。

在您收到 App Store 服务器通知后，当客户要求为应用内消费品购买退款时，使用发送消费信息端点向App Store 发送信息。您的数据有助于做出退款决定。

## AppWheel 配置和作用
### 配置生成
[官方文档地址](https://developer.apple.com/documentation/appstoreserverapi/creating_api_keys_to_use_with_the_app_store_server_api)
#### 生成私钥
要生成密钥，您必须在 App Store Connect 中具有管理员角色或帐户持有人角色。您可以生成多个 API 密钥。要生成用于 App Store Server API 的 API 密钥，请登录App Store Connect并完成以下步骤：

选择用户和访问，然后选择密钥选项卡。

在密钥类型下选择应用内购买。

单击生成 API 密钥或添加 (+) 按钮。

输入密钥的名称。该名称仅供您参考，不是密钥本身的一部分。

单击生成。

新密钥的名称、密钥 ID、下载链接和其他信息会显示在页面上。

#### 下载并存储私钥
生成 API 密钥后，App Store Connect 让您有机会下载密钥的私有部分。私钥只能下载一次。

登录App Store Connect。

选择用户和访问，然后选择密钥选项卡。

在密钥类型下选择应用内购买。

单击新 API 密钥旁边的下载 API 密钥。

仅当您尚未下载私钥时才会显示下载链接。Apple 不保留私钥的副本。将您的私钥存储在安全的地方。
#### 配置到以下页面
![App Store Server API](/img/tutorial/iosserverapi.png)


### IOSGetTransactionHistory 获取历史交易信息 
ref: https://developer.apple.com/documentation/appstoreserverapi/get_transaction_history

### IOSGetRefundHistory 获取退款历史记录
ref: https://developer.apple.com/documentation/appstoreserverapi/get_refund_history
