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
[[AWMarvelManager sharedInstance] getProductConfigWithLanguage:language withCountryCode:countryCode withPhrase:phrase withUpdate:update withEffectiveFilter:effectiveFilter withTimezoneOffset:timezoneOffset withCompletion:^(NSInteger result, NSString * _Nonnull errorMsg, NSDictionary * _Nullable data) {
        
}];
```
  </TabItem>
  <TabItem value="Swift" label="Swift">

```Swift
AWMarvelManager.sharedInstance().getProductConfig(withLanguage:language, withCountryCode: countryCode, withPhrase: phrase, withUpdate: update, withEffectiveFilter: effectiveFilter, withTimezoneOffset: timezoneOffset) { result, errorMsg, data in
            
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


### 返回数据
<table>
  <thead class="ant-table-thead">
    <tr>
      <th>名称</th><th>类型</th><th>是否必须</th><th>默认值</th><th>备注</th><th>其他信息</th>
    </tr>
   </thead>
   <tbody className="ant-table-tbody">
    <tr ><td  ><span ><span ></span> code</span></td><td  ><span>number</span></td><td  >必须</td><td  ></td><td  ><span >0成功 其他失败</span></td><td  ></td></tr>
    <tr  ><td  ><span ><span ></span> data</span></td><td  ><span>object</span></td><td  >必须</td><td  ></td><td  ><span >成功是必填，失败时无data，无数据空对象</span></td><td  ></td></tr>
    <tr  ><td  ><span  ><span  >├─</span> rid</span></td><td  ><span>string</span></td><td  >必须</td><td  ></td><td  ><span  >远程配置id</span></td><td  ></td></tr>
  <tr  ><td  ><span  ><span  >├─</span> sub_status</span></td><td  ><span>number</span></td><td  >必须</td><td  ></td><td  ><span  >订阅状态 1全部，2订阅中，3非订阅</span></td><td  ></td></tr>
  <tr  ><td  ><span  ><span  >├─</span> user_status</span></td><td  ><span>number</span></td><td  >必须</td><td  ></td><td  ><span  >用户状态 1全部，2新用户，3非新用户</span></td><td  ></td></tr>
  <tr  ><td  ><span  ><span  >├─</span> device_level</span></td><td  ><span>number</span></td><td  >必须</td><td  ></td><td  ><span  >机型等级 1低端，2中端，4高端，多选则相加，过滤&操作</span></td><td  ></td></tr>
  <tr  ><td  ><span  ><span  >├─</span> p_protocol</span></td><td  ><span>string</span></td><td  >必须</td><td  ></td><td  ><span  >隐私协议	</span></td><td  ></td></tr>
  <tr  ><td  ><span  ><span  >├─</span> u_protocol</span></td><td  ><span>string</span></td><td  >必须</td><td  ></td><td  ><span  >用户协议</span></td><td  ></td></tr>
  <tr  ><td  ><span  ><span  >├─</span> p_trigger</span></td><td  ><span>number</span></td><td  >必须</td><td  ></td><td  ><span  >隐私协议是否触发更新 1是 2否</span></td><td  ></td></tr>
  <tr  ><td  ><span  ><span  >├─</span> u_trigger</span></td><td  ><span>number</span></td><td  >必须</td><td  ></td><td  ><span  >用户协议是否触发更新 1是 2否</span></td><td  ></td></tr>
  <tr  ><td  ><span  ><span  >├─</span> cus_config</span></td><td  ><span>object []</span></td><td  >必须</td><td  ></td><td  ><span  >自定义配置</span></td><td  ><p  ><span  >item 类型: </span><span>object</span></p></td></tr>
  <tr  ><td  ><span  ><span  >├─</span> type</span></td><td  ><span>number</span></td><td  >必须</td><td  ></td><td  ><span  >1文案(字符串) 2数字 3 bool</span></td><td  ></td></tr><tr  ><td  ><span  ><span  >├─</span> key</span></td><td  ><span>string</span></td><td  >必须</td><td  ></td><td  ><span  >key值</span></td><td  ></td></tr>
  <tr  ><td  ><span  ><span  >├─</span> value</span></td><td  ><span>string</span></td><td  >必须</td><td  ></td><td  ><span  >type=1:字符串；type=2:数字；type=3:bool</span></td><td  ></td></tr>
  <tr  ><td  ><span  ><span  >├─</span> created_at</span></td><td  ><span>number</span></td><td  >必须</td><td  ></td><td  ><span  >创建时间，时间戳(秒)</span></td><td  ></td></tr>
  <tr  ><td  ><span  ><span  >├─</span> updated_at</span></td><td  ><span>number</span></td><td  >必须</td><td  ></td><td  ><span  >更新时间，时间戳(秒)</span></td><td  ></td></tr>
  <tr  ><td  ><span  ><span  >├─</span> ended_at</span></td><td  ><span>number</span></td><td  >必须</td><td  ></td><td  ><span  >结束时间，时间戳(秒)，为0时代表无结束时间</span></td><td  ></td></tr>
  <tr  ><td  ><span  ><span  ></span> message</span></td><td  ><span>string</span></td><td  >必须</td><td  ></td><td  ><span  ></span></td><td  ></td></tr>
  <tr  ><td  ><span  ><span  ></span> update</span></td><td  ><span>string</span></td><td  >必须</td><td  ></td><td  ><span  >数据的md5值</span></td><td  ></td></tr>
   </tbody>
 </table>