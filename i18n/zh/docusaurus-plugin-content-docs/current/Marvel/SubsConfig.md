---
sidebar_position: 1
title: 订阅管理
id: 订阅管理
---


import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

<Tabs>
  <TabItem value="Java" label="Java" default>

```Java
MarvelManager.getInstance().getNewSubs(countryCode, language, phrase, update, effectiveFilter, timezoneOffset, new AWHttpOriginalCallback() {
                @Override
                public void response(int code, String data) {

                }
            });
```
  </TabItem>
  <TabItem value="Kotlin" label="Kotlin">

```Kotlin

MarvelManager.getInstance().getNewSubs(countryCode, language, phrase, update, effectiveFilter, timezoneOffset, object : AWHttpOriginalCallback{
            override fun response(code: Int, data: String?) {
            }
        });
```
  </TabItem>
  <TabItem value="Objective-C" label="Objective-C">

```Objective-C 
[[AWPurchaseKit getMarvelManager] getNewSubsWithLanguage:language withCountryCode:countryCode withPhrase:phrase withUpdate:update withEffectiveFilter:effectiveFilter withTimezoneOffset:timezoneOffset withCompletion:^(NSInteger result, NSString * _Nonnull errorMsg, NSDictionary * _Nullable data) {
            
    }];
```
  </TabItem>
  <TabItem value="Swift" label="Swift">

```Swift
AWPurchaseKit.getMarvelManager().getNewSubs(withLanguage:language, withCountryCode: countryCode, withPhrase: phrase, withUpdate: update, withEffectiveFilter: effectiveFilter, withTimezoneOffset: timezoneOffset) { result, errorMsg, data in
            
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
    "activity": [],
    "daily": [],
    "promotion": [
      {
        "bac_pic": "",
        "banner": "",
        "cont_color": "",
        "content": [
          {
            "class_info": "",
            "cont_text": "",
            "picture": "https://gcs.beautyplus.com/eb4822eecd46e1b24fd4ceceb0eb9254.gif"
          },
          {
            "class_info": "",
            "cont_text": "",
            "picture": "https://gcs.beautyplus.com/393620a7ab1b42f9864903c84b6ed823.gif"
          },
          {
            "class_info": "",
            "cont_text": "",
            "picture": "https://gcs.beautyplus.com/6cbc76c95b7dab5eb745d358f2f37bd6.gif"
          }
        ],
        "countdown": {
          "countdown_color": "",
          "end_time": 1661054399,
          "start_time": 1660060800,
          "status": 1
        },
        "describe_color": "",
        "describe_copy": "",
        "eff_status": 1,
        "end_ed": 0,
        "highlight": "",
        "home_ent": "",
        "id": 0,
        "img_background": "",
        "lifetime": {
          "button_copy": "",
          "describe": "",
          "discount": 0,
          "free_days": 0,
          "mark": "",
          "product_id": "",
          "status": 0
        },
        "month": {
          "button_copy": "",
          "describe": "",
          "discount": 0,
          "free_days": 0,
          "mark": "",
          "product_id": "",
          "status": 0
        },
        "mtg_id": "BP_SUB_00000002",
        "name": "",
        "quarter": {
          "button_copy": "",
          "describe": "",
          "discount": 0,
          "free_days": 0,
          "mark": "",
          "product_id": "",
          "status": 0
        },
        "setting_entry": "",
        "shoot": "",
        "start_ed": 0,
        "sub_blacolor": "",
        "sub_color": "",
        "titleo_color": "",
        "titleo_cont": "",
        "titlet_color": "",
        "titlet_cont": "",
        "video_background": "",
        "week": {
          "button_copy": "",
          "describe": "",
          "discount": 0,
          "free_days": 0,
          "mark": "",
          "product_id": "",
          "status": 0
        },
        "year": {
          "button_copy": "",
          "describe": "",
          "discount": 0,
          "free_days": 0,
          "mark": "",
          "product_id": "",
          "status": 0
        }
      }
    ]
  },
  "message": "success",
  "update": ""
}

```