---
sidebar_position: 3
title: 产品配置
id: 产品配置
---


import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

<Tabs>
  <TabItem value="Java" label="Java" default>

```Java

MarvelManager.getInstance().getProductConfig(countryCode, language, phrase, update, effectiveFilter, timezoneOffset, new AWHttpOriginalCallback() {
    @Override
    public void response(int code, String data) {

    }
});
```
  </TabItem>
  <TabItem value="Kotlin" label="Kotlin">

```Kotlin
MarvelManager.getInstance().getProductConfig(countryCode, language, phrase, update, effectiveFilter, timezoneOffset, object : AWHttpOriginalCallback{
      override fun response(code: Int, data: String?) {
      }
});
```
  </TabItem>
  <TabItem value="Objective-C" label="Objective-C">

```Objective-C 
[[AWPurchaseKit getMarvelManager] getProductConfigWithLanguage:language withCountryCode:countryCode withPhrase:phrase withUpdate:update withEffectiveFilter:effectiveFilter withTimezoneOffset:timezoneOffset withCompletion:^(NSInteger result, NSString * _Nonnull errorMsg, NSDictionary * _Nullable data) {
        
}];
```
  </TabItem>
  <TabItem value="Swift" label="Swift">

```Swift
AWPurchaseKit.getMarvelManager().getProductConfig(withLanguage:language, withCountryCode: countryCode, withPhrase: phrase, withUpdate: update, withEffectiveFilter: effectiveFilter, withTimezoneOffset: timezoneOffset) { result, errorMsg, data in
            
}
```
  </TabItem>
</Tabs>


### 参数
- language：语言
- countryCode：国家
- phrase： 预发布密码（可空）
- update: 当前MD5值（可空）
- effectiveFilter： 传1新时区逻辑，不传为旧逻辑 （可空）
- timezoneOffset： 用户时区偏移值，分钟为单位，服务端将根据该值计算用户时区的数据，可替代effective_filter，此时不会进入effective_filter逻辑（可空）

### 返回
```Json
{
  "code": 0,
  "data": {
    "rid": "BP_CON_00000049",
    "sub_status": 1,
    "user_status": 1,
    "device_level": 1,
    "p_protocol": "",
    "u_protocol": "",
    "p_trigger": 1,
    "u_trigger": 1,
    "cus_config": [
      {
        "key": "",
        "type": 1,
        "value": ""
      }
    ],
    "created_at": 1660817040,
    "updated_at": 1660817040,
    "ended_at": 0
  },
  "message": "success",
  "update": "2c6456f5464e9c41677c4eb0919f9e23"
}

```