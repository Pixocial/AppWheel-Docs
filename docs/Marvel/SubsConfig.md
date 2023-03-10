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
MarvelManager.getInstance().getNewSubs(countryCode,language,phrase,update,effectiveFilter,timezoneOffset,new AWHttpOriginalCallback(){
@Override
public void response(int code,String data){

        }
        });
```

  </TabItem>
  <TabItem value="Kotlin" label="Kotlin">

```Kotlin

MarvelManager.getInstance().getNewSubs(countryCode, language, phrase, update, effectiveFilter, timezoneOffset, object : AWHttpOriginalCallback {
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

### 请求参数

**Query**

| 参数名称             | 是否必须 | 示例  | 备注                                                                        |
|------------------|------|-----|---------------------------------------------------------------------------|
| app_id           | 是    | 103 | 产品平台id                                                                    |
| lang             | 是    |     | 语言                                                                        |
| country_code     | 是    |     | 国家                                                                        |
| phrase           | 否    |     | 预览密钥                                                                      |
| version          | 是    |     | 客户端版本                                                                     |
| update           | 否    |     | 数据的md5值                                                                   |
| effective_filter | 否    |     | 传1新时区逻辑，不传为旧逻辑 参照https://meitu.feishu.cn/docs/doccnYciNqUjP32KmNro05TXoth |

### 返回数据

<table style={{'min-width':'1200px'}} >
    <thead class="ant-table-thead">
    <tr>
        <th>名称</th>
        <th >类型</th>
        <th >是否必须</th>
        <th >默认值</th>
        <th >备注</th>
        <th >其他信息</th>
    </tr>
    </thead>
    <tbody className="ant-table-tbody">
    <tr >
        <td ><span ><span ></span> code</span></td>
        <td ><span>number</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span ></span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span ></span> data</span></td>
        <td ><span>object</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span ></span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> activity</span></td>
        <td ><span>object []</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >活动（对用户下发多条）</span></td>
        <td ><p ><span >item 类型: </span><span>object</span></p></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> name</span></td>
        <td ><span>string</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >名称</span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> countdown</span></td>
        <td ><span>object</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >倒计时</span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> start_time</span></td>
        <td ><span>number</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >开始时间（时间戳：秒）</span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> end_time</span></td>
        <td ><span>number</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >结束时间（时间戳：秒）</span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> countdown_color</span></td>
        <td ><span>string</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >背景色值</span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> status</span></td>
        <td ><span>number</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >状态1启用2禁用</span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> countdown_text_color</span></td>
        <td ><span>string</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >倒计时文字背景</span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> titleo_color</span></td>
        <td ><span>string</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >标题1字体颜色</span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> titleo_cont</span></td>
        <td ><span>string</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >标题1标题</span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> titlet_color</span></td>
        <td ><span>string</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >标题2字体颜色</span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> titlet_cont</span></td>
        <td ><span>string</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >标题2标题</span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> bac_pic</span></td>
        <td ><span>string</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >标题背景</span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> describe_copy</span></td>
        <td ><span>string</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >描述文案</span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> describe_color</span></td>
        <td ><span>string</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >描述字体颜色</span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> content</span></td>
        <td ><span>object []</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >内容区</span></td>
        <td ><p ><span >item 类型: </span><span>object</span></p></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> cont_text</span></td>
        <td ><span>string</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >文本</span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> picture</span></td>
        <td ><span>string</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >图片</span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> class_info</span></td>
        <td ><span>string</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >分类</span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> year</span></td>
        <td ><span>object</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >订阅方案--年</span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> product_id</span></td>
        <td ><span>string</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >产品id</span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> discount</span></td>
        <td ><span>number</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >折扣</span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> free_days</span></td>
        <td ><span>number</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >免费天数</span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> describe</span></td>
        <td ><span>string</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >折扣描述</span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> mark</span></td>
        <td ><span>string</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >折扣标记</span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> button_copy</span></td>
        <td ><span>string</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >按钮文案</span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> status</span></td>
        <td ><span>number</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >状态1启用2禁用</span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> badge_bg_color</span></td>
        <td ><span>string</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >左侧标签颜色（底色/文字/描边）</span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> badge_text_color</span></td>
        <td ><span>string</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >左侧标签颜色（底色/文字/描边）</span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> badge_border_inside_color</span></td>
        <td ><span>string</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >左侧标签颜色（底色/文字/描边） </span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> save_bg_selected_color</span></td>
        <td ><span>string</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >Save %选中底色（包括底色与描边）</span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> save_text_selected_color</span></td>
        <td ><span>string</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >Save %选中文案色值</span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> save_bg_default_color</span></td>
        <td ><span>string</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >Save %未选中底色</span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> save_text_default_color</span></td>
        <td ><span>string</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >Save %未选中文案色值</span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> month</span></td>
        <td ><span>object</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >订阅方案--月</span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> product_id</span></td>
        <td ><span>string</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >产品id</span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> discount</span></td>
        <td ><span>number</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >折扣</span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> free_days</span></td>
        <td ><span>number</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >免费天数</span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> describe</span></td>
        <td ><span>string</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >折扣描述</span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> mark</span></td>
        <td ><span>string</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >折扣标记</span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> button_copy</span></td>
        <td ><span>string</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >按钮文案</span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> status</span></td>
        <td ><span>number</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >状态1启用2禁用</span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> week</span></td>
        <td ><span>object</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >订阅方案--周</span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> product_id</span></td>
        <td ><span>string</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >产品id</span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> discount</span></td>
        <td ><span>number</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >折扣</span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> free_days</span></td>
        <td ><span>number</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >免费天数</span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> describe</span></td>
        <td ><span>string</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >折扣描述</span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> mark</span></td>
        <td ><span>string</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >折扣标记</span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> button_copy</span></td>
        <td ><span>string</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >按钮文案</span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> status</span></td>
        <td ><span>number</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >状态1启用2禁用</span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> lifetime</span></td>
        <td ><span>object</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >订阅方案--终生</span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> product_id</span></td>
        <td ><span>string</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >产品id</span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> discount</span></td>
        <td ><span>number</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >折扣</span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> free_days</span></td>
        <td ><span>number</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >免费天数</span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> describe</span></td>
        <td ><span>string</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >折扣描述</span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> mark</span></td>
        <td ><span>string</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >折扣标记</span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> button_copy</span></td>
        <td ><span>string</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >按钮文案</span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> status</span></td>
        <td ><span>number</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >状态1启用2禁用</span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> quarter</span></td>
        <td ><span>object</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >订阅方案--季度</span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> product_id</span></td>
        <td ><span>string</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >产品id</span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> discount</span></td>
        <td ><span>number</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >折扣</span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> free_days</span></td>
        <td ><span>number</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >免费天数</span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> describe</span></td>
        <td ><span>string</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >折扣描述</span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> mark</span></td>
        <td ><span>string</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >折扣标记</span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> button_copy</span></td>
        <td ><span>string</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >按钮文案</span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> status</span></td>
        <td ><span>number</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >状态1启用2禁用</span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> cont_color</span></td>
        <td ><span>string</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >内容区字体颜色</span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> img_background</span></td>
        <td ><span>string</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >图片背景</span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> video_background</span></td>
        <td ><span>string</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >视频背景</span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> home_ent</span></td>
        <td ><span>string</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >首页入口</span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> setting_entry</span></td>
        <td ><span>string</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >设置页入口</span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> banner</span></td>
        <td ><span>string</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >banner入口</span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> sub_color</span></td>
        <td ><span>string</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >订阅方案字体颜色</span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> sub_blacolor</span></td>
        <td ><span>string</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >订阅方案背景颜色</span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> mtg_id</span></td>
        <td ><span>string</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >ID</span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> highlight</span></td>
        <td ><span>string</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >高亮选中 week：周 ，month：月，quarter：季，year：年，lifetime：终身（AB/AirVid）</span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> shoot</span></td>
        <td ><span>string</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >拍摄入口 （partynow专用）</span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> eff_status</span></td>
        <td ><span>number</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >是否开启生效时间，状态1启用2禁用</span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> end_ed</span></td>
        <td ><span>number</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >生效结束时间</span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> start_ed</span></td>
        <td ><span>string</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >生效开始时间</span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> sku_bg_default_color</span></td>
        <td ><span>string</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >SKU默认颜色SKU BG Default</span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> sku_bg_selected_color</span></td>
        <td ><span>string</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >SKU选中颜色 SKU BG Selected</span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> price_default_color</span></td>
        <td ><span>string</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >价格文案色值（默认/选中）Price Default</span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> price_selected_color</span></td>
        <td ><span>string</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >价格文案色值（默认/选中）Price Selected</span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> discount_bg_color</span></td>
        <td ><span>string</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >折扣底色</span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> discount_text_color</span></td>
        <td ><span>string</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >折扣文案</span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> background_color</span></td>
        <td ><span>string</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >背景色值</span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> terms_background_color</span></td>
        <td ><span>string</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >条款背景色</span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> foreground</span></td>
        <td ><span>string</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >前景</span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> promotion</span></td>
        <td ><span>object []</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >促销（字段同活动一致）（仅对用户下发一条（“开始时间”最小的，次优 “创建时间”「创建时间最小的一条」），开启了生效时间和没开启生效时间的促销类型，开启了生效时间的优先于没开启的 ））</span></td>
        <td ><p ><span >item 类型: </span><span>object</span></p></td>
    </tr>
    <tr >
        <td ><span ><span >├─</span> daily</span></td>
        <td ><span>object []</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >日常（字段同活动一致）</span></td>
        <td ><p ><span >item 类型: </span><span>object</span></p></td>
    </tr>
    <tr >
        <td ><span ><span ></span> message</span></td>
        <td ><span>string</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span ></span></td>
        <td ></td>
    </tr>
    <tr >
        <td ><span ><span ></span> update</span></td>
        <td ><span>string</span></td>
        <td >必须</td>
        <td ></td>
        <td ><span >数据的md5值</span></td>
        <td ></td>
    </tr>
    </tbody>
</table>

```json

{
    "code": 0,
    "data": {
        "activity": [
            {
                "id": 20478,
                "name": "TH-新尺寸-泼水节8折",
                "countdown": {
                    "start_time": 1649923200,
                    "end_time": 1650182399,
                    "countdown_color": "#154E3B",
                    "status": 1,
                    "countdown_text_color": "#454321"
                },
                "titleo_color": "#454321",
                "titleo_cont": "Happy Songkran",
                "titlet_color": "#454321",
                "titlet_cont": "",
                "bac_pic": "https://gcs.beautyplus.com/2845b996950260271c47adf6e3437024.png",
                "describe_copy": "",
                "describe_color": "",
                "content": [],
                "year": {
                    "status": 1,
                    "product_id": "beautyplus.subs.month12.func00.lev00.campaign.songkranfestival.ver0",
                    "discount": 0.8,
                    "free_days": 7,
                    "describe": "",
                    "button_copy": "dddddd",
                    "badge_bg_color": "#454321",
                    "badge_text_color": "#454321",
                    "badge_border_inside_color": "#4543fdfdf321",
                    "save_bg_selected_color": "#454321",
                    "save_text_selected_color": "#454321",
                    "save_bg_default_color": "#454321",
                    "save_text_default_color": "#454321",
                    "mark": ""
                },
                "month": {
                    "status": 1,
                    "product_id": "beautyplus.subs.month1.func00.lev00.campaign.songkranfestival.ver0",
                    "discount": 0,
                    "free_days": 0,
                    "describe": "",
                    "button_copy": "",
                    "badge_bg_color": "",
                    "badge_text_color": "",
                    "badge_border_inside_color": "",
                    "save_bg_selected_color": "",
                    "save_text_selected_color": "",
                    "save_bg_default_color": "",
                    "save_text_default_color": "",
                    "mark": ""
                },
                "week": {
                    "status": 2,
                    "product_id": "",
                    "discount": 0,
                    "free_days": 0,
                    "describe": "",
                    "button_copy": "",
                    "badge_bg_color": "",
                    "badge_text_color": "",
                    "badge_border_inside_color": "",
                    "save_bg_selected_color": "",
                    "save_text_selected_color": "",
                    "save_bg_default_color": "",
                    "save_text_default_color": "",
                    "mark": ""
                },
                "lifetime": {
                    "status": 2,
                    "product_id": "",
                    "discount": 0,
                    "free_days": 0,
                    "describe": "",
                    "button_copy": "",
                    "badge_bg_color": "",
                    "badge_text_color": "",
                    "badge_border_inside_color": "",
                    "save_bg_selected_color": "",
                    "save_text_selected_color": "",
                    "save_bg_default_color": "",
                    "save_text_default_color": "",
                    "mark": ""
                },
                "quarter": {
                    "status": 2,
                    "product_id": "",
                    "discount": 0,
                    "free_days": 0,
                    "describe": "",
                    "button_copy": "",
                    "badge_bg_color": "",
                    "badge_text_color": "",
                    "badge_border_inside_color": "",
                    "save_bg_selected_color": "",
                    "save_text_selected_color": "",
                    "save_bg_default_color": "",
                    "save_text_default_color": "",
                    "mark": ""
                },
                "cont_color": "",
                "img_background": "https://gcs.beautyplus.com/e0e54b954e9639507f0fd7c2f2145b8e.png",
                "video_background": "",
                "home_ent": "https://gcs.beautyplus.com/ab152a93e5f2d025782ba9e00b651997.png",
                "setting_entry": "",
                "banner": "",
                "shoot": "",
                "sub_color": "fdafadf",
                "sub_blacolor": "fdafadf",
                "start_ed": 0,
                "end_ed": 0,
                "eff_status": 2,
                "mtg_id": "BP_SUB_00001517",
                "highlight": "ddfdfdfsfadsfa",
                "sku_bg_default_color": "#454321",
                "sku_bg_selected_color": "#454321",
                "price_default_color": "#454321",
                "price_selected_color": "#454321",
                "discount_bg_color": "#454321",
                "discount_text_color": "#454321",
                "background_color": "#dfdf11",
                "terms_background_color": "#454321",
                "foreground": "https://dfdfdf"
            }
        ],
        "daily": [],
        "promotion": [
            {
                "id": 19411,
                "name": "测试-Tier2国家",
                "countdown": {
                    "start_time": 0,
                    "end_time": 0,
                    "countdown_color": "",
                    "status": 2,
                    "countdown_text_color": ""
                },
                "titleo_color": "",
                "titleo_cont": "Happy Halloween",
                "titlet_color": "",
                "titlet_cont": "",
                "bac_pic": "https://gcs.beautyplus.com/97b9926acea6b5969eaba2a50c850193.png",
                "describe_copy": "",
                "describe_color": "",
                "content": [],
                "year": {
                    "status": 1,
                    "product_id": "beautyplus.subs.month12.func00.lev00.campaign.halloween.ver4",
                    "discount": 0.8,
                    "free_days": 7,
                    "describe": "",
                    "button_copy": "",
                    "badge_bg_color": "",
                    "badge_text_color": "",
                    "badge_border_inside_color": "",
                    "save_bg_selected_color": "",
                    "save_text_selected_color": "",
                    "save_bg_default_color": "",
                    "save_text_default_color": "",
                    "mark": ""
                },
                "month": {
                    "status": 1,
                    "product_id": "beautyplus.subs.month1.func00.lev00.campaign.halloween.ver4",
                    "discount": 0,
                    "free_days": 0,
                    "describe": "",
                    "button_copy": "",
                    "badge_bg_color": "",
                    "badge_text_color": "",
                    "badge_border_inside_color": "",
                    "save_bg_selected_color": "",
                    "save_text_selected_color": "",
                    "save_bg_default_color": "",
                    "save_text_default_color": "",
                    "mark": ""
                },
                "week": {
                    "status": 2,
                    "product_id": "",
                    "discount": 0,
                    "free_days": 0,
                    "describe": "",
                    "button_copy": "",
                    "badge_bg_color": "",
                    "badge_text_color": "",
                    "badge_border_inside_color": "",
                    "save_bg_selected_color": "",
                    "save_text_selected_color": "",
                    "save_bg_default_color": "",
                    "save_text_default_color": "",
                    "mark": ""
                },
                "lifetime": {
                    "status": 2,
                    "product_id": "",
                    "discount": 0,
                    "free_days": 0,
                    "describe": "",
                    "button_copy": "",
                    "badge_bg_color": "",
                    "badge_text_color": "",
                    "badge_border_inside_color": "",
                    "save_bg_selected_color": "",
                    "save_text_selected_color": "",
                    "save_bg_default_color": "",
                    "save_text_default_color": "",
                    "mark": ""
                },
                "quarter": {
                    "status": 2,
                    "product_id": "",
                    "discount": 0,
                    "free_days": 0,
                    "describe": "",
                    "button_copy": "",
                    "badge_bg_color": "",
                    "badge_text_color": "",
                    "badge_border_inside_color": "",
                    "save_bg_selected_color": "",
                    "save_text_selected_color": "",
                    "save_bg_default_color": "",
                    "save_text_default_color": "",
                    "mark": ""
                },
                "cont_color": "",
                "img_background": "https://gcs.beautyplus.com/6333a2d8b333f0f342ad0b50744b36ab.png",
                "video_background": "",
                "home_ent": "https://gcs.beautyplus.com/925731bcb5a34e764dc100960a72e254.jpeg",
                "setting_entry": "",
                "banner": "",
                "shoot": "",
                "sub_color": "",
                "sub_blacolor": "",
                "start_ed": 1666627200,
                "end_ed": 1666843199,
                "eff_status": 1,
                "mtg_id": "BP_SUB_00000278",
                "highlight": "",
                "sku_bg_default_color": "",
                "sku_bg_selected_color": "",
                "price_default_color": "",
                "price_selected_color": "",
                "discount_bg_color": "",
                "discount_text_color": "",
                "background_color": "",
                "terms_background_color": "",
                "foreground": ""
            }
        ]
    },
    "message": "success",
    "update": "263aeefafe0b56ae9d77f1ffb77cf984"
}
```