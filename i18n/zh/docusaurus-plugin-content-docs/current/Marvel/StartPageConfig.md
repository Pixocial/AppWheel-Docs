---
sidebar_position: 2
title: 开屏管理
id: 开屏管理
---


import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

<Tabs>
  <TabItem value="Java" label="Java" default>

```Java
MarvelManager.getInstance().getStartPage(countryCode, language, phrase, update, effectiveFilter, timezoneOffset, new AWHttpOriginalCallback() {
      @Override
      public void response(int code, String data) {

      }
});
```
  </TabItem>
  <TabItem value="Kotlin" label="Kotlin">

```Kotlin

MarvelManager.getInstance().getStartPage(countryCode, language, phrase, update, effectiveFilter, timezoneOffset, object : AWHttpOriginalCallback{
      override fun response(code: Int, data: String?) {
      }
});
```
  </TabItem>
  <TabItem value="Objective-C" label="Objective-C">

```Objective-C 
[[AWPurchaseKit getMarvelManager] getStartPageWithLanguage:language withCountryCode:countryCode withPhrase:phrase withUpdate:update withEffectiveFilter:effectiveFilter withTimezoneOffset:timezoneOffset withCompletion:^(NSInteger result, NSString * _Nonnull errorMsg, NSDictionary * _Nullable data) {
            
}];
```
  </TabItem>
  <TabItem value="Swift" label="Swift">

```Swift

AWPurchaseKit.getMarvelManager().getStartPage(withLanguage:language, withCountryCode: countryCode, withPhrase: phrase, withUpdate: update, withEffectiveFilter: effectiveFilter, withTimezoneOffset: timezoneOffset) { result, errorMsg, data in
            
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
  "data": [
    {
      "rid": "BP_SPL_00000001",
      "sub_status": 1,
      "user_status": 1,
      "device_level": 1,
      "weight": 10,
      "number": 20,
      "duration": 3,
      "text_layer": "",
      "media": {
        "type": "video",
        "url": "https://gcs-vcus.meitu.com/517e6a76a24348d15c8111f23402b82a.mp4"
      },
      "deeplink": "beautyplusstory://p_camera/m_selfie?type=facial&strength=100",
      "ended_at": 0,
      "trigger": {
        "cycle": 1,
        "frequency": 1
      }
    }
  ],
  "message": "success",
  "update": "64ac1de2df75a1399cd60c9aaf5ced05"
}

```
