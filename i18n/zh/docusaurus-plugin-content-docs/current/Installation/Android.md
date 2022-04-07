

### 接入要求： Android SDk 版本 16 及其以上
本SDK托管于Maven，推荐使用gradle安装本SDK
 在project.gradle文件中添加如下代码
 
 ```gradle
 repositories {
    ...
    google()
    jcenter()
}

dependencies {
    ...
    classpath 'com.google.gms:google-services:4.2.0'
}

allprojects {
    repositories {
        google()
        jcenter()
    }
}
 
 ```




在app.gradle文件中添加如下代码

 ```gradle
 
apply plugin: 'com.google.gms.google-services'

implementation 'com.github.pixocial:purchases:1.xxx'
 ```


### 下一步

[配置SDK](/ConfiguringTheSDK/Android.md)