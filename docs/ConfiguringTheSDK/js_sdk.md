---
sidebar_position: 1
title: JS SDK
id: js_sdk
---
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

在调用接口时，需要进行接口签名，以保证数据安全。



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
