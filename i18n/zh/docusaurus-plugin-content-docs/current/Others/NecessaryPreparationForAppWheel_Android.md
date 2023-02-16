---
sidebar_position: 1
title: AppWheel 必要的前期准备_Android 
id: Necessary preparation for AppWheel_Android
---

## 简介
为了实现AppWheel后台与Google play后台需要进行的一些必要的接口通信。你的应用需要提供一组服务证书给到订阅AppWheel服务后端。下面是应用服务证书的配置步骤。
## 步骤

### 1. 链接到[Google Play Console](https://play.google.com/console)

#### 1.1、打开Settings > Developer account > API access 

![Overall Process](/img/necessaryPreparationForAppWheel_Android/NPA1.jpeg)

 #### 1.2、选择服务账号需要关联的项目

![Overall Process](/img/necessaryPreparationForAppWheel_Android/NPA2.png)


#### 1.3、同意条款与条件

![Overall Process](/img/necessaryPreparationForAppWheel_Android/NPA3.png)

   
### 2. 创建服务账号

#### 2.1、选择Create Service Account

![Overall Process](/img/necessaryPreparationForAppWheel_Android/NPA4.png)

#### 2.2、点击链接到 Google API Console

![Overall Process](/img/necessaryPreparationForAppWheel_Android/NPA5.png)

#### 2.3、Create Service Account

![Overall Process](/img/necessaryPreparationForAppWheel_Android/NPA6.png)

#### 2.4、配置服务账号信息

![Overall Process](/img/necessaryPreparationForAppWheel_Android/NPA7.png)

                
设置Role to Pub/Sub Admin 
![Overall Process](/img/necessaryPreparationForAppWheel_Android/NPA8.png)

 可以直接点击Done跳过可选的第三步
![Overall Process](/img/necessaryPreparationForAppWheel_Android/NPA9.png)

点击<strong>Actions</strong> > <strong>Create key</strong> 生成你的<strong>JSON key</strong>
![Overall Process](/img/necessaryPreparationForAppWheel_Android/NPA10.png)
![Overall Process](/img/necessaryPreparationForAppWheel_Android/NPA11.png)


下载json文件去配置或上传到订阅服务后台
![Overall Process](/img/necessaryPreparationForAppWheel_Android/NPA12.png)


### 3. 授权服务账号

#### 3.1、去Google Play Console授权

![Overall Process](/img/necessaryPreparationForAppWheel_Android/NPA13.png)

#### 3.2、勾选以下权限

![Overall Process](/img/necessaryPreparationForAppWheel_Android/NPA14.png)

#### 3.3、底部点击 Invite User 发送邀请

![Overall Process](/img/necessaryPreparationForAppWheel_Android/NPA15.png)

#### 3.4、将服务账号的权限apply到你的App

在Users and Permissions 部分, 点击前面创建的service account 然后把app添加到这个服务账   
号下面。点击Apply使之生效
![Overall Process](/img/necessaryPreparationForAppWheel_Android/NPA16.png)

### 4.  服务证书配置到订阅AppWheel

将前面从Google Play Console下载下来的json文件配置到订阅AppWheel。

### 5. 获取app端的json文件

- 需要去firebase控制台的[Project settings](https://console.firebase.google.com/project/_/settings/general).
- 选中“Your apps” , 选中需要接入的app的配置.
- 点击 google-services.json.
- 把下载的json文件放到module (app-level) 目录中.

## 配置结果检查

### 1.检查app是否授权成功。

![Overall Process](/img/necessaryPreparationForAppWheel_Android/NPA17.png)

### 2. 等待48小时

完成上面所有配置步骤之后Service Credentials还没有真正生效，因为Google Play方面原因需要等待最多48小时这个 Service Credentials 配置才能真正生效。(<font color="red"> **未生效期间如果AppWheel的SDK发起购买会收到类似invalid credentials 的错误提示"**</font>)

