---
description: Analyse & resolve your issues.
---

# Troubleshooting

## Requirements

* Android 4.2 \(API level 16\) and above
* Devices that support GPS. Devices with only A-GPS are not supported

## Install SDK Manual

[Download](https://s3.amazonaws.com/geospark-frameworks/Android/GeoSpark.zip) and unzip the GeoSpark SDK.

The package contains an aar file. In Android Studio, add the SDK as a module using `File > New Module > Import .JAR/.AAR Package`**.** Once Gradle is finished, click `File > Project Structure` again. Click on `App`, then `Dependencies` tab, then click the plus icon in the bottom left, select `Module Dependency`, click on GeoSpark, then press Ok and wait for Gradle to sync again and include the dependencies separately and sync your project.

```groovy
dependencies {
    implementation'androidx.work:work-runtime:2.2.0'
    implementation'com.google.android.gms:play-services-location:15.0.1'
    implementation'com.squareup.retrofit2:retrofit:2.6.2'
    implementation'com.google.code.gson:gson:2.8.5'
    implementation'com.squareup.retrofit2:converter-gson:2.1.0'
}
```

## Set up Firebase

If you haven't already, then [add Firebase to your Android project.](https://firebase.google.com/docs/android/setup)

```java
public class MyFireBaseMessagingService extends FirebaseMessagingService {
    @Override
    public void onNewToken(String token) {
        super.onNewToken(token);
        if (token != null) {
             GeoSpark.setDeviceToken(this, token);
        }
    }

    @Override
    public void onMessageReceived(RemoteMessage remoteMessage) {
         super.onMessageReceived(remoteMessage);
         .......
     }
}
```

```java
<application>
  ...
  <service
          android:name=".MyFireBaseMessagingService"
          android:exported="false">
          <intent-filter>
            <action android:name="com.google.firebase.MESSAGING_EVENT"/>
          </intent-filter>
  </service>
  ...
</application>
```

## **Customize Notification**

Android O is coming up with restrictions on background updates, GeoSpark SDK needs use of Foreground service to send location updates. This will not lead to a persistent Foreground notification in the status bar. You can customize small icon and title in this notification.

```java
GeoSpark.setNotificationIconAndText(this, smallIconId, title, content);
```

| Name | Type | Description |
| :--- | :--- | :--- |
| smallIconId | Integer | Resource id for small icon of notification |
| title | String | Title of notification |

