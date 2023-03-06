---
sidebar_position: 5
title: 弹窗设置
id: 弹窗设置
---

## 获取弹窗列表

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

<Tabs>
  <TabItem value="Java" label="Java" default>

```Java
MarvelManager.getInstance().getPopup(countryCode, language, phrase, update, effectiveFilter, timezoneOffset, new AWHttpOriginalCallback() {
      @Override
      public void response(int code, String data) {

      }
});
```
  </TabItem>
  <TabItem value="Kotlin" label="Kotlin">

```Kotlin

MarvelManager.getInstance().getPopup(countryCode, language,phrase, update, effectiveFilter, timezoneOffset, object : AWHttpOriginalCallback{
      override fun response(code: Int, data: String?) {
      }
})
```
  </TabItem>
  <TabItem value="Objective-C" label="Objective-C">

```Objective-C 
[[AWPurchaseKit getMarvelManager] getPopupWithLanguage:language withCountryCode:countryCode withPhrase:phrase withUpdate:update withEffectiveFilter:effectFilter withTimezoneOffset:timezoneOffset withCompletion:^(NSInteger result, NSString * _Nonnull errorMsg, NSDictionary * _Nullable data) {
            
}];
```
  </TabItem>
  <TabItem value="Swift" label="Swift">

```Swift
AWPurchaseKit.getMarvelManager().getPopupWithLanguage(language, withCountryCode: countryCode, withPhrase: phrase, withUpdate: update, withEffectiveFilter: effectiveFilter, withTimezoneOffset: timezoneOffset) { result, errorMsg, data in
            
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
      "created_at": 1660730787,
      "device_level": 7,
      "number": 2,
      "popup_config": {
        "cancel_button": {
          "status": 2,
          "text": ""
        },
        "close_angle_mark": 1,
        "confirm_button": {
          "deeplink": "https://confirmButton",
          "status": 1,
          "text": "confirmButton"
        },
        "custom_config": [
          {
            "key": "1",
            "type": 1,
            "value": "2"
          },
          {
            "key": "22",
            "type": 4,
            "value": "https://gcs.beautyplus.com/e2447c74dda61b210d4030e21a3baf80.png"
          },
          {
            "key": "33",
            "type": 4,
            "value": "https://gcs.beautyplus.com/08e568ccf4d7134300a698cf2158d8fd.png"
          },
          {
            "key": "233",
            "type": 4,
            "value": "https://gcs.beautyplus.com/8726d07d5ce91ce8c7f9ed219dbaacca.png"
          }
        ],
        "deeplink": "https://baidu.com",
        "media": {
          "type": "pag",
          "url": "https://gcs.beautyplus.com/47e72087e662e68bdb4c4f04c58c95c9.pag"
        },
        "text": "081714",
        "text_two": "081714-2",
        "title": "081714"
      },
      "popup_type": 5,
      "rid": "BP_POP_00000005",
      "sub_status": 1,
      "trigger": {
        "cycle": 2,
        "frequency": 2
      },
      "trigger_type": 1,
      "updated_at": 1660730787,
      "user_status": 1,
      "weight": 2
    },
    {
      "created_at": 1660554325,
      "device_level": 7,
      "number": 2,
      "popup_config": {
        "cancel_button": {
          "status": 2,
          "text": ""
        },
        "close_angle_mark": 1,
        "confirm_button": {
          "deeplink": "",
          "status": 1,
          "text": ""
        },
        "custom_config": [
          {
            "key": "1",
            "type": 1,
            "value": "2"
          },
          {
            "key": "22",
            "type": 4,
            "value": "https://gcs.beautyplus.com/e2447c74dda61b210d4030e21a3baf80.png"
          },
          {
            "key": "33",
            "type": 4,
            "value": "https://gcs.beautyplus.com/08e568ccf4d7134300a698cf2158d8fd.png"
          },
          {
            "key": "233",
            "type": 4,
            "value": "https://gcs.beautyplus.com/8726d07d5ce91ce8c7f9ed219dbaacca.png"
          }
        ],
        "deeplink": "",
        "media": {
          "type": "pag",
          "url": "https://gcs.beautyplus.com/47e72087e662e68bdb4c4f04c58c95c9.pag"
        },
        "text": "",
        "text_two": "",
        "title": ""
      },
      "popup_type": 5,
      "rid": "BP_POP_00000001",
      "sub_status": 1,
      "trigger": {
        "cycle": 2,
        "frequency": 2
      },
      "trigger_type": 1,
      "updated_at": 1660730816,
      "user_status": 1,
      "weight": 2
    }
  ],
  "message": "success",
  "update": "faa8435d115b0b99d15ae7331263713b"
}
```

