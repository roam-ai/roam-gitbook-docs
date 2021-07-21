# SDK Configuration

## Set Tracking in AppState

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
GeoSpark.setTrackingInAppState(STATE)
```
{% endtab %}

{% tab title="Java" %}
```java
GeoSpark.setTrackingInAppState(STATE);
```
{% endtab %}
{% endtabs %}

<table>
  <thead>
    <tr>
      <th style="text-align:left"><b>Parameter</b>
      </th>
      <th style="text-align:left"><b>Description</b>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">STATE</td>
      <td style="text-align:left">
        <p>GeoSparkTrackingMode.AppState.FOREGROUND (or)</p>
        <p>GeoSparkTrackingMode.AppState.BACKGROUND (or)</p>
        <p>GeoSparkTrackingMode.AppState.ALWAYS_ON</p>
      </td>
    </tr>
  </tbody>
</table>

## Offline Location Tracking <a id="Offline-Location-Tracking"></a>

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
GeoSpark.offlineLocationTracking(Boolean)
```
{% endtab %}

{% tab title="Java" %}
```java
GeoSpark.offlineLocationTracking(Boolean);
```
{% endtab %}
{% endtabs %}

| **Parameter** | **Description** |
| :--- | :--- |
| Boolean | **true** \(default\) -- Offline location enabled. **false** -- Offline location disabled. |

## Allow Mock Location

GeoSpark SDKs **reject** Mock Locations on the device by default.

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
GeoSpark.allowMockLocation(Boolean)
```
{% endtab %}

{% tab title="Java" %}
```java
GeoSpark.allowMockLocation(Boolean);
```
{% endtab %}
{% endtabs %}

<table>
  <thead>
    <tr>
      <th style="text-align:left">Parameter</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">Boolean</td>
      <td style="text-align:left">
        <p><b>false</b> (default) -- Mock location disabled.</p>
        <p><b>true</b> -- Mock location enabled</p>
      </td>
    </tr>
  </tbody>
</table>

## Accuracy Engine

For enabling accuracy engine for Passive, Active, and Balanced tracking

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
GeoSpark.enableAccuracyEngine()
```
{% endtab %}

{% tab title="Java" %}
```
GeoSpark.enableAccuracyEngine();
```
{% endtab %}
{% endtabs %}

For Custom tracking modes, you can pass the desired accuracy values in integer ranging from 1 - 150m.

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
GeoSpark.enableAccuracyEngine("DESIRED-ACCURACY-VALUE")
```
{% endtab %}

{% tab title="Java" %}
```
GeoSpark.enableAccuracyEngine("DESIRED-ACCURACY-VALUE");
```
{% endtab %}
{% endtabs %}

For disabling accuracy engine

{% tabs %}
{% tab title="Kotlin" %}
```kotlin
 GeoSpark.disableAccuracyEngine()
```
{% endtab %}
{% endtabs %}

