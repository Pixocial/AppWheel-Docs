---
sidebar_position: 7
title: Banner配置
id: Banner配置
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
#import <AWMarvel/AWMarvel.h>
......
[[AWMarvelManager sharedInstance] getBannerWithLanguage:language withCountryCode:countryCode withPhrase:phrase withUpdate:update withAbcodes:abcodes withEffectiveFilter:effectiveFilter withTimezoneOffset:timezoneOffset withCompletion:^(NSInteger result, NSString * _Nonnull errorMsg, NSDictionary * _Nullable data) {
            
}];
```
  </TabItem>
  <TabItem value="Swift" label="Swift">

```Swift

#import <AWMarvel/AWMarvel.h>
......
AWMarvelManager.sharedInstance().getBannerWithLanguage(language, withCountryCode: countryCode, withPhrase: phrase, withUpdate: update, withAbcodes: abcodes, withEffectiveFilter: effectiveFilter, withTimezoneOffset: timezoneOffset) { result, errorMsg, data in
            
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

### 返回数据

<table style={{'min-width':'1200px'}}>
  <thead class="ant-table-thead">
    <tr>
      <th >名称</th><th >类型</th><th >是否必须</th><th >默认值</th><th >备注</th><th >其他信息</th>
    </tr>
  </thead><tbody className="ant-table-tbody"><tr ><td ><span ><span ></span> code</span></td><td ><span>number</span></td><td >必须</td><td ></td><td ><span ></span></td><td ></td></tr><tr ><td ><span ><span ></span> data</span></td><td ><span>object []</span></td><td >非必须</td><td ></td><td ><span ></span></td><td ><p ><span >item 类型: </span><span>object</span></p></td></tr><tr ><td ><span ><span >├─</span> rid</span></td><td ><span>string</span></td><td >必须</td><td ></td><td ><span >远程配置id	</span></td><td ></td></tr><tr ><td ><span ><span >├─</span> sub_status</span></td><td ><span>number</span></td><td >必须</td><td ></td><td ><span >订阅状态 1全部，2订阅中，3非订阅	</span></td><td ></td></tr><tr ><td ><span ><span >├─</span> user_status</span></td><td ><span>number</span></td><td >必须</td><td ></td><td ><span >用户状态 1全部，2新用户，3非新用户	</span></td><td ></td></tr><tr ><td ><span ><span >├─</span> position</span></td><td ><span>string</span></td><td >必须</td><td ></td><td ><span >位置 B+「top（默认）、second」 AB「HPB（默认）、HPBS、HPBL」</span></td><td ></td></tr><tr ><td ><span ><span >├─</span> text_layer</span></td><td ><span>string</span></td><td >必须</td><td ></td><td ><span >文字图层url</span></td><td ></td></tr><tr ><td ><span ><span >├─</span> deeplink</span></td><td ><span>string</span></td><td >必须</td><td ></td><td ><span ></span></td><td ></td></tr><tr ><td ><span ><span >├─</span> media</span></td><td ><span>object</span></td><td >必须</td><td ></td><td ><span >图片/视频</span></td><td ></td></tr><tr ><td ><span ><span >├─</span> type</span></td><td ><span>string</span></td><td >非必须</td><td ></td><td ><span >img ｜ video</span></td><td ></td></tr><tr ><td ><span ><span >├─</span> url</span></td><td ><span>string</span></td><td >非必须</td><td ></td><td ><span ></span></td><td ></td></tr><tr ><td ><span ><span >├─</span> same_using</span></td><td ><span>object</span></td><td >必须</td><td ></td><td ><span >拍同款</span></td><td ></td></tr><tr ><td ><span ><span >├─</span> using_music_id</span></td><td ><span>string</span></td><td >非必须</td><td ></td><td ><span >同款音乐素材id</span></td><td ></td></tr><tr ><td ><span ><span >├─</span> media</span></td><td ><span>object</span></td><td >非必须</td><td ></td><td ><span >目前都是视频</span></td><td ></td></tr><tr ><td ><span ><span >├─</span> type</span></td><td ><span>string</span></td><td >非必须</td><td ></td><td ><span >媒体类型 video</span></td><td ></td></tr><tr ><td ><span ><span >├─</span> url</span></td><td ><span>string</span></td><td >非必须</td><td ></td><td ><span >url</span></td><td ></td></tr><tr ><td ><span ><span >├─</span> desc</span></td><td ><span>string</span></td><td >非必须</td><td ></td><td ><span >描述</span></td><td ></td></tr><tr ><td ><span ><span >├─</span> relation_music_list</span></td><td ><span>string []</span></td><td >非必须</td><td ></td><td ><span >音乐素材id列表</span></td><td ><p ><span >item 类型: </span><span>string</span></p></td></tr><tr ><td ><span ><span >├─</span> </span></td><td ><span></span></td><td >非必须</td><td ></td><td ><span ></span></td><td ></td></tr><tr ><td ><span ><span >├─</span> status</span></td><td ><span>number</span></td><td >非必须</td><td ></td><td ><span >状态 1开启 2关闭</span></td><td ></td></tr><tr ><td ><span ><span >├─</span> order_no</span></td><td ><span>number</span></td><td >必须</td><td ></td><td ><span >排序值，大的在前，小的在后</span></td><td ></td></tr><tr ><td ><span ><span >├─</span> text_content</span></td><td ><span>object</span></td><td >必须</td><td ></td><td ><span >文字内容</span></td><td ></td></tr><tr ><td ><span ><span >├─</span> title</span></td><td ><span>string</span></td><td >必须</td><td ></td><td ><span ></span></td><td ></td></tr><tr ><td ><span ><span >├─</span> text</span></td><td ><span>string</span></td><td >必须</td><td ></td><td ><span ></span></td><td ></td></tr><tr ><td ><span ><span >├─</span> ended_at</span></td><td ><span>number</span></td><td >必须</td><td ></td><td ><span >结束时间，时间戳(秒)，为0时代表无结束时间</span></td><td ><p ><span >mock: </span><span>1637125199</span></p></td></tr><tr ><td ><span ><span >├─</span> abcode</span></td><td ><span>number</span></td><td >必须</td><td ></td><td ><span >abcode，未填时为0</span></td><td ><p ><span >mock: </span><span>0</span></p></td></tr><tr ><td ><span ><span ></span> message</span></td><td ><span>string</span></td><td >必须</td><td ></td><td ><span ></span></td><td ></td></tr><tr ><td ><span ><span ></span> update</span></td><td ><span>string</span></td><td >必须</td><td ></td><td ><span ></span></td><td ></td></tr>
               </tbody>
              </table>

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