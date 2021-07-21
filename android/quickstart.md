---
description: >-
  The GeoSpark Android SDK makes it quick and easy to build a location tracker
  for your Android app. We provide powerful and customizable tracking modes and
  features.
---

# Quickstart

## Requirements <a id="Quickstart(Android)-Requirements"></a>

To use the GeoSpark SDK, the following things are required:

* Get yourself a free [GeoSpark Account](https://playground.geospark.co). No credit card required.
* Create a project and add an Android app to the project.
* You need the `SDK_KEY` in your project settings which you’ll need to initialize the SDK.
* Now, you’re ready to integrate the SDK into your Android application. 

The GeoSpark Android SDK requires Android Studio 2.0 or later and is compatible with apps targeting Android SDK Version 16 or above.

## Run the example application

The GeoSpark Example repository on GitHub includes sample apps that demonstrate the use of the v3 GeoSpark SDK for Android.

To run the example app, clone this repository, navigate to the example app in paths `CloudIntegration/`, `Self-ManagedIntegration/` or `Trips/` , and add your publishable "YOUR-SDK-KEY" key in `MainApplication.java`, and run the app.

Make sure the package name is the same as the one registered in our GeoSpark Playground dashboard.

{% embed url="https://github.com/geosparks/geospark-android-sdk-example" %}

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
        url 'https://com-geospark-android.s3.amazonaws.com/'
    }
}
```

add the dependencies below in your `app build.gradle` file.

```javascript
dependencies {
 implementation 'com.geospark.android:geospark:3.1.6'
}
```

Then sync Gradle.

### Manual Installation

[Download](https://s3.amazonaws.com/geospark-frameworks/Android/GeoSpark.zip) and unzip GeoSpark SDK

1. Open Android Studio and add the SDK `GeoSpark.aar` as a module using File &gt; New &gt; New Module &gt; Import .JAR/.AAR Package.
2. Once Gradle is finished click File &gt; Project Structure again.
3. Click on the Dependencies tab &gt; click App &gt; click the “+” icon in the top left in Declared Dependencies section &gt; select Module Dependency &gt; click on GeoSpark-release &gt; press Ok and wait for Gradle to sync again and include the dependencies separately and sync your project.
4. Wait for Gradle to sync again and include the dependencies separately and sync your project.

```java
dependencies {
    implementation 'com.google.android.gms:play-services-location:17.0.0'
    implementation 'com.squareup.retrofit2:retrofit:2.6.2'
    implementation 'com.squareup.retrofit2:converter-gson:2.1.0'
    implementation("com.amazonaws:aws-android-sdk-iot:2.16.+@aar") {
        exclude group: 'org.eclipse.paho', module: 'org.eclipse.paho.client.mqttv3'
        transitive = true
    }
    implementation "org.eclipse.paho:org.eclipse.paho.client.mqttv3:1.2.4"
    implementation('com.amazonaws:aws-android-sdk-mobile-client:2.16.+@aar') { transitive = true }
}
```

## Initialize SDK

Before initializing the SDK, the below must be imported.

```
import com.geospark.lib.GeoSpark;
```

After import, add the below code under the Application class `onCreate()` method. The SDK must be initialised before calling any of the other SDK methods.

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
GeoSpark.initialize(this, "YOUR SDK KEY GOES HERE")
```
{% endtab %}

{% tab title="Java" %}
```java
GeoSpark.initialize(this, "YOUR SDK KEY GOES HERE");
```
{% endtab %}
{% endtabs %}