## 根据弹窗ID获取弹窗配置

<Tabs>
  <TabItem value="Java" label="Java" default>

```Java
MarvelManager.getInstance().getPopupPreview(rid, countryCode, language, new AWHttpOriginalCallback() {
                @Override
                public void response(int code, String data) {
                    
                }
            });
```
  </TabItem>
  <TabItem value="Kotlin" label="Kotlin">

```Kotlin

MarvelManager.getInstance().getPopupPreview(rid, countryCode, language, object : AWHttpOriginalCallback{
            override fun response(code: Int, data: String?) {
            }
        });
```
  </TabItem>
  <TabItem value="Objective-C" label="Objective-C">

```Objective-C 
[[AWPurchaseKit getMarvelManager] getPopupPreviewWithRid:rid WithLanguage:language withCountryCode:countryCode withCompletion:^(NSInteger result, NSString * _Nonnull errorMsg, NSDictionary * _Nullable data) {
            
    }];
```
  </TabItem>
  <TabItem value="Swift" label="Swift">

```Swift

AWPurchaseKit.getMarvelManager().getPopupPreview(withRid: rid, withLanguage: language, withCountryCode: countryCode){ result, errorMsg, data in
            
        }
```
  </TabItem>
</Tabs>

### 参数
- rid: 弹窗ID，例如：BP_POP_00000015
- language：语言
- countryCode：国家

### 返回
```Json
{
  "code": 0,
  "data": {
    "created_at": 1660730787,
    "device_level": 7,
    "number": 2,
    "popup_config": {
      "cancel_button": {
        "status": 2,
        "text": ""
      },
      "close_angle_mark": 1,
      "confirm_button": {
        "deeplink": "https://confirmButton",
        "status": 1,
        "text": "confirmButton"
      },
      "custom_config": [
        {
          "key": "1",
          "type": 1,
          "value": "2"
        },
        {
          "key": "22",
          "type": 4,
          "value": "https://gcs.beautyplus.com/e2447c74dda61b210d4030e21a3baf80.png"
        },
        {
          "key": "33",
          "type": 4,
          "value": "https://gcs.beautyplus.com/08e568ccf4d7134300a698cf2158d8fd.png"
        },
        {
          "key": "233",
          "type": 4,
          "value": "https://gcs.beautyplus.com/8726d07d5ce91ce8c7f9ed219dbaacca.png"
        }
      ],
      "deeplink": "https://baidu.com",
      "media": {
        "type": "pag",
        "url": "https://gcs.beautyplus.com/47e72087e662e68bdb4c4f04c58c95c9.pag"
      },
      "text": "081714",
      "text_two": "081714-2",
      "title": "081714"
    },
    "popup_type": 5,
    "rid": "BP_POP_00000005",
    "sub_status": 1,
    "trigger": {
      "cycle": 2,
      "frequency": 2
    },
    "trigger_type": 1,
    "updated_at": 1660730787,
    "user_status": 1,
    "weight": 2
  },
  "message": "success",
  "update": "057aba931fa3efb89c50cecc1e7dbbce"
}

```