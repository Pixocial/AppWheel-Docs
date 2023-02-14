---
sidebar_position: 1
title: Authentication
id: Authentication
---
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

在调用接口时，需要进行接口签名，以保证数据安全。



<Tabs>
  <TabItem value="Javascript" label="Javascript">

```Javascript
var CryptoJS = require("cryptojs")

var AppWheel = function (appid, platfrom, accessKey) {
    this.appid = appid
    this.platform = platfrom
    this.accessKey = accessKey
}
AppWheel.prototype.sign = function (date, tm, nonce, method, uri, data) {

    let strToSign = tm + "\n" + nonce + "\n" + method + " " + uri + "\n"
    if (method !== "GET") {
        let payloadHash = CryptoJS.MD5(data).toString()
        strToSign += payloadHash;
    }
    strToSign = strToSign.toLowerCase()
    let app_id = this.appid
    let secret = this.accessKey
    let platform = this.platform
    let sign = CryptoJS.HmacSHA256(strToSign.toLowerCase(), secret);
    sign = "Signature " + CryptoJS.enc.Hex.stringify(sign);

    return {
        "X-Request-AppId": app_id.toString(),
        "X-Request-Platform": platform,
        "X-Request-Nonce": nonce,
        "X-Request-Uri": uri,
        "X-Request-Timestamp": tm,
        "Authorization": sign,
    }
}

```

</TabItem>
</Tabs>