## Request Permission <a id="Quickstart(Android)-RequestLocationPermission"></a>

 To start tracking the location below Android 10.

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
if (!GeoSpark.checkLocationServices()) {
	GeoSpark.requestLocationServices(this)
} else if (!GeoSpark.checkLocationPermission()) {
	GeoSpark.requestLocationPermission(this)
} else if (Build.VERSION.SDK_INT >= Build.VERSION_CODES.Q && !GeoSpark.checkBackgroundLocationPermission()) {
	GeoSpark.requestBackgroundLocationPermission(this)
} else {
    startTracking()
}
```
{% endtab %}

{% tab title="Java" %}
```java
if (!GeoSpark.checkLocationServices()) {
	GeoSpark.requestLocationServices(this);
} else if (!GeoSpark.checkLocationPermission()) {
	GeoSpark.requestLocationPermission(this);
} else if (Build.VERSION.SDK_INT >= Build.VERSION_CODES.Q && !GeoSpark.checkBackgroundLocationPermission()) {
	GeoSpark.requestBackgroundLocationPermission(this);
} else {
    startTracking()
}
```
{% endtab %}
{% endtabs %}

## Location Tracking <a id="Location-Tracking"></a>

### Start Tracking <a id="Start-Tracking"></a>

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
GeoSpark.startSelfTracking(TrackingMode)
```
{% endtab %}

{% tab title="Java" %}
```java
GeoSpark.startSelfTracking(TrackingMode);
```
{% endtab %}
{% endtabs %}

Use the tracking modes while you use the `GeoSpark.startSelfTracking`  method.

### Stop Tracking <a id="Stop-Tracking"></a>

To stop the tracking use the below method.

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
GeoSpark.stopSelfTracking()
```
{% endtab %}
{% endtabs %}

## Tracking Modes

### Adaptive Tracking

GeoSpark has three default tracking modes along with a custom version. They differ based on the frequency of location updates and battery consumption. The higher the frequency, the higher is the battery consumption. You must use [foreground service](https://developer.android.com/about/versions/oreo/background-location-limits) for continuous tracking.

| **Mode** | **Battery usage** | **Updates every**  | **Optimised for/advised for**  |
| :--- | :--- | :--- | :--- |
| Active  | 6% - 12%  | 25 ~ 250 meters  | Ride Hailing / Sharing |
| Balanced | 3% - 6%  | 50 ~ 500 meters  | On Demand Services |
| Passive | 0% - 1% | 100 ~ 1000 meters  | Social Apps |

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
// active tracking
GeoSpark.startSelfTracking(GeoSparkTrackingMode.ACTIVE)
// balanced tracking
GeoSpark.startSelfTracking(GeoSparkTrackingMode.BALANCED)
// passive tracking
GeoSpark.startSelfTracking(GeoSparkTrackingMode.PASSIVE)
```
{% endtab %}

{% tab title="Java" %}
```java
// active tracking
GeoSpark.startSelfTracking(GeoSparkTrackingMode.ACTIVE);
// balanced tracking
GeoSpark.startSelfTracking(GeoSparkTrackingMode.BALANCED);
// passive tracking
GeoSpark.startSelfTracking(GeoSparkTrackingMode.PASSIVE);
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
//Update location based on distance between locations.
val trackingMode = GeoSparkTrackingMode.Builder("DISTANCE IN METERS", "STATIONARY DURATION IN SECONDS")
                  .setDesiredAccuracy(GeoSparkTrackingMode.DesiredAccuracy.HIGH)
                  .build()
```
{% endtab %}

{% tab title="Java" %}
```java
//Update location based on distance between locations.
GeoSparkTrackingMode trackingMode = new GeoSparkTrackingMode.Builder("DISTANCE IN METERS", "STATIONARY DURATION IN SECONDS")
                        .setDesiredAccuracy(GeoSparkTrackingMode.DesiredAccuracy.HIGH)
                        .build();
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
//Update location based on time interval.
val trackingMode = GeoSparkTrackingMode.Builder("INTERVAL IN SECONDS")
                  .setDesiredAccuracy(GeoSparkTrackingMode.DesiredAccuracy.HIGH)
                  .build()
```
{% endtab %}

{% tab title="Java" %}
```java
//Update location based on time interval.
GeoSparkTrackingMode trackingMode = new GeoSparkTrackingMode.Builder("INTERVAL IN SECONDS")
                        .setDesiredAccuracy(GeoSparkTrackingMode.DesiredAccuracy.HIGH)
                        .build();
```
{% endtab %}
{% endtabs %}

You may see a delay if the user's device is in low power mode or has connectivity issues.

## Location Listener

In order to listen to location updates locally, you can follow the below steps for self tracking.

{% page-ref page="sdk-methods/listeners-and-events.md" %}



