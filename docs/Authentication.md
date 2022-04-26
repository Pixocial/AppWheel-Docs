---
sidebar_position: 1
title: Authentication
id: Authentication
---

在调用接口时，需要进行接口签名，以保证数据安全。


Authorization Header


|  Error Code | explanation  | Suggestions|
| Authorization | 最终签名的结果 | 包含“Signature ”前缀 |
| X-Request-Timestamp | 时间| 60s有效期，服务端会进行校验是否过期 |
| X-Request-Nonce | 随机数 | 可以是任意随机字符串，建议使用uuid |
| X-Request-Uri | Uri | 包含query |
| X-Request-AppId | appId | 后端用于检索access_secret 秘钥，校验签名使用 |