### 首先确保在使用订阅页功能之前，您的app已经接入了AW的支付功能SDK

```
    //aw purchase
    implementation 'com.github.pixocial:purchases:1.0.13.0'
```

### 添加activity
在app层级的AndroidMainifest.xml，里面添加activity

```xml
<activity android:name="com.pixocial.purchases.ui.activity.AWSubscribeActivity" android:theme="@style/Theme.AppCompat.NoActionBar"
            android:screenOrientation="portrait"/>
```

### 支持数据绑定
在app层级的build.gradle中添加dataBinding
```
android {
    ...
    dataBinding {
            enabled = true
        }
}
```