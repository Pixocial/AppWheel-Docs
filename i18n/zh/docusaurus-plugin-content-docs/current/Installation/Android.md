# Android

## 安装
### 说明：
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
