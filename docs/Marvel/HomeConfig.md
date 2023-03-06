---
sidebar_position: 6
title: 首页配置
id: 首页配置
---


import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

<Tabs>
  <TabItem value="Java" label="Java" default>

```Java
MarvelManager.getInstance().getHomeConfig(countryCode, language, phrase, update, effectiveFilter, timezoneOffset, new AWHttpOriginalCallback() {
    @Override
    public void response(int code, String data) {

    }
});
```
  </TabItem>
  <TabItem value="Kotlin" label="Kotlin">

```Kotlin

MarvelManager.getInstance().getHomeConfig(countryCode, language,phrase, update, effectiveFilter, timezoneOffset, object : AWHttpOriginalCallback{
    override fun response(code: Int, data: String?) {
    }
})
```
  </TabItem>
  <TabItem value="Objective-C" label="Objective-C">

```Objective-C 
 [[AWPurchaseKit getMarvelManager] getHomeConfigWithLanguage:language withCountryCode:countryCode withPhrase:phrase withUpdate:update withEffectiveFilter:effectiveFilter withTimezoneOffset:timezoneOffset completion:^(NSInteger result, NSString * _Nonnull errorMsg, NSDictionary * _Nullable data) {
        
}];
```
  </TabItem>
  <TabItem value="Swift" label="Swift">

