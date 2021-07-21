# SDK Configuration

## Set Tracking in AppState

{% tabs %}
{% tab title="Swift" %}
```swift
Roam.setTrackingInAppState(STATE)
```
{% endtab %}

{% tab title="Objective-C" %}
```objectivec
[Roam setTrackingInAppState:STATE];
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
        <p>RoamTrackingState.Foreground (or)
          <br />RoamTrackingState.Background (or)</p>
        <p>RoamTrackingState.AlwaysOn</p>
      </td>
    </tr>
  </tbody>
</table>

## Offline Location Tracking <a id="Offline-Location-Tracking"></a>

{% tabs %}
{% tab title="Swift" %}
```swift
Roam.offlineLocationTracking(Bool)
```
{% endtab %}

{% tab title="Objective-C" %}
```objectivec
[Roam offlineLocationTracking];
```
{% endtab %}
{% endtabs %}

| **Parameter** | **Description** |
| :--- | :--- |
| Bool | **true** \(default\) -- Offline location enabled. **false** -- Offline location disabled. |

## Accuracy Engine

For enabling accuracy engine for Passive, Active, and Balanced tracking

```text
Roam.enableAccuracyEngine()
```

For Custom tracking mores, you can pass the desired accuracy values in integers ranging from 1-150m.

```text
Roam.enableAccuracyEngine("DESIRED-ACCURACY-VALUE")
```

For disabling accuracy engine

```text
Roam.disableAccuracyEngine()
```

