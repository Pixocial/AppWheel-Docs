---
sidebar_position: 0
title: Android
id: Android
---

## Android Integration
### Step 1: Create an app

![createAnAppAndroid](/img/integration/createAnAppAndroid.png)
- **App name**: The name of your app
- **Store**: The platform that is divided into Android and iOS, and you should select Android in this case.
- **Google Play package**: The package name of your app, which is the unique identifier of your app in the Google Play Store and can be obtained in the Google Play Console
- **Service Account credentials JSON**: The json file required by the server to verify the order. Before you obtain this file, please confirm that you have completed the necessary configuration for Google payments, which is described in the [Necessary Preparation for AppWheel (Android)](Others/NecessaryPreparationForAppWheel_Android.md). When you have completed the configuration, you will have a json file. Please upload this file to our backend to create your Android app accordingly.

### Step 2: Configuration
#### Notification Receiving Configuration (<font color="red"> **Important: If you have your own receiving server, please refer to the "Configure Notification Receiving Server"**</font>)
To send Google server notifications to AppWheel, please configure the address

![configServerAndroid](/img/integration/configServerAndroid.png)
To Google Cloud Platform,(ensure you can enable [Google Cloud Pub/Sub](https://developer.android.com/google/play/billing/getting-ready#configure-rtdn)）):

![notificationReceivingConfigurationAndroid](/img/integration/notificationReceivingConfigurationAndroid.png)
#### Configure Notification Receiving Server(optional)
▪ If you have your own notification receiving server that needs the push data, you can set the receiving server address in the AppWheel main site. We will send each message once in the order in which the messages arrive, but sometimes the messages may not be delivered in sequence, or will be transmitted multiple times. You should design the program in the way of idempotent processing.

![configServerAndroid](/img/integration/configServerPushAndroid.png)


▪ After the configuration is complete, you can test the availability of the address. The configuration must be consistent with the requirements, that is, accept the request of the POST method, return 200 Http status code after successful processing, and return 400 or 500 status code when processing fails. In addition, because there is no actual business data body in the test, the 200 http status code can be returned when empty data is received.

#### Product Configuration
- There's already a product configuration
- No product configuration

### Step 3: Install the SDK

[SDK Installation](/Installation/Android.md)

[Configuring The SDK](/ConfiguringTheSDK/Android)

[Displaying Products](/DisplayingProducts/Android.md)

[Making Purchases](/MakingPurchases/Android.md)

[Restoring Purchases](/Restoring_Purchases)

[User Benefits](/UserBenefits/Android.md)

[Adding a Global Listener](/Adding_a_Global_Listener)



### Step 4: Acceptance Inspection
- App Configuration Check
- To make sure a notification is configured successfully: Check if the [Google Cloud Pub/Sub](https://cloud.google.com/pubsub) queue has notification settings


![pubSub](/img/integration/pubSub.png)

- The basic configuration is as follows

![androidSetting](/img/integration/androidSetting.png)

- Whether the initialization interface is called at startup
- Whether the AppWheel SDK can get the information of purchased products
- Subscription Products
- In-App Products
- Discount products (optional)
- Single Payment Products
- Recurring Payment Products
- Whether the AppWheel SDK can restore product information