```Swift

AWPurchaseKit.getMarvelManager().gethomeConfig(withLanguage:language, withCountryCode: countryCode, withPhrase: phrase, withUpdate: update, withEffectiveFilter: effectiveFilter, withTimezoneOffset: timezoneOffset) { result, errorMsg, data in
            
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
    "logo": "",
    "list": [
      {
        "rid": "BP_cat_HPB_00000001",
        "user_status": 1,
        "sub_status": 1,
        "effective_time": {
          "status": 2,
          "info": [
            0,
            0
          ],
          "timezone": {
            "id": "CTT",
            "std_offset": 480
          }
        },
        "type": "HPB_TOP",
        "sort": 0,
        "text_content": {},
        "text_layer": {},
        "media": {
          "type": "",
          "url": "",
          "ratio": ""
        },
        "size": "",
        "marvellink": "",
        "link_type": 0,
        "abcode": 0,
        "background_color": "",
        "pag": {
          "type": "",
          "url": ""
        },
        "custom_config": [],
        "title": "",
        "subtitle": "",
        "show_title": false,
        "head_img": {
          "url": "",
          "ratio": ""
        },
        "material_content": [],
        "sub": [
          {
            "name": "🎃促销（亚洲版本）",
            "rid": "BP_HPB_00000139",
            "user_status": 1,
            "sub_status": 3,
            "effective_time": {
              "status": 1,
              "info": [
                1666886400,
                1667375999
              ],
              "timezone": {
                "id": "CTT",
                "std_offset": 480
              }
            },
            "sort": 100000,
            "text_content": {
              "en": {
                "title": "",
                "text": "",
                "color_value": ""
              }
            },
            "text_layer": {},
            "media": {
              "type": "img",
              "url": "https://gcs.beautyplus.com/ed51b9c4287e4e13840a12a75bbe30b6.jpeg",
              "ratio": "750:640"
            },
            "abcode": 0,
            "background_color": "",
            "marvellink": "beautyplus://p_subscription",
            "link_type": 2,
            "cover_img": ""
          },
          {
            "name": "🎃万圣节漫画脸亚",
            "rid": "BP_HPB_00000112",
            "user_status": 1,
            "sub_status": 1,
            "effective_time": {
              "status": 1,
              "info": [
                1665936000,
                1667361599
              ],
              "timezone": {
                "id": "CTT",
                "std_offset": 480
              }
            },
            "sort": 100002,
            "text_content": {
              "en": {
                "title": "",
                "text": "",
                "color_value": ""
              }
            },
            "text_layer": {},
            "media": {
              "type": "img",
              "url": "https://gcs.beautyplus.com/01533f0c604b45538b215e1308b9bfea.png",
              "ratio": "750:640"
            },
            "abcode": 0,
            "background_color": "",
            "marvellink": "beautyplus://p_edit/f_style?content=1STY00000038",
            "link_type": 2,
            "cover_img": ""
          },
          {
            "name": "壁纸H5_1101(秋天)",
            "rid": "BP_HPB_00000145",
            "user_status": 1,
            "sub_status": 1,
            "effective_time": {
              "status": 1,
              "info": [
                1667232000,
                0
              ],
              "timezone": {
                "id": "CTT",
                "std_offset": 480
              }
            },
            "sort": 100004,
            "text_content": {
              "en": {
                "title": "",
                "text": "",
                "color_value": ""
              }
            },
            "text_layer": {},
            "media": {
              "type": "img",
              "url": "https://gcs.beautyplus.com/7b55526e9831a74e727b63ee847f13c7.jpeg",
              "ratio": "750:640"
            },
            "abcode": 0,
            "background_color": "",
            "marvellink": "https://batman.meitu.com/h5/projects/7bbcae2746f24bcf848e2ba10336048f?lang=en",
            "link_type": 1,
            "cover_img": ""
          },
          {
            "name": "漫画脸EN亚",
            "rid": "BP_HPB_00000034",
            "user_status": 1,
            "sub_status": 1,
            "effective_time": {
              "status": 1,
              "info": [
                1667361600,
                0
              ],
              "timezone": {
                "id": "CTT",
                "std_offset": 480
              }
            },
            "sort": 100005,
            "text_content": {
              "en": {
                "title": "",
                "text": "",
                "color_value": ""
              }
            },
            "text_layer": {},
            "media": {
              "type": "img",
              "url": "https://gcs.beautyplus.com/64a3b3d08aedc07da21c9a561ddc74d5.jpeg",
              "ratio": "750:640"
            },
            "abcode": 0,
            "background_color": "",
            "marvellink": "beautyplus://p_edit/f_style?content=1STY00000038",
            "link_type": 2,
            "cover_img": ""
          },
          {
            "name": "🎃换脸H5_亚",
            "rid": "BP_HPB_00000133",
            "user_status": 1,
            "sub_status": 1,
            "effective_time": {
              "status": 1,
              "info": [
                1666713600,
                1667361599
              ],
              "timezone": {
                "id": "CTT",
                "std_offset": 480
              }
            },
            "sort": 100009,
            "text_content": {
              "en": {
                "title": "",
                "text": "",
                "color_value": ""
              }
            },
            "text_layer": {},
            "media": {
              "type": "img",
              "url": "https://gcs.beautyplus.com/f926510221e2efcce396d2d301b2a8de.png",
              "ratio": "750:640"
            },
            "abcode": 0,
            "background_color": "",
            "marvellink": "https://h5.mr.meitu.com/2022/faceswap_h5/?language=en",
            "link_type": 1,
            "cover_img": ""
          },
          {
            "name": "<7.5.131 🎃万圣节风格化天空_亚洲",
            "rid": "BP_HPB_00000130",
            "user_status": 1,
            "sub_status": 1,
            "effective_time": {
              "status": 1,
              "info": [
                1666281600,
                1667361599
              ],
              "timezone": {
                "id": "CTT",
                "std_offset": 480
              }
            },
            "sort": 100012,
            "text_content": {
              "en": {
                "title": "",
                "text": "",
                "color_value": ""
              }
            },
            "text_layer": {},
            "media": {
              "type": "img",
              "url": "https://gcs.beautyplus.com/bd5a34fc3f66fbc4bf71d170039afb7f.jpeg",
              "ratio": "750:640"
            },
            "abcode": 0,
            "background_color": "",
            "marvellink": "https://go.onelink.me/3931227768/e33dc7d6",
            "link_type": 3,
            "cover_img": ""
          }
        ],
        "cover_img": ""
      },
      {
        "rid": "BP_cat_HPB_00000067",
        "user_status": 1,
        "sub_status": 3,
        "effective_time": {
          "status": 2,
          "info": [
            0,
            0
          ],
          "timezone": {
            "id": "CTT",
            "std_offset": 480
          }
        },
        "type": "HPB_AD",
        "sort": 100000,
        "text_content": {},
        "text_layer": {},
        "media": {
          "type": "",
          "url": "",
          "ratio": ""
        },
        "size": "680:500",
        "marvellink": "ad_banner_topbanner",
        "link_type": 2,
        "abcode": 0,
        "background_color": "",
        "pag": {
          "type": "",
          "url": ""
        },
        "custom_config": [],
        "title": "",
        "subtitle": "",
        "show_title": false,
        "head_img": {
          "url": "",
          "ratio": ""
        },
        "material_content": [],
        "sub": [],
        "cover_img": ""
      },
      {
        "rid": "BP_cat_HPB_00000312",
        "user_status": 1,
        "sub_status": 1,
        "effective_time": {
          "status": 2,
          "info": [
            0,
            0
          ],
          "timezone": {
            "id": "CTT",
            "std_offset": 480
          }
        },
        "type": "HPB_TEM",
        "sort": 100001,
        "text_content": {},
        "text_layer": {},
        "media": {
          "type": "",
          "url": "",
          "ratio": ""
        },
        "size": "",
        "marvellink": "",
        "link_type": 0,
        "abcode": 0,
        "background_color": "",
        "pag": {
          "type": "",
          "url": ""
        },
        "custom_config": [],
        "title": "🍂Autumn Aesthetics",
        "subtitle": "All at once, summer collapsed into Autumn.",
        "show_title": true,
        "head_img": {
          "url": "",
          "ratio": ""
        },
        "material_content": [
          {
            "m_id": "BP_TEM_00002067",
            "tag": "NEW",
            "is_paid": 1,
            "img": "https://gcs-duffle.pixocial.com/duffle/72ad6d11e4ef6a0c5579ac19abfc5ef2.jpeg",
            "color": "",
            "img_ratio": "1080:1620",
            "title": "October ",
            "cover_video": ""
          },
          {
            "m_id": "BP_TEM_00001960",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs-duffle.pixocial.com/duffle/client/4944a0e4-8e39-469f-b060-dfbe4784e2e9.jpeg",
            "color": "",
            "img_ratio": "1080:1350",
            "title": "Autumn",
            "cover_video": ""
          },
          {
            "m_id": "BP_TEM_00001911",
            "tag": "NEW",
            "is_paid": 1,
            "img": "https://gcs-duffle.pixocial.com/duffle/client/7aab5268-dbc8-4a43-9962-d616c75f58a0.jpeg",
            "color": "",
            "img_ratio": "1080:1350",
            "title": "Adventure time",
            "cover_video": ""
          },
          {
            "m_id": "BP_TEM_00002071",
            "tag": "NEW",
            "is_paid": 1,
            "img": "https://gcs-duffle.pixocial.com/duffle/client/6d8d83a3-8d65-4e8c-a247-4cd35c3ab7b7.jpeg",
            "color": "",
            "img_ratio": "1080:1920",
            "title": "October 01",
            "cover_video": ""
          },
          {
            "m_id": "BP_TEM_00001952",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs-duffle.pixocial.com/duffle/client/49d4e46f-5517-46f2-bb7e-9080d2b5b2bd.jpeg",
            "color": "",
            "img_ratio": "1080:1620",
            "title": "Autumn",
            "cover_video": ""
          },
          {
            "m_id": "BP_TEM_00001954",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs-duffle.pixocial.com/duffle/client/4792e020-89a6-4aca-a21f-00a665500cce.jpeg",
            "color": "",
            "img_ratio": "1080:1350",
            "title": "初秋outfit",
            "cover_video": ""
          },
          {
            "m_id": "BP_TEM_00001977",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs-duffle.pixocial.com/duffle/client/790f7f3a-432c-4605-8563-d08bdef9366f.jpeg",
            "color": "",
            "img_ratio": "1080:1920",
            "title": "Autumn",
            "cover_video": ""
          },
          {
            "m_id": "BP_TEM_00000637",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs-duffle.pixocial.com/test/65c9074b-ff1e-4273-9ac9-ff872607816e.jpeg",
            "color": "",
            "img_ratio": "1080:1620",
            "title": "Enjoy the journey ",
            "cover_video": ""
          }
        ],
        "sub": [],
        "cover_img": ""
      },
      {
        "rid": "BP_cat_HPB_00000040",
        "user_status": 1,
        "sub_status": 3,
        "effective_time": {
          "status": 2,
          "info": [
            0,
            0
          ],
          "timezone": {
            "id": "CTT",
            "std_offset": 480
          }
        },
        "type": "HPB",
        "sort": 100002,
        "text_content": {
          "en": {
            "title": "",
            "text": "",
            "color_value": ""
          }
        },
        "text_layer": {
          "en": ""
        },
        "media": {
          "type": "video",
          "url": "https://gcs.beautyplus.com/b6a03993b17a28d7adb6c36522df202b.mp4",
          "ratio": ""
        },
        "size": "680:500",
        "marvellink": "beautyplus://p_subscription",
        "link_type": 2,
        "abcode": 0,
        "background_color": "",
        "pag": {
          "type": "",
          "url": ""
        },
        "custom_config": [],
        "title": "",
        "subtitle": "",
        "show_title": false,
        "head_img": {
          "url": "",
          "ratio": ""
        },
        "material_content": [],
        "sub": [],
        "cover_img": ""
      },
      {
        "rid": "BP_cat_HPB_00000120",
        "user_status": 1,
        "sub_status": 1,
        "effective_time": {
          "status": 2,
          "info": [
            0,
            0
          ],
          "timezone": {
            "id": "CTT",
            "std_offset": 480
          }
        },
        "type": "HPB_ARR",
        "sort": 100003,
        "text_content": {},
        "text_layer": {},
        "media": {
          "type": "",
          "url": "",
          "ratio": ""
        },
        "size": "",
        "marvellink": "",
        "link_type": 0,
        "abcode": 0,
        "background_color": "",
        "pag": {
          "type": "",
          "url": ""
        },
        "custom_config": [],
        "title": "Daily Makeup",
        "subtitle": "",
        "show_title": true,
        "head_img": {
          "url": "",
          "ratio": ""
        },
        "material_content": [
          {
            "m_id": "501375",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs.beautyplus.com/8f2a111b71a4f7376e142f0500289550.jpeg",
            "color": "#CDB381",
            "img_ratio": "",
            "title": "ApricotBlush",
            "cover_video": ""
          },
          {
            "m_id": "502083",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs.beautyplus.com/002d26e591bdbd19d8c5f64562c482cf.jpeg",
            "color": "#CDB381",
            "img_ratio": "",
            "title": "Blush girl",
            "cover_video": ""
          },
          {
            "m_id": "502119",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs.beautyplus.com/71e1afb089c4c45c807ec7ba68c8c311.png",
            "color": "#CDB381",
            "img_ratio": "",
            "title": "lilac makeup",
            "cover_video": ""
          },
          {
            "m_id": "501733",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs.beautyplus.com/f317648c1e534857e601a4825f6e494f.png",
            "color": "#CDB381",
            "img_ratio": "",
            "title": "Orange soda",
            "cover_video": ""
          },
          {
            "m_id": "500906",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs.beautyplus.com/365ad70a2b081ccdb3cf658ef8c58433.jpeg",
            "color": "#CDB381",
            "img_ratio": "",
            "title": "LightRed Makeup",
            "cover_video": ""
          },
          {
            "m_id": "502094",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs.beautyplus.com/84ec1c114fe6055c335eaeaa02823914.png",
            "color": "#CDB381",
            "img_ratio": "",
            "title": "JP Gal makeup",
            "cover_video": ""
          }
        ],
        "sub": [],
        "cover_img": ""
      },
      {
        "rid": "BP_cat_HPB_00000068",
        "user_status": 1,
        "sub_status": 3,
        "effective_time": {
          "status": 2,
          "info": [
            0,
            0
          ],
          "timezone": {
            "id": "CTT",
            "std_offset": 480
          }
        },
        "type": "HPB_AD",
        "sort": 100004,
        "text_content": {},
        "text_layer": {},
        "media": {
          "type": "",
          "url": "",
          "ratio": ""
        },
        "size": "680:140",
        "marvellink": "ad_banner_bottom",
        "link_type": 2,
        "abcode": 0,
        "background_color": "",
        "pag": {
          "type": "",
          "url": ""
        },
        "custom_config": [],
        "title": "",
        "subtitle": "",
        "show_title": false,
        "head_img": {
          "url": "",
          "ratio": ""
        },
        "material_content": [],
        "sub": [],
        "cover_img": ""
      },
      {
        "rid": "BP_cat_HPB_00000311",
        "user_status": 1,
        "sub_status": 1,
        "effective_time": {
          "status": 2,
          "info": [
            0,
            0
          ],
          "timezone": {
            "id": "CTT",
            "std_offset": 480
          }
        },
        "type": "HPB_TEM",
        "sort": 100005,
        "text_content": {},
        "text_layer": {},
        "media": {
          "type": "",
          "url": "",
          "ratio": ""
        },
        "size": "",
        "marvellink": "",
        "link_type": 0,
        "abcode": 0,
        "background_color": "",
        "pag": {
          "type": "",
          "url": ""
        },
        "custom_config": [],
        "title": "#PFP",
        "subtitle": "Cartoon Profile Pictures",
        "show_title": true,
        "head_img": {
          "url": "",
          "ratio": ""
        },
        "material_content": [
          {
            "m_id": "BP_TEM_00001473",
            "tag": "HOT",
            "is_paid": 1,
            "img": "https://gcs.beautyplus.com/e38df237e4fd98dc536642cf06d8c658.jpeg",
            "color": "",
            "img_ratio": "1080:1080",
            "title": "Sns8",
            "cover_video": ""
          },
          {
            "m_id": "BP_TEM_00002006",
            "tag": "HOT",
            "is_paid": 1,
            "img": "https://gcs-duffle.pixocial.com/duffle/187ee5378b042a6877cb60e07e1c0893.png",
            "color": "",
            "img_ratio": "1080:1350",
            "title": "seal story",
            "cover_video": ""
          },
          {
            "m_id": "BP_TEM_00001998",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs-duffle.pixocial.com/duffle/1078887be19e18d731a21fffbd2ed6cd.jpeg",
            "color": "",
            "img_ratio": "1080:1080",
            "title": "cartoon filter",
            "cover_video": ""
          },
          {
            "m_id": "BP_TEM_00002009",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs-duffle.pixocial.com/duffle/client/c0034e0b-0fac-4261-a1b8-a0fbbb4e8708.jpeg",
            "color": "",
            "img_ratio": "1080:1350",
            "title": "cartoon Dargon",
            "cover_video": ""
          },
          {
            "m_id": "BP_TEM_00002019",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs-duffle.pixocial.com/duffle/client/759cb68f-b78d-4b92-bf5c-85aaed345b89.jpeg",
            "color": "",
            "img_ratio": "1080:1080",
            "title": "漫画脸",
            "cover_video": ""
          },
          {
            "m_id": "BP_TEM_00002018",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs-duffle.pixocial.com/duffle/client/66f2c240-6053-41b5-8a56-04d9ffea9f95.jpeg",
            "color": "",
            "img_ratio": "1080:1080",
            "title": "ooops",
            "cover_video": ""
          },
          {
            "m_id": "BP_TEM_00002007",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs-duffle.pixocial.com/duffle/402911118bd7d2f1d62380498ad8b30b.png",
            "color": "",
            "img_ratio": "1080:1350",
            "title": "seal story",
            "cover_video": ""
          },
          {
            "m_id": "BP_TEM_00002010",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs-duffle.pixocial.com/duffle/client/9f947896-128d-40b8-a106-43fc56458485.jpeg",
            "color": "",
            "img_ratio": "1080:1080",
            "title": "cartoon shine",
            "cover_video": ""
          },
          {
            "m_id": "BP_TEM_00001798",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs-duffle.pixocial.com/duffle/client/901d4854-8d71-4921-aaf2-a91e7d1598e5.jpeg",
            "color": "",
            "img_ratio": "1080:1350",
            "title": "梵高",
            "cover_video": ""
          },
          {
            "m_id": "BP_TEM_00001799",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs-duffle.pixocial.com/duffle/client/b855e7ad-3846-43a6-b582-15ae059f24a4.jpeg",
            "color": "",
            "img_ratio": "1080:1350",
            "title": "向日葵",
            "cover_video": ""
          }
        ],
        "sub": [],
        "cover_img": ""
      },
      {
        "rid": "BP_cat_HPB_00000426",
        "user_status": 1,
        "sub_status": 1,
        "effective_time": {
          "status": 1,
          "info": [
            1666886400,
            1667836799
          ],
          "timezone": {
            "id": "CTT",
            "std_offset": 480
          }
        },
        "type": "HPB",
        "sort": 100007,
        "text_content": {
          "en": {
            "title": "",
            "text": "",
            "color_value": ""
          }
        },
        "text_layer": {
          "en": ""
        },
        "media": {
          "type": "img",
          "url": "https://gcs.beautyplus.com/38810e303dc550160332583a0ad916ec.jpeg",
          "ratio": "680:500"
        },
        "size": "680:500",
        "marvellink": "https://www.beautyplus.com/which-halloween-makeup-is-perfect-for-you/",
        "link_type": 1,
        "abcode": 0,
        "background_color": "",
        "pag": {
          "type": "",
          "url": ""
        },
        "custom_config": [],
        "title": "",
        "subtitle": "",
        "show_title": false,
        "head_img": {
          "url": "",
          "ratio": ""
        },
        "material_content": [],
        "sub": [],
        "cover_img": ""
      },
      {
        "rid": "BP_cat_HPB_00000158",
        "user_status": 1,
        "sub_status": 1,
        "effective_time": {
          "status": 2,
          "info": [
            0,
            0
          ],
          "timezone": {
            "id": "CTT",
            "std_offset": 480
          }
        },
        "type": "HPB_ARR",
        "sort": 100008,
        "text_content": {},
        "text_layer": {},
        "media": {
          "type": "",
          "url": "",
          "ratio": ""
        },
        "size": "",
        "marvellink": "",
        "link_type": 0,
        "abcode": 0,
        "background_color": "",
        "pag": {
          "type": "",
          "url": ""
        },
        "custom_config": [],
        "title": "Autumn Makeup",
        "subtitle": "",
        "show_title": true,
        "head_img": {
          "url": "",
          "ratio": ""
        },
        "material_content": [
          {
            "m_id": "502195",
            "tag": "HOT",
            "is_paid": 1,
            "img": "https://gcs.beautyplus.com/a16c89d5bd97d657c90990a07c3dabb3.png",
            "color": "",
            "img_ratio": "",
            "title": "Summer-Fall",
            "cover_video": ""
          },
          {
            "m_id": "501375",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs.beautyplus.com/2bf1352625928dc9ebe141fe5b44a2ec.jpeg",
            "color": "",
            "img_ratio": "",
            "title": "ApricotBlush",
            "cover_video": ""
          },
          {
            "m_id": "501441",
            "tag": "",
            "is_paid": 0,
            "img": "https://gcs.beautyplus.com/ea43b5b9bf70b35945c21a66279d3ad0.png",
            "color": "",
            "img_ratio": "",
            "title": "DownturnedEyes",
            "cover_video": ""
          },
          {
            "m_id": "501733",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs.beautyplus.com/6a297bafbe7f654b71b3325e0c4e677d.png",
            "color": "",
            "img_ratio": "",
            "title": "Orange soda",
            "cover_video": ""
          },
          {
            "m_id": "502091",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs.beautyplus.com/c38d22fc637eddb297c4ce195ac5584a.jpeg",
            "color": "",
            "img_ratio": "",
            "title": "KR 90's Retro Mu",
            "cover_video": ""
          },
          {
            "m_id": "501554",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs.beautyplus.com/d48505b9182105a57325b5c054d3768c.jpeg",
            "color": "",
            "img_ratio": "",
            "title": "GlitterPinkMakeu",
            "cover_video": ""
          },
          {
            "m_id": "500906",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs.beautyplus.com/ecdd6ff234da2339b5b9a0866e79dafe.jpeg",
            "color": "",
            "img_ratio": "",
            "title": "LightRed Makeup",
            "cover_video": ""
          }
        ],
        "sub": [],
        "cover_img": ""
      },
      {
        "rid": "BP_cat_HPB_00000131",
        "user_status": 1,
        "sub_status": 1,
        "effective_time": {
          "status": 2,
          "info": [
            0,
            0
          ],
          "timezone": {
            "id": "CTT",
            "std_offset": 480
          }
        },
        "type": "HPB",
        "sort": 100012,
        "text_content": {
          "en": {
            "title": "",
            "text": "",
            "color_value": ""
          }
        },
        "text_layer": {
          "en": ""
        },
        "media": {
          "type": "video",
          "url": "https://gcs.beautyplus.com/f9d781d0a695a8b7e13609ac51ea281e.mp4",
          "ratio": ""
        },
        "size": "680:500",
        "marvellink": "beautyplus://p_edit/f_style?content=1STY00000038",
        "link_type": 2,
        "abcode": 0,
        "background_color": "",
        "pag": {
          "type": "",
          "url": ""
        },
        "custom_config": [],
        "title": "",
        "subtitle": "",
        "show_title": false,
        "head_img": {
          "url": "",
          "ratio": ""
        },
        "material_content": [],
        "sub": [],
        "cover_img": ""
      },
      {
        "rid": "BP_cat_HPB_00000362",
        "user_status": 1,
        "sub_status": 1,
        "effective_time": {
          "status": 2,
          "info": [
            0,
            0
          ],
          "timezone": {
            "id": "CTT",
            "std_offset": 480
          }
        },
        "type": "HPB_TEM",
        "sort": 100013,
        "text_content": {},
        "text_layer": {},
        "media": {
          "type": "",
          "url": "",
          "ratio": ""
        },
        "size": "",
        "marvellink": "",
        "link_type": 0,
        "abcode": 0,
        "background_color": "",
        "pag": {
          "type": "",
          "url": ""
        },
        "custom_config": [],
        "title": "Mirror Selfie",
        "subtitle": "💖Feeling the need for a little self love.",
        "show_title": true,
        "head_img": {
          "url": "",
          "ratio": ""
        },
        "material_content": [
          {
            "m_id": "BP_TEM_00002029",
            "tag": "HOT",
            "is_paid": 1,
            "img": "https://gcs-duffle.pixocial.com/duffle/96546890c717bc0d367387b3db70c9e2.jpeg",
            "color": "",
            "img_ratio": "1080:1620",
            "title": "mirror selfie",
            "cover_video": ""
          },
          {
            "m_id": "BP_TEM_00002028",
            "tag": "NEW",
            "is_paid": 1,
            "img": "https://gcs-duffle.pixocial.com/duffle/7e7b84f19e9892ae74fdc92bdccddbad.jpeg",
            "color": "",
            "img_ratio": "1080:1620",
            "title": "mirror selfie",
            "cover_video": ""
          },
          {
            "m_id": "BP_TEM_00001861",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs-duffle.pixocial.com/duffle/client/60e33a41-cd61-40de-a1c7-392a25a4e227.jpeg",
            "color": "",
            "img_ratio": "1080:1350",
            "title": "flexdith",
            "cover_video": ""
          },
          {
            "m_id": "BP_TEM_00001244",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs-duffle.pixocial.com/test/a66d9859-5a58-4c8f-8a91-477c70050ada.jpeg",
            "color": "",
            "img_ratio": "1080:1920",
            "title": "OOTD Frame",
            "cover_video": ""
          },
          {
            "m_id": "BP_TEM_00001673",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs-duffle.pixocial.com/test/9feacc59-0d2d-4645-bac4-13f8b2b4c322.jpeg",
            "color": "",
            "img_ratio": "1080:1920",
            "title": "mirror.lookatme",
            "cover_video": ""
          },
          {
            "m_id": "BP_TEM_00001793",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs-duffle.pixocial.com/duffle/client/a4100f89-360e-4966-b385-9a748b27267e.jpeg",
            "color": "",
            "img_ratio": "1080:1920",
            "title": "diptych babeparis",
            "cover_video": ""
          }
        ],
        "sub": [],
        "cover_img": ""
      },
      {
        "rid": "BP_cat_HPB_00000397",
        "user_status": 1,
        "sub_status": 1,
        "effective_time": {
          "status": 2,
          "info": [
            0,
            0
          ],
          "timezone": {
            "id": "CTT",
            "std_offset": 480
          }
        },
        "type": "HPB_TEM",
        "sort": 100014,
        "text_content": {},
        "text_layer": {},
        "media": {
          "type": "",
          "url": "",
          "ratio": ""
        },
        "size": "",
        "marvellink": "",
        "link_type": 0,
        "abcode": 0,
        "background_color": "",
        "pag": {
          "type": "",
          "url": ""
        },
        "custom_config": [],
        "title": "Album Cover",
        "subtitle": "Make your own album cover",
        "show_title": true,
        "head_img": {
          "url": "",
          "ratio": ""
        },
        "material_content": [
          {
            "m_id": "BP_TEM_00002210",
            "tag": "NEW",
            "is_paid": 1,
            "img": "https://gcs-duffle.pixocial.com/duffle/0e121248ef919ce818ff9274547b9d91.jpeg",
            "color": "",
            "img_ratio": "1080:1080",
            "title": "selfie",
            "cover_video": ""
          },
          {
            "m_id": "BP_TEM_00002165",
            "tag": "NEW",
            "is_paid": 1,
            "img": "https://gcs-duffle.pixocial.com/duffle/700add405dd0262e48d72ff2d17d9805.jpeg",
            "color": "",
            "img_ratio": "1080:1080",
            "title": "Midnight ",
            "cover_video": ""
          },
          {
            "m_id": "BP_TEM_00002131",
            "tag": "NEW",
            "is_paid": 1,
            "img": "https://gcs-duffle.pixocial.com/duffle/client/9cc4551a-8b22-42f5-815c-a9543a5e9bd4.jpeg",
            "color": "",
            "img_ratio": "1080:1080",
            "title": "I LOVE",
            "cover_video": ""
          },
          {
            "m_id": "BP_TEM_00001882",
            "tag": "HOT",
            "is_paid": 1,
            "img": "https://gcs-duffle.pixocial.com/duffle/e759439ed8c8737b0c098bbabca03f86.jpeg",
            "color": "",
            "img_ratio": "1080:1350",
            "title": "shattered glass",
            "cover_video": ""
          },
          {
            "m_id": "BP_TEM_00001816",
            "tag": "HOT",
            "is_paid": 1,
            "img": "https://gcs.beautyplus.com/c68a663ecd7f8b3f16d12fb9b3c051f5.jpeg",
            "color": "",
            "img_ratio": "1080:1080",
            "title": "Super prom girl",
            "cover_video": ""
          },
          {
            "m_id": "BP_TEM_00001974",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs-duffle.pixocial.com/duffle/8da0d2a913d235a1648654b5f56147a2.png",
            "color": "",
            "img_ratio": "1080:1350",
            "title": "Pink Shot",
            "cover_video": ""
          },
          {
            "m_id": "BP_TEM_00001879",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs-duffle.pixocial.com/duffle/client/00ad1dd4-d949-42ac-b16b-7c213497edf0.jpeg",
            "color": "",
            "img_ratio": "1080:1620",
            "title": "PinkVersion",
            "cover_video": ""
          },
          {
            "m_id": "BP_TEM_00001401",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs-duffle.pixocial.com/test/54dbff71-0aaa-4cf1-89f3-9800b9e44a93.jpeg",
            "color": "",
            "img_ratio": "1080:1620",
            "title": "The queen",
            "cover_video": ""
          },
          {
            "m_id": "BP_TEM_00001402",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs-duffle.pixocial.com/test/cec7d68f-07b9-4bdd-aa2c-5457aad199f0.jpeg",
            "color": "",
            "img_ratio": "1080:1620",
            "title": "Midnight ",
            "cover_video": ""
          },
          {
            "m_id": "BP_TEM_00001400",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs-duffle.pixocial.com/test/36615ce3-5099-4b11-84cc-c22a7e2d8c35.jpeg",
            "color": "",
            "img_ratio": "1080:1080",
            "title": "Golden country",
            "cover_video": ""
          },
          {
            "m_id": "BP_TEM_00001301",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs-duffle.pixocial.com/test/0e26e796-07ae-42d8-9827-59cf826d6fb2.jpeg",
            "color": "",
            "img_ratio": "1080:1080",
            "title": "blue wave",
            "cover_video": ""
          }
        ],
        "sub": [],
        "cover_img": ""
      },
      {
        "rid": "BP_cat_HPB_00000334",
        "user_status": 1,
        "sub_status": 3,
        "effective_time": {
          "status": 1,
          "info": [
            1665244800,
            0
          ],
          "timezone": {
            "id": "CTT",
            "std_offset": 480
          }
        },
        "type": "HPB",
        "sort": 100015,
        "text_content": {
          "en": {
            "title": "",
            "text": "",
            "color_value": ""
          }
        },
        "text_layer": {
          "en": ""
        },
        "media": {
          "type": "video",
          "url": "https://gcs.beautyplus.com/6909523344177e586eb8e390a7feba17.mp4",
          "ratio": ""
        },
        "size": "680:500",
        "marvellink": "https://beautyplusvideo.onelink.me/Ukj8/s3zttt28",
        "link_type": 3,
        "abcode": 0,
        "background_color": "",
        "pag": {
          "type": "",
          "url": ""
        },
        "custom_config": [],
        "title": "",
        "subtitle": "",
        "show_title": false,
        "head_img": {
          "url": "",
          "ratio": ""
        },
        "material_content": [],
        "sub": [],
        "cover_img": "https://gcs.beautyplus.com/46b450b02af4c3f76a45eec7b75c2700.jpeg"
      },
      {
        "rid": "BP_cat_HPB_00000363",
        "user_status": 1,
        "sub_status": 1,
        "effective_time": {
          "status": 2,
          "info": [
            0,
            0
          ],
          "timezone": {
            "id": "CTT",
            "std_offset": 480
          }
        },
        "type": "HPB_TEM",
        "sort": 100016,
        "text_content": {},
        "text_layer": {},
        "media": {
          "type": "",
          "url": "",
          "ratio": ""
        },
        "size": "",
        "marvellink": "",
        "link_type": 0,
        "abcode": 0,
        "background_color": "",
        "pag": {
          "type": "",
          "url": ""
        },
        "custom_config": [],
        "title": "Workout Inspo",
        "subtitle": "Workout, sweat, and repeat. 💪",
        "show_title": true,
        "head_img": {
          "url": "",
          "ratio": ""
        },
        "material_content": [
          {
            "m_id": "BP_TEM_00001806",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs-duffle.pixocial.com/duffle/2a9f7718301d3f6683e9ab4a8782455e.jpeg",
            "color": "",
            "img_ratio": "1080:1920",
            "title": "Morning Routine",
            "cover_video": ""
          },
          {
            "m_id": "BP_TEM_00001803",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs-duffle.pixocial.com/duffle/client/24b9d287-d5f4-443d-94bc-6aee1272864c.jpeg",
            "color": "",
            "img_ratio": "1080:1920",
            "title": "YOGA",
            "cover_video": ""
          },
          {
            "m_id": "BP_TEM_00001765",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs-duffle.pixocial.com/duffle/client/954c2af1-9bd2-4caa-bbb6-b88230b27c25.jpeg",
            "color": "",
            "img_ratio": "1080:1920",
            "title": "hustle 01",
            "cover_video": ""
          },
          {
            "m_id": "BP_TEM_00001589",
            "tag": "",
            "is_paid": 0,
            "img": "https://gcs-duffle.pixocial.com/test/3cd486f0-a35f-495d-90f4-b688e300732f.jpeg",
            "color": "",
            "img_ratio": "1080:1350",
            "title": "workout",
            "cover_video": ""
          },
          {
            "m_id": "BP_TEM_00001576",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs-duffle.pixocial.com/test/f7655a6b-1870-4a04-9a20-090622aa5701.jpeg",
            "color": "",
            "img_ratio": "1080:1620",
            "title": "Yoga",
            "cover_video": ""
          },
          {
            "m_id": "BP_TEM_00001231",
            "tag": "",
            "is_paid": 0,
            "img": "https://gcs-duffle.pixocial.com/test/93aea062-37f5-4293-a611-2aae64386e23.jpeg",
            "color": "",
            "img_ratio": "1080:1080",
            "title": "shoulder presses",
            "cover_video": ""
          },
          {
            "m_id": "BP_TEM_00000645",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs-duffle.pixocial.com/test/4f629141-86bf-4e2b-a340-fa377dc40690.jpeg",
            "color": "",
            "img_ratio": "1080:1620",
            "title": "Sports ",
            "cover_video": ""
          },
          {
            "m_id": "BP_TEM_00000650",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs-duffle.pixocial.com/test/8376c9c1-f6ee-4b19-8df7-a1c70929dfa3.jpeg",
            "color": "",
            "img_ratio": "1080:1920",
            "title": "Basketball 3",
            "cover_video": ""
          },
          {
            "m_id": "BP_TEM_00001225",
            "tag": "",
            "is_paid": 0,
            "img": "https://gcs-duffle.pixocial.com/test/20aaf857-c711-42fa-bd0c-a5a25e5bd907.jpeg",
            "color": "",
            "img_ratio": "1080:1920",
            "title": "Abs Workout",
            "cover_video": ""
          },
          {
            "m_id": "BP_TEM_00001766",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs-duffle.pixocial.com/duffle/client/2c77cd64-120a-4212-b7bf-12ad8db53463.jpeg",
            "color": "",
            "img_ratio": "1080:1920",
            "title": "Surfing Triptych",
            "cover_video": ""
          }
        ],
        "sub": [],
        "cover_img": ""
      },
      {
        "rid": "BP_cat_HPB_00000308",
        "user_status": 1,
        "sub_status": 1,
        "effective_time": {
          "status": 2,
          "info": [
            0,
            0
          ],
          "timezone": {
            "id": "CTT",
            "std_offset": 480
          }
        },
        "type": "HPB_STI",
        "sort": 100017,
        "text_content": {},
        "text_layer": {},
        "media": {
          "type": "",
          "url": "",
          "ratio": ""
        },
        "size": "",
        "marvellink": "",
        "link_type": 0,
        "abcode": 0,
        "background_color": "",
        "pag": {
          "type": "",
          "url": ""
        },
        "custom_config": [],
        "title": "Hello Autumn",
        "subtitle": "BeautyPlus X Erin Williams",
        "show_title": true,
        "head_img": {
          "url": "https://gcs.beautyplus.com/01fb2714939171f80525b3197867359b.jpeg",
          "ratio": "500:500"
        },
        "material_content": [
          {
            "m_id": "30044809",
            "tag": "HOT",
            "is_paid": 1,
            "img": "https://gcs.beautyplus.com/09ef2dcdc25335c53b603b170aea5e23.png",
            "color": "#4f3612",
            "img_ratio": "140:140",
            "title": "",
            "cover_video": ""
          },
          {
            "m_id": "30044802",
            "tag": "HOT",
            "is_paid": 1,
            "img": "https://gcs.beautyplus.com/33688c91b56d9d9165635fd75efc79d5.png",
            "color": "#4f3612",
            "img_ratio": "140:140",
            "title": "",
            "cover_video": ""
          },
          {
            "m_id": "30044805",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs.beautyplus.com/c8bcd4b31bc1cdfc3f511171d4f1a6ac.png",
            "color": "#4f3612",
            "img_ratio": "140:140",
            "title": "",
            "cover_video": ""
          },
          {
            "m_id": "30044825",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs.beautyplus.com/b7a5008e80f6ad80a2059531fa062236.png",
            "color": "#4f3612",
            "img_ratio": "140:140",
            "title": "",
            "cover_video": ""
          },
          {
            "m_id": "30044806",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs.beautyplus.com/3178971a7eecf82cd853f5b41b373570.png",
            "color": "#4f3612",
            "img_ratio": "140:140",
            "title": "",
            "cover_video": ""
          },
          {
            "m_id": "30044801",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs.beautyplus.com/ed5bf621ec8dcf8338f78f80238e4599.png",
            "color": "#4f3612",
            "img_ratio": "140:140",
            "title": "",
            "cover_video": ""
          },
          {
            "m_id": "30044814",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs.beautyplus.com/3f9447dd362cd40ba9163edb5596c224.png",
            "color": "#4f3612",
            "img_ratio": "140:140",
            "title": "",
            "cover_video": ""
          },
          {
            "m_id": "30044803",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs.beautyplus.com/497db6e8cae654018e2f6cdbcc567f79.png",
            "color": "#4f3612",
            "img_ratio": "140:140",
            "title": "",
            "cover_video": ""
          },
          {
            "m_id": "30044808",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs.beautyplus.com/20f2022f22f3337d3241401dd11db10f.png",
            "color": "#4f3612",
            "img_ratio": "140:140",
            "title": "",
            "cover_video": ""
          },
          {
            "m_id": "30044816",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs.beautyplus.com/b5798ae32957d210f0d210350a328734.png",
            "color": "#4f3612",
            "img_ratio": "140:140",
            "title": "",
            "cover_video": ""
          },
          {
            "m_id": "30044826",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs.beautyplus.com/09d79558346c91c0199b5b0abea0d21c.png",
            "color": "#4f3612",
            "img_ratio": "140:140",
            "title": "",
            "cover_video": ""
          },
          {
            "m_id": "30044827",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs.beautyplus.com/aa565f2babd0a2cf76f4027f1583e49e.png",
            "color": "#4f3612",
            "img_ratio": "140:140",
            "title": "",
            "cover_video": ""
          },
          {
            "m_id": "30044817",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs.beautyplus.com/89f4049edb9d757c4e395b2bc1a9e2f8.png",
            "color": "#4f3612",
            "img_ratio": "140:140",
            "title": "",
            "cover_video": ""
          },
          {
            "m_id": "30044828",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs.beautyplus.com/4059afb6b8572c48e2c84e34042501f5.png",
            "color": "#4f3612",
            "img_ratio": "140:140",
            "title": "",
            "cover_video": ""
          },
          {
            "m_id": "30044818",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs.beautyplus.com/c86b0844cea4142e5894d22f4e4ae42c.png",
            "color": "#4f3612",
            "img_ratio": "140:140",
            "title": "",
            "cover_video": ""
          },
          {
            "m_id": "30044813",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs.beautyplus.com/d23c3e0baadc49e0deca4c3679190c39.png",
            "color": "#4f3612",
            "img_ratio": "140:140",
            "title": "",
            "cover_video": ""
          },
          {
            "m_id": "30044821",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs.beautyplus.com/ccb181b96f6f07fb6b29684e97234621.png",
            "color": "#4f3612",
            "img_ratio": "140:140",
            "title": "",
            "cover_video": ""
          },
          {
            "m_id": "30044812",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs.beautyplus.com/0313cbee7e7177e8f81bea7dbebe42b2.png",
            "color": "#4f3612",
            "img_ratio": "140:140",
            "title": "",
            "cover_video": ""
          }
        ],
        "sub": [],
        "cover_img": ""
      },
      {
        "rid": "BP_cat_HPB_00000128",
        "user_status": 1,
        "sub_status": 1,
        "effective_time": {
          "status": 2,
          "info": [
            0,
            0
          ],
          "timezone": {
            "id": "CTT",
            "std_offset": 480
          }
        },
        "type": "HPB",
        "sort": 100018,
        "text_content": {
          "en": {
            "title": "",
            "text": "",
            "color_value": ""
          }
        },
        "text_layer": {
          "en": ""
        },
        "media": {
          "type": "video",
          "url": "https://gcs.beautyplus.com/be082391d6b106ca3ba04a961570c015.mp4",
          "ratio": ""
        },
        "size": "680:500",
        "marvellink": "https://h5.mr.meitu.com/2020/sky_h5/?language=en",
        "link_type": 1,
        "abcode": 0,
        "background_color": "",
        "pag": {
          "type": "",
          "url": ""
        },
        "custom_config": [],
        "title": "",
        "subtitle": "",
        "show_title": false,
        "head_img": {
          "url": "",
          "ratio": ""
        },
        "material_content": [],
        "sub": [],
        "cover_img": ""
      },
      {
        "rid": "BP_cat_HPB_00000425",
        "user_status": 1,
        "sub_status": 1,
        "effective_time": {
          "status": 2,
          "info": [
            0,
            0
          ],
          "timezone": {
            "id": "CTT",
            "std_offset": 480
          }
        },
        "type": "HPB_ARR",
        "sort": 100019,
        "text_content": {},
        "text_layer": {},
        "media": {
          "type": "",
          "url": "",
          "ratio": ""
        },
        "size": "",
        "marvellink": "",
        "link_type": 0,
        "abcode": 0,
        "background_color": "",
        "pag": {
          "type": "",
          "url": ""
        },
        "custom_config": [],
        "title": "🐶Pet & I",
        "subtitle": "",
        "show_title": true,
        "head_img": {
          "url": "",
          "ratio": ""
        },
        "material_content": [
          {
            "m_id": "500655",
            "tag": "",
            "is_paid": 0,
            "img": "https://gcs.beautyplus.com/925076d285dcef4f447d09b29d757d9b.png",
            "color": "",
            "img_ratio": "213:284",
            "title": "pumpkin hat/南瓜帽",
            "cover_video": ""
          },
          {
            "m_id": "502385",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs.beautyplus.com/cfb3b3d8b3897b1a94021f8ff46b1f0e.webp",
            "color": "",
            "img_ratio": "260:346",
            "title": "Pet Hamburger",
            "cover_video": ""
          },
          {
            "m_id": "500656",
            "tag": "",
            "is_paid": 0,
            "img": "https://gcs.beautyplus.com/51c30c611ccc1dd045eef2d082239f67.jpeg",
            "color": "",
            "img_ratio": "260:346",
            "title": "小鬼/lil ghost",
            "cover_video": ""
          },
          {
            "m_id": "502050",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs.beautyplus.com/96fc838e704c166b3ad7a24f8d612aac.png",
            "color": "",
            "img_ratio": "260:346",
            "title": "Animal_face",
            "cover_video": ""
          },
          {
            "m_id": "500671",
            "tag": "",
            "is_paid": 0,
            "img": "https://gcs.beautyplus.com/62dbae4af2155bbe74ec05f2dc9a7fd3.jpeg",
            "color": "",
            "img_ratio": "260:346",
            "title": "Halloween-bat",
            "cover_video": ""
          },
          {
            "m_id": "502340",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs.beautyplus.com/25203c75ba3f0cd9bcbee7bbea1ad8d2.png",
            "color": "",
            "img_ratio": "260:346",
            "title": "Watermelon Cap",
            "cover_video": ""
          },
          {
            "m_id": "502287",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs.beautyplus.com/6b3dcfa35eaec05d31715c629601dfa3.png",
            "color": "",
            "img_ratio": "260:346",
            "title": "Bing_DwenDwen",
            "cover_video": ""
          },
          {
            "m_id": "502283",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs.beautyplus.com/737d071a5b7b8af79227e719e232ed91.webp",
            "color": "",
            "img_ratio": "260:346",
            "title": "Plutus cat",
            "cover_video": ""
          },
          {
            "m_id": "502238",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs.beautyplus.com/f56d0c6ae375910be9decb8c77575d15.png",
            "color": "",
            "img_ratio": "260:346",
            "title": "Pet_T_Cap",
            "cover_video": ""
          },
          {
            "m_id": "500966",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs.beautyplus.com/af5c32d6c732289e61f6bdcdf724aa37.png",
            "color": "",
            "img_ratio": "260:346",
            "title": "Pet-FlowerCrown",
            "cover_video": ""
          },
          {
            "m_id": "501728",
            "tag": "",
            "is_paid": 0,
            "img": "https://gcs.beautyplus.com/b40f27658d7f1ea71bf509ab33d8f49b.png",
            "color": "",
            "img_ratio": "260:346",
            "title": "Pet candy hat",
            "cover_video": ""
          },
          {
            "m_id": "500979",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs.beautyplus.com/6edf3d2f01a2458764ded309c5a65d50.png",
            "color": "",
            "img_ratio": "260:346",
            "title": "pet_crown",
            "cover_video": ""
          },
          {
            "m_id": "500637",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs.beautyplus.com/a1f82bf5cd0c835d2a35bac07397b239.png",
            "color": "",
            "img_ratio": "260:346",
            "title": "爱心眼镜玫瑰",
            "cover_video": ""
          },
          {
            "m_id": "500825",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs.beautyplus.com/c8e39465b15ffacd15488d37b29572d6.png",
            "color": "",
            "img_ratio": "260:346",
            "title": "宠物赫本Hepburn Hair",
            "cover_video": ""
          },
          {
            "m_id": "500754",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs.beautyplus.com/537d30dfc57b52c77f4ef2dd44b3b2cb.png",
            "color": "",
            "img_ratio": "260:346",
            "title": "3D_Dinosaur",
            "cover_video": ""
          },
          {
            "m_id": "500665",
            "tag": "",
            "is_paid": 0,
            "img": "https://gcs.beautyplus.com/cc961127c7bf90a54da72c3f0d4126c4.jpeg",
            "color": "",
            "img_ratio": "260:346",
            "title": "海盗船长猫狗",
            "cover_video": ""
          },
          {
            "m_id": "501204",
            "tag": "",
            "is_paid": 0,
            "img": "https://gcs.beautyplus.com/1ca892adbf90c01f0a74af059542b14d.png",
            "color": "",
            "img_ratio": "260:346",
            "title": "pet_nosebear",
            "cover_video": ""
          }
        ],
        "sub": [],
        "cover_img": ""
      },
      {
        "rid": "BP_cat_HPB_00000129",
        "user_status": 1,
        "sub_status": 1,
        "effective_time": {
          "status": 2,
          "info": [
            0,
            0
          ],
          "timezone": {
            "id": "CTT",
            "std_offset": 480
          }
        },
        "type": "HPB",
        "sort": 100021,
        "text_content": {
          "en": {
            "title": "",
            "text": "",
            "color_value": ""
          }
        },
        "text_layer": {
          "en": ""
        },
        "media": {
          "type": "video",
          "url": "https://gcs.beautyplus.com/3c29d7fb99b06962f61898b3d23cac13.mp4",
          "ratio": ""
        },
        "size": "680:500",
        "marvellink": "beautyplus://p_edit/f_firm_auto",
        "link_type": 2,
        "abcode": 0,
        "background_color": "",
        "pag": {
          "type": "",
          "url": ""
        },
        "custom_config": [],
        "title": "",
        "subtitle": "",
        "show_title": false,
        "head_img": {
          "url": "",
          "ratio": ""
        },
        "material_content": [],
        "sub": [],
        "cover_img": ""
      },
      {
        "rid": "BP_cat_HPB_00000075",
        "user_status": 1,
        "sub_status": 1,
        "effective_time": {
          "status": 2,
          "info": [
            0,
            0
          ],
          "timezone": {
            "id": "CTT",
            "std_offset": 480
          }
        },
        "type": "HPB_TEM",
        "sort": 100022,
        "text_content": {},
        "text_layer": {},
        "media": {
          "type": "",
          "url": "",
          "ratio": ""
        },
        "size": "",
        "marvellink": "",
        "link_type": 0,
        "abcode": 0,
        "background_color": "",
        "pag": {
          "type": "",
          "url": ""
        },
        "custom_config": [],
        "title": "Trending Photo Templates",
        "subtitle": "",
        "show_title": true,
        "head_img": {
          "url": "",
          "ratio": ""
        },
        "material_content": [
          {
            "m_id": "BP_TEM_00001906",
            "tag": "HOT",
            "is_paid": 1,
            "img": "https://gcs-duffle.pixocial.com/duffle/client/11c364d2-cf00-4715-892d-f76ce754cacf.jpeg",
            "color": "#E69E79",
            "img_ratio": "1080:1920",
            "title": "September01",
            "cover_video": ""
          },
          {
            "m_id": "BP_TEM_00001879",
            "tag": "HOT",
            "is_paid": 1,
            "img": "https://gcs-duffle.pixocial.com/duffle/client/00ad1dd4-d949-42ac-b16b-7c213497edf0.jpeg",
            "color": "#FFFFFF",
            "img_ratio": "1080:1620",
            "title": "PinkVersion",
            "cover_video": ""
          },
          {
            "m_id": "BP_TEM_00001849",
            "tag": "NEW",
            "is_paid": 1,
            "img": "https://gcs-duffle.pixocial.com/duffle/100631b31338fc94fa03c8b411fbba18.jpeg",
            "color": "#FFFFFF",
            "img_ratio": "1080:1350",
            "title": "Polaroid ",
            "cover_video": ""
          },
          {
            "m_id": "BP_TEM_00001875",
            "tag": "NEW",
            "is_paid": 1,
            "img": "https://gcs-duffle.pixocial.com/duffle/client/06d1ed6c-1c26-42d1-a835-42015c9a721a.jpeg",
            "color": "#FFFFFF",
            "img_ratio": "1080:1350",
            "title": "CutiesLife",
            "cover_video": ""
          },
          {
            "m_id": "BP_TEM_00000782",
            "tag": "",
            "is_paid": 0,
            "img": "https://gcs-duffle.pixocial.com/test/d5b87669-81a9-4512-ba86-e3b4838a877a.jpeg",
            "color": "#FFFFFF",
            "img_ratio": "1080:1080",
            "title": "I love you",
            "cover_video": ""
          },
          {
            "m_id": "BP_TEM_00001851",
            "tag": "NEW",
            "is_paid": 1,
            "img": "https://gcs-duffle.pixocial.com/duffle/client/4aa79df9-fa48-4349-8985-43f57a568b50.jpeg",
            "color": "#FFFFFF",
            "img_ratio": "1080:1350",
            "title": "stay wild",
            "cover_video": ""
          },
          {
            "m_id": "BP_TEM_00001589",
            "tag": "",
            "is_paid": 0,
            "img": "https://gcs-duffle.pixocial.com/test/3cd486f0-a35f-495d-90f4-b688e300732f.jpeg",
            "color": "#FFFFFF",
            "img_ratio": "1080:1350",
            "title": "workout",
            "cover_video": ""
          },
          {
            "m_id": "BP_TEM_00001880",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs-duffle.pixocial.com/duffle/a9bb9be6da2a3029799972983679c277.png",
            "color": "#FFFFFF",
            "img_ratio": "1080:1350",
            "title": "Dragón ",
            "cover_video": ""
          },
          {
            "m_id": "BP_TEM_00001882",
            "tag": "HOT",
            "is_paid": 1,
            "img": "https://gcs-duffle.pixocial.com/duffle/e759439ed8c8737b0c098bbabca03f86.jpeg",
            "color": "#FFFFFF",
            "img_ratio": "1080:1350",
            "title": "shattered glass",
            "cover_video": ""
          },
          {
            "m_id": "BP_TEM_00001492",
            "tag": "",
            "is_paid": 0,
            "img": "https://gcs-duffle.pixocial.com/test/fbf772f1-09c5-4cc2-931f-88da4ac014ff.jpeg",
            "color": "#FFFFFF",
            "img_ratio": "1080:1920",
            "title": "New dish",
            "cover_video": ""
          }
        ],
        "sub": [],
        "cover_img": ""
      },
      {
        "rid": "BP_cat_HPB_00000222",
        "user_status": 1,
        "sub_status": 1,
        "effective_time": {
          "status": 2,
          "info": [
            0,
            0
          ],
          "timezone": {
            "id": "CTT",
            "std_offset": 480
          }
        },
        "type": "HPB_STI",
        "sort": 100023,
        "text_content": {},
        "text_layer": {},
        "media": {
          "type": "",
          "url": "",
          "ratio": ""
        },
        "size": "",
        "marvellink": "",
        "link_type": 0,
        "abcode": 0,
        "background_color": "#f5c0d6",
        "pag": {
          "type": "",
          "url": ""
        },
        "custom_config": [],
        "title": "🎂Hippo's Celebration",
        "subtitle": "BeautyPlus x @minipack_ ",
        "show_title": true,
        "head_img": {
          "url": "https://gcs.beautyplus.com/302c797ac769cf2bbcbc7aba838e3d5f.jpeg",
          "ratio": "500:500"
        },
        "material_content": [
          {
            "m_id": "30045417",
            "tag": "HOT",
            "is_paid": 1,
            "img": "https://gcs.beautyplus.com/2da5023710fbfa583cd3c258ecb1c2ee.png",
            "color": "#f5c0d6",
            "img_ratio": "140:140",
            "title": "",
            "cover_video": ""
          },
          {
            "m_id": "30045401",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs.beautyplus.com/9e52872f67ac523b9ffbea1df5761978.png",
            "color": "#f5c0d6",
            "img_ratio": "140:140",
            "title": "",
            "cover_video": ""
          },
          {
            "m_id": "30045411",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs.beautyplus.com/0970ded85eb683b93ea4c5dcb7cd4967.png",
            "color": "#f5c0d6",
            "img_ratio": "140:140",
            "title": "",
            "cover_video": ""
          },
          {
            "m_id": "30045402",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs.beautyplus.com/25ac6332a98c59006ab177b07acee8be.png",
            "color": "#f5c0d6",
            "img_ratio": "140:140",
            "title": "",
            "cover_video": ""
          },
          {
            "m_id": "30045424",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs.beautyplus.com/b8fcc6a4b4bb1b919564174e91215850.png",
            "color": "#f5c0d6",
            "img_ratio": "140:140",
            "title": "",
            "cover_video": ""
          },
          {
            "m_id": "30045408",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs.beautyplus.com/ed867ff54d93cf35c7a1cd7f59afbeae.png",
            "color": "#f5c0d6",
            "img_ratio": "140:140",
            "title": "",
            "cover_video": ""
          },
          {
            "m_id": "30045406",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs.beautyplus.com/bc8d1f7d690d19fc1674dc26278389ce.png",
            "color": "#f5c0d6",
            "img_ratio": "140:140",
            "title": "",
            "cover_video": ""
          },
          {
            "m_id": "30045410",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs.beautyplus.com/ba33c5ddda8aebfa4fd407ff46a4a8d4.png",
            "color": "#f5c0d6",
            "img_ratio": "140:140",
            "title": "",
            "cover_video": ""
          },
          {
            "m_id": "30045420",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs.beautyplus.com/a7ceace6db4432b683256b06f731fd08.png",
            "color": "#f5c0d6",
            "img_ratio": "140:140",
            "title": "",
            "cover_video": ""
          },
          {
            "m_id": "30045426",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs.beautyplus.com/4e7bc837c1fce45f145d7652f51cea8d.png",
            "color": "#f5c0d6",
            "img_ratio": "140:140",
            "title": "",
            "cover_video": ""
          },
          {
            "m_id": "30045415",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs.beautyplus.com/233ad0c72ce6ea814ab1557d35317f18.png",
            "color": "#f5c0d6",
            "img_ratio": "140:140",
            "title": "",
            "cover_video": ""
          },
          {
            "m_id": "30045409",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs.beautyplus.com/a8034a493c19ef783751e0829dda962c.png",
            "color": "#f5c0d6",
            "img_ratio": "140:140",
            "title": "",
            "cover_video": ""
          }
        ],
        "sub": [],
        "cover_img": ""
      },
      {
        "rid": "BP_cat_HPB_00000157",
        "user_status": 1,
        "sub_status": 1,
        "effective_time": {
          "status": 2,
          "info": [
            0,
            0
          ],
          "timezone": {
            "id": "CTT",
            "std_offset": 480
          }
        },
        "type": "HPB",
        "sort": 100024,
        "text_content": {
          "en": {
            "title": "",
            "text": "",
            "color_value": ""
          }
        },
        "text_layer": {
          "en": ""
        },
        "media": {
          "type": "video",
          "url": "https://gcs.beautyplus.com/3eed2334632cfcd51ec24b349faa3586.mp4",
          "ratio": ""
        },
        "size": "680:500",
        "marvellink": "https://h5.mr.meitu.com/2022/faceswap_h5/?language=en",
        "link_type": 1,
        "abcode": 0,
        "background_color": "",
        "pag": {
          "type": "",
          "url": ""
        },
        "custom_config": [],
        "title": "",
        "subtitle": "",
        "show_title": false,
        "head_img": {
          "url": "",
          "ratio": ""
        },
        "material_content": [],
        "sub": [],
        "cover_img": "https://gcs.beautyplus.com/9ee180556cee35c6ae5f4136a06684dc.jpeg"
      },
      {
        "rid": "BP_cat_HPB_00000161",
        "user_status": 1,
        "sub_status": 1,
        "effective_time": {
          "status": 2,
          "info": [
            0,
            0
          ],
          "timezone": {
            "id": "CTT",
            "std_offset": 480
          }
        },
        "type": "HPB_TEM",
        "sort": 100025,
        "text_content": {},
        "text_layer": {},
        "media": {
          "type": "",
          "url": "",
          "ratio": ""
        },
        "size": "",
        "marvellink": "",
        "link_type": 0,
        "abcode": 0,
        "background_color": "",
        "pag": {
          "type": "",
          "url": ""
        },
        "custom_config": [],
        "title": "Food Templates",
        "subtitle": "",
        "show_title": true,
        "head_img": {
          "url": "",
          "ratio": ""
        },
        "material_content": [
          {
            "m_id": "BP_TEM_00001930",
            "tag": "NEW",
            "is_paid": 1,
            "img": "https://gcs-duffle.pixocial.com/duffle/client/7abd2ee2-b978-4dc5-a85b-f429e7080b65.jpeg",
            "color": "",
            "img_ratio": "1080:1920",
            "title": "brunch",
            "cover_video": ""
          },
          {
            "m_id": "BP_TEM_00001657",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs-duffle.pixocial.com/test/1f27b758-202c-4892-86c8-6a4a646502d9.jpeg",
            "color": "",
            "img_ratio": "1080:1080",
            "title": "Watermelon ",
            "cover_video": ""
          },
          {
            "m_id": "BP_TEM_00001618",
            "tag": "",
            "is_paid": 0,
            "img": "https://gcs-duffle.pixocial.com/test/cdf4ace2-34d2-45e5-9150-7b5bf2cd43a7.jpeg",
            "color": "",
            "img_ratio": "1080:1620",
            "title": "Summer ",
            "cover_video": ""
          },
          {
            "m_id": "BP_TEM_00001490",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs-duffle.pixocial.com/test/ccf0a9b4-ab96-42cd-b46d-78dc01b98447.jpeg",
            "color": "",
            "img_ratio": "1080:1620",
            "title": "have a nice Sunday",
            "cover_video": ""
          },
          {
            "m_id": "BP_TEM_00001519",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs-duffle.pixocial.com/test/67c4830c-88ca-4f9f-875b-de40ef4ae9af.jpeg",
            "color": "",
            "img_ratio": "1080:1350",
            "title": "Ice cream ",
            "cover_video": ""
          },
          {
            "m_id": "BP_TEM_00001492",
            "tag": "",
            "is_paid": 0,
            "img": "https://gcs-duffle.pixocial.com/test/fbf772f1-09c5-4cc2-931f-88da4ac014ff.jpeg",
            "color": "",
            "img_ratio": "1080:1920",
            "title": "New dish",
            "cover_video": ""
          },
          {
            "m_id": "BP_TEM_00001411",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs-duffle.pixocial.com/test/76fd7824-e5ff-4a46-b065-28744eb88ab2.jpeg",
            "color": "",
            "img_ratio": "1080:1350",
            "title": "salad hack",
            "cover_video": ""
          },
          {
            "m_id": "BP_TEM_00001367",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs-duffle.pixocial.com/test/359da44e-0fa3-4a28-8077-95c61bee8d96.jpeg",
            "color": "",
            "img_ratio": "1080:1080",
            "title": "breakfast",
            "cover_video": ""
          },
          {
            "m_id": "BP_TEM_00001358",
            "tag": "",
            "is_paid": 0,
            "img": "https://gcs-duffle.pixocial.com/test/da4674dd-82d2-47cc-8770-bbdf056d0772.jpeg",
            "color": "",
            "img_ratio": "1080:1920",
            "title": "dessert",
            "cover_video": ""
          },
          {
            "m_id": "BP_TEM_00001101",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs-duffle.pixocial.com/test/28eb3a83-0570-423b-bb27-0a764906e79a.jpeg",
            "color": "",
            "img_ratio": "1080:1350",
            "title": "Food documentary ",
            "cover_video": ""
          }
        ],
        "sub": [],
        "cover_img": ""
      },
      {
        "rid": "BP_cat_HPB_00000127",
        "user_status": 1,
        "sub_status": 1,
        "effective_time": {
          "status": 2,
          "info": [
            0,
            0
          ],
          "timezone": {
            "id": "CTT",
            "std_offset": 480
          }
        },
        "type": "HPB",
        "sort": 100026,
        "text_content": {
          "en": {
            "title": "",
            "text": "",
            "color_value": ""
          }
        },
        "text_layer": {
          "en": ""
        },
        "media": {
          "type": "video",
          "url": "https://gcs.beautyplus.com/13f518fdcfe4761a4e39ebc83bffc815.mp4",
          "ratio": ""
        },
        "size": "680:500",
        "marvellink": "beautyplus://p_edit/f_bokeh_auto?content=102",
        "link_type": 2,
        "abcode": 0,
        "background_color": "",
        "pag": {
          "type": "",
          "url": ""
        },
        "custom_config": [],
        "title": "",
        "subtitle": "",
        "show_title": false,
        "head_img": {
          "url": "",
          "ratio": ""
        },
        "material_content": [],
        "sub": [],
        "cover_img": ""
      },
      {
        "rid": "BP_cat_HPB_00000338",
        "user_status": 1,
        "sub_status": 1,
        "effective_time": {
          "status": 1,
          "info": [
            1665417600,
            1703995199
          ],
          "timezone": {
            "id": "CTT",
            "std_offset": 480
          }
        },
        "type": "HPB",
        "sort": 100027,
        "text_content": {
          "en": {
            "title": "",
            "text": "",
            "color_value": ""
          }
        },
        "text_layer": {
          "en": ""
        },
        "media": {
          "type": "img",
          "url": "https://gcs.beautyplus.com/1f986078cb9c0606b3eca9826e521040.jpeg",
          "ratio": "680:500"
        },
        "size": "680:500",
        "marvellink": "https://www.beautyplus.com/business/",
        "link_type": 1,
        "abcode": 0,
        "background_color": "",
        "pag": {
          "type": "",
          "url": ""
        },
        "custom_config": [],
        "title": "",
        "subtitle": "",
        "show_title": false,
        "head_img": {
          "url": "",
          "ratio": ""
        },
        "material_content": [],
        "sub": [],
        "cover_img": ""
      },
      {
        "rid": "BP_cat_HPB_00000160",
        "user_status": 1,
        "sub_status": 1,
        "effective_time": {
          "status": 2,
          "info": [
            0,
            0
          ],
          "timezone": {
            "id": "CTT",
            "std_offset": 480
          }
        },
        "type": "HPB_ARR",
        "sort": 100028,
        "text_content": {},
        "text_layer": {},
        "media": {
          "type": "",
          "url": "",
          "ratio": ""
        },
        "size": "",
        "marvellink": "",
        "link_type": 0,
        "abcode": 0,
        "background_color": "",
        "pag": {
          "type": "",
          "url": ""
        },
        "custom_config": [],
        "title": "Butterflies",
        "subtitle": "",
        "show_title": true,
        "head_img": {
          "url": "",
          "ratio": ""
        },
        "material_content": [
          {
            "m_id": "500785",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs.beautyplus.com/0d900ac4963c1d82c694bcdc0fb84c0f.webp",
            "color": "",
            "img_ratio": "",
            "title": "fly butterflies",
            "cover_video": ""
          },
          {
            "m_id": "501797",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs.beautyplus.com/aff23ed8a9b43474a910f10ebf35f426.png",
            "color": "",
            "img_ratio": "",
            "title": "Autumn butterfly",
            "cover_video": ""
          },
          {
            "m_id": "501495",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs.beautyplus.com/0eabf88ff3123a554cce1531dbe261b3.png",
            "color": "",
            "img_ratio": "",
            "title": "Retro little ang",
            "cover_video": ""
          },
          {
            "m_id": "501427",
            "tag": "",
            "is_paid": 0,
            "img": "https://gcs.beautyplus.com/dd3a1e68836bd52ba7f72c3fafeab564.jpeg",
            "color": "",
            "img_ratio": "",
            "title": "Freckles&Butterf",
            "cover_video": ""
          },
          {
            "m_id": "502098",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs.beautyplus.com/e7cb2597c6b483915d626bfe8471fa7b.png",
            "color": "",
            "img_ratio": "",
            "title": "Glass Butterfly",
            "cover_video": ""
          },
          {
            "m_id": "501161",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs.beautyplus.com/37fa4788b99d751791e98fe5e5dd2e11.png",
            "color": "",
            "img_ratio": "",
            "title": "蝴蝶边框",
            "cover_video": ""
          },
          {
            "m_id": "501717",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs.beautyplus.com/9f0ef63ff378374e7da95daf1830f082.png",
            "color": "",
            "img_ratio": "",
            "title": "Butterfly",
            "cover_video": ""
          },
          {
            "m_id": "501206",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs.beautyplus.com/4f5f114aff372fff17b9277604985afb.jpeg",
            "color": "",
            "img_ratio": "",
            "title": "Vintage flower",
            "cover_video": ""
          },
          {
            "m_id": "502007",
            "tag": "",
            "is_paid": 1,
            "img": "https://gcs.beautyplus.com/d93fb76e6faf129f953de9722ea2da0f.webp",
            "color": "",
            "img_ratio": "",
            "title": "Sakura Butterfli",
            "cover_video": ""
          },
          {
            "m_id": "501307",
            "tag": "",
            "is_paid": 0,
            "img": "https://gcs.beautyplus.com/c53994e8a8924ca59992a36f16f91ee8.jpeg",
            "color": "",
            "img_ratio": "",
            "title": "butterflylight",
            "cover_video": ""
          }
        ],
        "sub": [],
        "cover_img": ""
      },
      {
        "rid": "BP_cat_HPB_00000337",
        "user_status": 1,
        "sub_status": 1,
        "effective_time": {
          "status": 1,
          "info": [
            1665417600,
            1703995199
          ],
          "timezone": {
            "id": "CTT",
            "std_offset": 480
          }
        },
        "type": "HPB",
        "sort": 100029,
        "text_content": {
          "en": {
            "title": "",
            "text": "",
            "color_value": ""
          }
        },
        "text_layer": {
          "en": ""
        },
        "media": {
          "type": "img",
          "url": "https://gcs.beautyplus.com/8bd79082d63992ef2ddb3acd8d810ce3.jpeg",
          "ratio": "750:640"
        },
        "size": "680:500",
        "marvellink": "https://forms.gle/dUNXPDoTAT1eGxJRA",
        "link_type": 1,
        "abcode": 0,
        "background_color": "",
        "pag": {
          "type": "",
          "url": ""
        },
        "custom_config": [],
        "title": "",
        "subtitle": "",
        "show_title": false,
        "head_img": {
          "url": "",
          "ratio": ""
        },
        "material_content": [],
        "sub": [],
        "cover_img": ""
      },
      {
        "rid": "BP_cat_HPB_00000159",
        "user_status": 1,
        "sub_status": 1,
        "effective_time": {
          "status": 2,
          "info": [
            0,
            0
          ],
          "timezone": {
            "id": "CTT",
            "std_offset": 480
          }
        },
        "type": "HPB",
        "sort": 100030,
        "text_content": {
          "en": {
            "title": "",
            "text": "",
            "color_value": ""
          }
        },
        "text_layer": {
          "en": ""
        },
        "media": {
          "type": "img",
          "url": "https://gcs.beautyplus.com/0eba02ef863df20af87e3ebea41a3d20.webp",
          "ratio": "680:500"
        },
        "size": "680:500",
        "marvellink": "https://h5.mr.meitu.com/2020/duang_h5/?language=en",
        "link_type": 1,
        "abcode": 0,
        "background_color": "",
        "pag": {
          "type": "",
          "url": ""
        },
        "custom_config": [],
        "title": "",
        "subtitle": "",
        "show_title": false,
        "head_img": {
          "url": "",
          "ratio": ""
        },
        "material_content": [],
        "sub": [],
        "cover_img": ""
      }
    ]
  },
  "message": "success",
  "update": "a5455e4b8ca0b1b7934b63893228b4f9"
}

```