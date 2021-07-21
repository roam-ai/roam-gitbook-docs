---
description: >-
  The Roam Android SDK makes it quick and easy to build a location tracker for
  your Android app. We provide powerful and customizable tracking modes and
  features.
---

# Quickstart

## Requirements <a id="Quickstart(Android)-Requirements"></a>

To use the Roam SDK, the following things are required:

* Get yourself a free [Roam Account](htpps://roam.ai/dashboard/signup). No credit card required.
* Create a project and add an Android app to the project.
* You need the `PUBLISHABLE_KEY` in your project settings which you’ll need to initialize the SDK.
* Now, you’re ready to integrate the SDK into your Android application. 

The Roam Android SDK requires Android Studio 2.0 or later and is compatible with apps targeting Android SDK Version 16 or above.

## Run the example application

The Roam Example repository on GitHub includes sample apps that demonstrate the use of the v3 Roam SDK for Android.

To run the example app, clone this repository, navigate to the example app in paths `Example/`  and add your publishable `YOUR-PUBLISHABLE-KEY` key in `MainApplication.java`, and run the app.

Make sure the `package name` is the same as the one registered in our Roam  dashboard.

{% embed url="https://github.com/roam-ai/roam-android" %}

## Android Studio Setup <a id="Quickstart(Android)-AndroidStudioSetup"></a>

To use the Android SDK in a project, add the SDK as a build dependency and sync the project.

1. Go to Android Studio &gt; New Project &gt; Minimum SDK
2. Select API 16: Android 4.1.0 \(Jelly Bean\) or higher and create a project
3. After you create a new project, open Gradle Scripts &gt; build.gradle \(Project: &lt;your\_project&gt;\) and do the following:
   1. Add the following to the build script {repositories {}} section of the build.gradle \(Project\)file:

      ```text
      mavenCentral()
      ```

Sync and close build.gradle \(Project: &lt;your\_project&gt;\)

## SDK Installation <a id="Quickstart(Android)-GradleInstallation"></a>

### Gradle Installation

Install the SDK to your project via `Gradle` in Android Studio, add the maven below in your `project build.gradle` file.

```text
repositories {
    maven {
        url 'https://com-roam-android.s3.amazonaws.com/'
    }
}
```

add the dependencies below in your `app build.gradle` file.

```javascript
dependencies {
 implementation 'com.roam.sdk:roam-android:0.0.3'
}
```

Then sync Gradle.

### Manual Installation

[Download](https://github.com/roam-ai/roam-android/releases/download/0.0.3/Roam.zip) and unzip Roam SDK

1. Open Android Studio and add the SDK `Roam.aar` as a module using File &gt; New &gt; New Module &gt; Import .JAR/.AAR Package.
2. Once Gradle is finished click File &gt; Project Structure again.
3. Click on the Dependencies tab &gt; click App &gt; click the “+” icon in the top left in Declared Dependencies section &gt; select Module Dependency &gt; click on Roam-release &gt; press Ok and wait for Gradle to sync again and include the dependencies separately and sync your project.
4. Wait for Gradle to sync again and include the dependencies separately and sync your project.

```java
dependencies {
    implementation 'com.google.android.gms:play-services-location:17.0.0'
    implementation 'com.squareup.retrofit2:retrofit:2.6.2'
    implementation 'com.squareup.retrofit2:converter-gson:2.1.0'
    implementation 'org.eclipse.paho:org.eclipse.paho.client.mqttv3:1.2.4'
    implementation 'org.eclipse.paho:org.eclipse.paho.android.service:1.1.1'
}
```

## Initialize SDK

Before initializing the SDK, the below must be imported.

```
import com.roam.sdk.Roam;
```

After import, add the below code under the Application class `onCreate()` method. The SDK must be initialised before calling any of the other SDK methods.

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
Roam.initialize(this, "YOUR-SDK-KEY-GOES-HERE")
```
{% endtab %}

{% tab title="Java" %}
```
Roam.initialize(this, "YOUR-SDK-KEY-GOES-HERE");
```
{% endtab %}
{% endtabs %}

## Request Permission

To request the location for devices running both below/above Android 10.

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
if (!Roam.checkLocationServices()) {
	Roam.requestLocationServices(this)
} else if (!Roam.checkLocationPermission()) {
	Roam.requestLocationPermission(this)
} else if (Build.VERSION.SDK_INT >= Build.VERSION_CODES.Q && !Roam.checkBackgroundLocationPermission()) {
	Roam.requestBackgroundLocationPermission(this)
}
```
{% endtab %}

{% tab title="Java" %}
```java
if (!Roam.checkLocationServices()) {
       Roam.requestLocationServices(this);
} else if (!Roam.checkLocationPermission()) {
       Roam.requestLocationPermission(this);
} else if (Build.VERSION.SDK_INT >= Build.VERSION_CODES.Q && !Roam.checkBackgroundLocationPermission()) {
       Roam.requestBackgroundLocationPermission(this);
}
```
{% endtab %}
{% endtabs %}

## Location Tracking <a id="Location-Tracking"></a>

### Start Tracking <a id="Start-Tracking"></a>

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
Roam.startSelfTracking(TrackingMode)
```
{% endtab %}

{% tab title="Java" %}
```java
Roam.startSelfTracking(TrackingMode);
```
{% endtab %}
{% endtabs %}

Use the tracking modes while you use the `Roam.startSelfTracking`  method.

## Tracking Modes

### Adaptive Tracking

Roam has three default tracking modes along with a custom version. They differ based on the frequency of location updates and battery consumption. The higher the frequency, the higher is the battery consumption. You must use [foreground service](https://developer.android.com/about/versions/oreo/background-location-limits) for continuous tracking.

| **Mode** | **Battery usage** | **Updates every**  | **Optimised for/advised for**  |
| :--- | :--- | :--- | :--- |
| Active  | 6% - 12%  | 25 ~ 250 meters  | Ride Hailing / Sharing |
| Balanced | 3% - 6%  | 50 ~ 500 meters  | On Demand Services |
| Passive | 0% - 1% | 100 ~ 1000 meters  | Social Apps |

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
// active tracking
Roam.startSelfTracking(RoamTrackingMode.ACTIVE)
// balanced tracking
Roam.startSelfTracking(RoamTrackingMode.BALANCED)
// passive tracking
Roam.startSelfTracking(RoamTrackingMode.PASSIVE)
```
{% endtab %}

{% tab title="Java" %}
```java
// active tracking
Roam.startTracking(RoamTrackingMode.ACTIVE);
// balanced tracking
Roam.startTracking(RoamTrackingMode.BALANCED);
// passive tracking
Roam.startTracking(RoamTrackingMode.PASSIVE);
```
{% endtab %}
{% endtabs %}

### Distance Interval Tracking

The SDK also provides a custom tracking mode that allows you to customize and build your own tracking modes.

With distance interval tracking you create a tracking mode with a distance interval in meters of your choice. 

| **Type** | **Unit** | **Unit Range** |
| :--- | :--- | :--- |
| Distance Interval | Meters | 1m ~ 2500m |

**Distance between location updates example code:**

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
// Define a custom tracking method with desired distance interval, stop duration and accuracy
RoamTrackingMode trackingMode = new RoamTrackingMode.Builder(<DISTANCE-FILTER-IN-METERS>, <STOP-INTERVAL-IN-SECONDS>)
                .setDesiredAccuracy(RoamTrackingMode.DesiredAccuracy.HIGH)
                .build()
// Start the tracking with the above created custom tracking method
Roam.startSelfTracking(trackingMode)
```
{% endtab %}

{% tab title="Java" %}
```java
// Define a custom tracking method with desired distance interval, stop duration and accuracy
RoamTrackingMode trackingMode = new RoamTrackingMode.Builder(<DISTANCE-FILTER-IN-METERS>, <STOP-INTERVAL-IN-SECONDS>)
                .setDesiredAccuracy(RoamTrackingMode.DesiredAccuracy.HIGH)
                .build();
// Start the tracking with the above created custom tracking method
Roam.startTracking(trackingMode);
```
{% endtab %}
{% endtabs %}

### **Time Interval Tracking**

With time interval tracking you create a tracking mode with a time interval in seconds of your choice. 

| **Type** | **Unit** | **Unit Range** |
| :--- | :--- | :--- |
| Time Interval | Seconds | 10s ~ 10800s |

**Time between location updates example code:**

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
// Define a custom tracking method with desired time interval and accuracy
RoamTrackingMode trackingMode = new RoamTrackingMode.Builder(<TIME-INTERVAL-IN-SECONDS>)
                .setDesiredAccuracy(RoamTrackingMode.DesiredAccuracy.HIGH)
                .build()
// Start the tracking with the above created custom tracking method
Roam.startSelfTracking(trackingMode)
```
{% endtab %}

{% tab title="Java" %}
```java
// Define a custom tracking method with desired time interval and accuracy
RoamTrackingMode trackingMode = new RoamTrackingMode.Builder(<TIME-INTERVAL-IN-SECONDS>)
                .setDesiredAccuracy(RoamTrackingMode.DesiredAccuracy.HIGH)
                .build();
// Start the tracking with the above created custom tracking method
Roam.startTracking(trackingMode);
```
{% endtab %}
{% endtabs %}

You may see a delay if the user's device is in low power mode or has connectivity issues.

### Stop Tracking <a id="Stop-Tracking"></a>

To stop the tracking use the below method.

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
Roam.stopSelfTracking()
```
{% endtab %}

{% tab title="Java" %}
```
Roam.stopSelfTracking();
```
{% endtab %}
{% endtabs %}

## Location Listeners

Listeners are needed to consume the location or event data from the SDK iteself. In order to enable listerners, the below setps are needed.

To listen to location updates create a class that extends RoamReceiver. Then register the receiver by adding a receiver element to the application element in your manifest.

{% hint style="info" %}
Note: In self tracking, you can listen to only location, error and offline trips status data since the locations are not being sent to our servers for processing events.
{% endhint %}

```markup
<application>
        ...
     <receiver android:name=".LocationReceiver"
                    android:enabled="true"
                    android:exported="false">
         <intent-filter>
         <action android:name="com.roam.android.RECEIVED"/>
         </intent-filter>
     </receiver>
         ...
</application>
```

Then add the code to the receiver.

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
public class LocationReceiver extends RoamReceiver {

    @Override
    public void onLocationUpdated(Context context, RoamLocation roamLocation) {
        super.onLocationUpdated(context, roamLocation);
        // receive own location updates here
	      // do something with location data using location
	      // roamLocation.getLocation().getLatitude() 
	      // roamLocation.getLocation().getLongitude());
    }

    @Override
    public void onError(Context context, RoamError roamError) {
    	// receive error message here
    	// roamError.getMessage());
    }

}
```
{% endtab %}

{% tab title="Java" %}
```java
public class LocationReceiver extends RoamReceiver {

    @Override
    public void onLocationUpdated(Context context, RoamLocation roamLocation) {
        super.onLocationUpdated(context, roamLocation);
        // receive own location updates here
	      // do something with location data using location
	      // roamLocation.getLocation().getLatitude() 
	      // roamLocation.getLocation().getLongitude());
    }

    @Override
    public void onError(Context context, RoamError roamError) {
    	// receive error message here
    	// roamError.getMessage());
    }

}
```
{% endtab %}
{% endtabs %}

