---
sidebar_position: 7
title: banner配置
id: banner配置
---


import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

<Tabs>
  <TabItem value="Java" label="Java" default>

```Java
MarvelManager.getInstance().getBanner(countryCode, language, abcodes, phrase, update, effectiveFilter, timezoneOffset, new AWHttpOriginalCallback() {
                @Override
                public void response(int code, String data) {
                    
                }
            });
///Remove listener
UserOrderManager.getProvider().removePurchaseObserver(orderObserver);
```
  </TabItem>
  <TabItem value="Kotlin" label="Kotlin">

```Kotlin

MarvelManager.getInstance().getBanner(countryCode, language, abcodes,phrase, update, effectiveFilter, timezoneOffset, object : AWHttpOriginalCallback{
    override fun response(code: Int, data: String?) {
    }
})
```
  </TabItem>
  <TabItem value="Objective-C" label="Objective-C">

```Objective-C 
[[AWPurchaseKit getMarvelManager] getBannerWithLanguage:language withCountryCode:countryCode withPhrase:phrase withUpdate:update withAbcodes:abcodes withEffectiveFilter:effectiveFilter withTimezoneOffset:timezoneOffset withCompletion:^(NSInteger result, NSString * _Nonnull errorMsg, NSDictionary * _Nullable data) {
            
    }];
```
  </TabItem>
  <TabItem value="Swift" label="Swift">

```Swift

AWPurchaseKit.getMarvelManager().getBannerWithLanguage(language, withCountryCode: countryCode, withPhrase: phrase, withUpdate: update, withAbcodes: abcodes, withEffectiveFilter: effectiveFilter, withTimezoneOffset: timezoneOffset) { result, errorMsg, data in
            
        }
```
  </TabItem>
</Tabs>

### 参数
- language：语言
- countryCode：国家
- phrase： 预发布密码（可空）
- update: 当前MD5值（可空）
- abcodes： abcode多个按逗号分隔(,)
- effectiveFilter： 传1新时区逻辑，不传为旧逻辑 （可空）
- timezoneOffset： 用户时区偏移值，分钟为单位，服务端将根据该值计算用户时区的数据，可替代effective_filter，此时不会进入effective_filter逻辑（可空）

### 返回
```Json
{
  "code": 0,
  "data": [
    {
      "deeplink": "11111",
      "effective_time": {
        "status": 2
      },
      "media": {
        "type": "img",
        "url": "https://gcs-airvid.meitu.com/27696587407b910a36b523b024969858.jpeg"
      },
      "position": "HPBL",
      "rid": "AW_BAN_00000019",
      "same_using": {
        "desc": "ddd",
        "media": {
          "type": "fdafdf",
          "url": "https://gcs-airvid.meitu.com/27696587407b910a36b523b024969858.jpeg"
        },
        "relation_music_list": [
          "fdfd",
          "fdafsaf"
        ],
        "status": 1
      },
      "sub_status": 1,
      "text_content": {
        "text": "dddd",
        "title": "dddd"
      },
      "text_layer": "dfdfdf",
      "user_status": 1
    },
    {
      "deeplink": "11111",
      "effective_time": {
        "status": 2
      },
      "media": {
        "type": "img",
        "url": "https://gcs-airvid.meitu.com/27696587407b910a36b523b024969858.jpeg"
      },
      "position": "HPBL",
      "rid": "AW_BAN_00000018",
      "same_using": {
        "desc": "ddd",
        "media": {
          "type": "fdafdf",
          "url": "https://gcs-airvid.meitu.com/27696587407b910a36b523b024969858.jpeg"
        },
        "relation_music_list": [
          "fdfd",
          "fdafsaf"
        ],
        "status": 1
      },
      "sub_status": 1,
      "text_content": {
        "text": "dddd",
        "title": "dddd"
      },
      "text_layer": "dfdfdf",
      "user_status": 1
    },
    {
      "deeplink": "11111",
      "effective_time": {
        "status": 2
      },
      "media": {
        "type": "img",
        "url": "https://gcs-airvid.meitu.com/27696587407b910a36b523b024969858.jpeg"
      },
      "position": "HPBL",
      "rid": "AW_BAN_00000016",
      "same_using": {
        "desc": "ddd",
        "media": {
          "type": "fdafdf",
          "url": "https://gcs-airvid.meitu.com/27696587407b910a36b523b024969858.jpeg"
        },
        "relation_music_list": [
          "fdfd",
          "fdafsaf"
        ],
        "status": 1
      },
      "sub_status": 1,
      "text_content": {
        "text": "dddd",
        "title": "dddd"
      },
      "text_layer": "dfdfdf",
      "user_status": 1
    }
  ],
  "message": "success",
  "update": "0560e5ea1c13a686801d2683d92bdb33"
}

```