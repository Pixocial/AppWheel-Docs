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

#import <AWMarvel/AWMarvel.h>
......
[[AWMarvelManager sharedInstance] getPopupWithLanguage:language withCountryCode:countryCode withPhrase:phrase withUpdate:update withEffectiveFilter:effectFilter withTimezoneOffset:timezoneOffset withCompletion:^(NSInteger result, NSString * _Nonnull errorMsg, NSDictionary * _Nullable data) {
            
}];
```
  </TabItem>
  <TabItem value="Swift" label="Swift">

```Swift

#import <AWMarvel/AWMarvel.h>
......
AWMarvelManager.sharedInstance().getPopupWithLanguage(language, withCountryCode: countryCode, withPhrase: phrase, withUpdate: update, withEffectiveFilter: effectiveFilter, withTimezoneOffset: timezoneOffset) { result, errorMsg, data in
            
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

### 返回数据

<table style={{'min-width':'1200px'}}>
  <thead class="ant-table-thead">
    <tr>
      <th >名称</th><th >类型</th><th >是否必须</th><th >默认值</th><th >备注</th><th >其他信息</th>
    </tr>
  </thead><tbody className="ant-table-tbody"><tr ><td ><span ><span ></span> code</span></td><td ><span>number</span></td><td >非必须</td><td ></td><td ><span >0成功 其他失败</span></td><td ><p ><span >mock: </span><span>0</span></p></td></tr><tr ><td ><span ><span ></span> data</span></td><td ><span>object []</span></td><td >非必须</td><td ></td><td ><span >成功是必填，失败时无data</span></td><td ><p ><span >item 类型: </span><span>object</span></p></td></tr><tr ><td ><span ><span >├─</span> rid</span></td><td ><span>string</span></td><td >必须</td><td ></td><td ><span >远程配置id</span></td><td ></td></tr><tr ><td ><span ><span >├─</span> sub_status</span></td><td ><span>number</span></td><td >必须</td><td ></td><td ><span >订阅状态 1全部，2订阅中，3非订阅</span></td><td ></td></tr><tr ><td ><span ><span >├─</span> user_status</span></td><td ><span>number</span></td><td >必须</td><td ></td><td ><span >用户状态 1全部，2新用户，3非新用户</span></td><td ></td></tr><tr ><td ><span ><span >├─</span> device_level</span></td><td ><span>number</span></td><td >必须</td><td ></td><td ><span >机型等级 1低端，2中端，4高端，多选则相加，过滤&操作</span></td><td ></td></tr><tr ><td ><span ><span >├─</span> weight</span></td><td ><span>number</span></td><td >必须</td><td ></td><td ><span >权重</span></td><td ></td></tr><tr ><td ><span ><span >├─</span> number</span></td><td ><span>number</span></td><td >必须</td><td ></td><td ><span >次数（新接入的客户端废除此参数，改用trigger下的参数）</span></td><td ></td></tr><tr ><td ><span ><span >├─</span> trigger_type</span></td><td ><span>number</span></td><td >必须</td><td ></td><td ><span >触发时机 1首页，2编辑页，3自拍页，4保存页，5分享页 6 限时免费 7 强制升级</span></td><td ></td></tr><tr ><td ><span ><span >├─</span> popup_type</span></td><td ><span>number</span></td><td >必须</td><td ></td><td ><span >弹窗类型 1文字，2图文，3图片/视频，4反馈	5 pag</span></td><td ></td></tr><tr ><td ><span ><span >├─</span> popup_config</span></td><td ><span>object</span></td><td >必须</td><td ></td><td ><span >弹窗配置</span></td><td ></td></tr><tr ><td ><span ><span >├─</span> title</span></td><td ><span>string</span></td><td >非必须</td><td ></td><td ><span >标题</span></td><td ></td></tr><tr ><td ><span ><span >├─</span> text</span></td><td ><span>string</span></td><td >非必须</td><td ></td><td ><span >文案</span></td><td ></td></tr><tr ><td ><span ><span >├─</span> text_two</span></td><td ><span>string</span></td><td >非必须</td><td ></td><td ><span >文案二 弹窗类型为1时使用，目前b+用到</span></td><td ></td></tr><tr ><td ><span ><span >├─</span> confirm_button</span></td><td ><span>object</span></td><td >非必须</td><td ></td><td ><span >确认按钮 弹窗类型为1，2，3时使用，部分app未用请忽略</span></td><td ></td></tr><tr ><td ><span ><span >├─</span> text</span></td><td ><span>string</span></td><td >非必须</td><td ></td><td ><span >文案</span></td><td ></td></tr><tr ><td ><span ><span >├─</span> deeplink</span></td><td ><span>string</span></td><td >非必须</td><td ></td><td ><span ></span></td><td ></td></tr><tr ><td ><span ><span >├─</span> status</span></td><td ><span>number</span></td><td >非必须</td><td ></td><td ><span >1开启 2关闭</span></td><td ></td></tr><tr ><td ><span ><span >├─</span> cancel_button</span></td><td ><span>object</span></td><td >非必须</td><td ></td><td ><span >取消按钮 确认按钮 弹窗类型为1，2，3时使用，部分app未用请忽略</span></td><td ></td></tr><tr ><td ><span ><span >├─</span> text</span></td><td ><span>string</span></td><td >非必须</td><td ></td><td ><span >文案</span></td><td ></td></tr><tr ><td ><span ><span >├─</span> status</span></td><td ><span>number</span></td><td >非必须</td><td ></td><td ><span >1开启2关闭</span></td><td ></td></tr><tr ><td ><span ><span >├─</span> close_angle_mark</span></td><td ><span>number</span></td><td >非必须</td><td ></td><td ><span >关闭角标 1开启 2关闭，部分app未用请忽略</span></td><td ></td></tr><tr ><td ><span ><span >├─</span> media</span></td><td ><span>object</span></td><td >非必须</td><td ></td><td ><span >媒体素材，图片|视频，弹窗类型2，3，5时使用</span></td><td ></td></tr><tr ><td ><span ><span >├─</span> type</span></td><td ><span>string</span></td><td >非必须</td><td ></td><td ><span >类型，img｜video ｜ pag</span></td><td ></td></tr><tr ><td ><span ><span >├─</span> url</span></td><td ><span>string</span></td><td >非必须</td><td ></td><td ><span >地址</span></td><td ></td></tr><tr ><td ><span ><span >├─</span> deeplink</span></td><td ><span>string</span></td><td >非必须</td><td ></td><td ><span >弹窗类型3时使用</span></td><td ></td></tr><tr ><td ><span ><span >├─</span> custom_config</span></td><td ><span>object []</span></td><td >必须</td><td ></td><td ><span >自定义配置</span></td><td ><p ><span >item 类型: </span><span>object</span></p></td></tr><tr ><td ><span ><span >├─</span> type</span></td><td ><span>number</span></td><td >必须</td><td ></td><td ><span >1文案(字符串) 2数字 3 bool 4 图片
注意弹窗中目前只有1，4两个类型</span></td><td ></td></tr><tr ><td ><span ><span >├─</span> key</span></td><td ><span>string</span></td><td >必须</td><td ></td><td ><span >key</span></td><td ></td></tr><tr ><td ><span ><span >├─</span> value</span></td><td ><span>可变类型</span></td><td >必须</td><td ></td><td ><span >value的数据类型根据type变化
str：1，4
bool：3
number：2</span></td><td ></td></tr><tr ><td ><span ><span >├─</span> popup_button_title</span></td><td ><span>string</span></td><td >非必须</td><td ></td><td ><span >弹窗限时免费 popup_button_title</span></td><td ></td></tr><tr ><td ><span ><span >├─</span> popup_message</span></td><td ><span>string</span></td><td >非必须</td><td ></td><td ><span >弹窗限时免费 popup_message</span></td><td ></td></tr><tr ><td ><span ><span >├─</span> popup_title</span></td><td ><span>string</span></td><td >非必须</td><td ></td><td ><span >弹窗限时免费 popup_title</span></td><td ></td></tr><tr ><td ><span ><span >├─</span> created_at</span></td><td ><span>number</span></td><td >必须</td><td ></td><td ><span >创建时间，时间戳(秒)</span></td><td ></td></tr><tr ><td ><span ><span >├─</span> ended_at</span></td><td ><span>number</span></td><td >必须</td><td ></td><td ><span >结束时间，时间戳(秒)，为0时代表无结束时间</span></td><td ></td></tr><tr ><td ><span ><span >├─</span> updated_at</span></td><td ><span>number</span></td><td >必须</td><td ></td><td ><span >更新时间，时间戳(秒)</span></td><td ></td></tr><tr ><td ><span ><span >├─</span> trigger</span></td><td ><span>object</span></td><td >必须</td><td ></td><td ><span >频率</span></td><td ></td></tr><tr ><td ><span ><span >├─</span> frequency</span></td><td ><span>number</span></td><td >必须</td><td ></td><td ><span >频率次数</span></td><td ></td></tr><tr ><td ><span ><span >├─</span> cycle</span></td><td ><span>number</span></td><td >必须</td><td ></td><td ><span >频率周期:1天、2周、3月、4年</span></td><td ></td></tr><tr ><td ><span ><span >├─</span> feature_name</span></td><td ><span>string</span></td><td >必须</td><td ></td><td ><span >弹窗限时免费 feature_name</span></td><td ></td></tr><tr ><td ><span ><span ></span> message</span></td><td ><span>string</span></td><td >非必须</td><td ></td><td ><span ></span></td><td ></td></tr><tr ><td ><span ><span ></span> update</span></td><td ><span>string</span></td><td >必须</td><td ></td><td ><span >数据的md5值</span></td><td ></td></tr>
               </tbody>
              </table>

### Example
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
[[AWMarvelManager sharedInstance] getPopupPreviewWithRid:rid WithLanguage:language withCountryCode:countryCode withCompletion:^(NSInteger result, NSString * _Nonnull errorMsg, NSDictionary * _Nullable data) {
            
    }];
```
  </TabItem>
  <TabItem value="Swift" label="Swift">

```Swift

AWMarvelManager.sharedInstance().getPopupPreview(withRid: rid, withLanguage: language, withCountryCode: countryCode){ result, errorMsg, data in
            
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