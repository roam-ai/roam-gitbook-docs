# SDK Configuration

## Set Tracking in AppState

{% tabs %}
{% tab title="Swift" %}
```swift
GeoSpark.setTrackingInAppState(STATE)
```
{% endtab %}

{% tab title="Objective-C" %}
```objectivec
[GeoSpark setTrackingInAppState:STATE];
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
        <p>GeoSparkTrackingState.Foreground (or)
          <br />GeoSparkTrackingState.Background (or)</p>
        <p>GeoSparkTrackingState.AlwaysOn</p>
      </td>
    </tr>
  </tbody>
</table>

## Offline Location Tracking <a id="Offline-Location-Tracking"></a>

{% tabs %}
{% tab title="Swift" %}
```swift
GeoSpark.offlineLocationTracking(Bool)
```
{% endtab %}

{% tab title="Objective-C" %}
```objectivec
[GeoSpark offlineLocationTracking];
```
{% endtab %}
{% endtabs %}

| **Parameter** | **Description** |
| :--- | :--- |
| Bool | **true** \(default\) -- Offline location enabled. **false** -- Offline location disabled. |

## Accuracy Engine

For enabling accuracy engine for Passive, Active, and Balanced tracking

```text
GeoSpark.enableAccuracyEngine()
```

For Custom tracking mores, you can pass the desired accuracy values in integers ranging from 1-150m.

```text
GeoSpark.enableAccuracyEngine("DESIRED-ACCURACY-VALUE")
```

For disabling accuracy engine

```text
GeoSpark.disableAccuracyEngine()
```

