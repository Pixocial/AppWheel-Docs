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

### 返回数据

<table style={{'min-width':'1200px'}}>
  <thead class="ant-table-thead">
    <tr>
      <th >名称</th><th >类型</th><th >是否必须</th><th >默认值</th><th >备注</th><th >其他信息</th>
    </tr>
  </thead><tbody className="ant-table-tbody"><tr ><td ><span ><span ></span> code</span></td><td ><span>number</span></td><td >必须</td><td ></td><td ><span ></span></td><td ></td></tr><tr ><td ><span ><span ></span> data</span></td><td ><span>object []</span></td><td >非必须</td><td ></td><td ><span ></span></td><td ><p ><span >item 类型: </span><span>object</span></p></td></tr><tr ><td ><span ><span >├─</span> rid</span></td><td ><span>string</span></td><td >必须</td><td ></td><td ><span >远程配置id</span></td><td ></td></tr><tr ><td ><span ><span >├─</span> sub_status</span></td><td ><span>number</span></td><td >必须</td><td ></td><td ><span >订阅状态 1全部，2订阅中，3非订阅</span></td><td ></td></tr><tr ><td ><span ><span >├─</span> user_status</span></td><td ><span>number</span></td><td >必须</td><td ></td><td ><span >用户状态 1全部，2新用户，3非新用户		</span></td><td ></td></tr><tr ><td ><span ><span >├─</span> device_level</span></td><td ><span>number</span></td><td >必须</td><td ></td><td ><span >机型等级 1低端，2中端，4高端，多选则相加，过滤&操作	</span></td><td ></td></tr><tr ><td ><span ><span >├─</span> weight</span></td><td ><span>number</span></td><td >必须</td><td ></td><td ><span >权重</span></td><td ></td></tr><tr ><td ><span ><span >├─</span> number</span></td><td ><span>number</span></td><td >必须</td><td ></td><td ><span >次数</span></td><td ></td></tr><tr ><td ><span ><span >├─</span> duration</span></td><td ><span>number</span></td><td >必须</td><td ></td><td ><span >时长</span></td><td ></td></tr><tr ><td ><span ><span >├─</span> text_layer</span></td><td ><span>string</span></td><td >必须</td><td ></td><td ><span >文字图层url，注意是图片</span></td><td ></td></tr><tr ><td ><span ><span >├─</span> media</span></td><td ><span>object</span></td><td >必须</td><td ></td><td ><span >媒体数据</span></td><td ></td></tr><tr ><td ><span ><span >├─</span> type</span></td><td ><span>string</span></td><td >必须</td><td ></td><td ><span >img ｜ video</span></td><td ></td></tr><tr ><td ><span ><span >├─</span> url</span></td><td ><span>string</span></td><td >必须</td><td ></td><td ><span ></span></td><td ></td></tr><tr ><td ><span ><span >├─</span> deeplink</span></td><td ><span>string</span></td><td >必须</td><td ></td><td ><span ></span></td><td ></td></tr><tr ><td ><span ><span >├─</span> ended_at</span></td><td ><span>number</span></td><td >必须</td><td ></td><td ><span >结束时间，时间戳(秒)，为0时代表无结束时间</span></td><td ></td></tr><tr ><td ><span ><span >├─</span> trigger</span></td><td ><span>object</span></td><td >必须</td><td ></td><td ><span >频率</span></td><td ></td></tr><tr ><td ><span ><span >├─</span> frequency</span></td><td ><span>number</span></td><td >必须</td><td ></td><td ><span >频率次数</span></td><td ></td></tr><tr ><td ><span ><span >├─</span> cycle</span></td><td ><span>number</span></td><td >必须</td><td ></td><td ><span >频率周期:1天、2周、3月、4年</span></td><td ></td></tr><tr ><td ><span ><span ></span> message</span></td><td ><span>string</span></td><td >必须</td><td ></td><td ><span ></span></td><td ></td></tr><tr ><td ><span ><span ></span> update</span></td><td ><span>string</span></td><td >必须</td><td ></td><td ><span ></span></td><td ></td></tr>
               </tbody>
              </table>


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
