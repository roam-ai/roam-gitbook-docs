# Get Current Location

Get the current location of the user. You can set the accuracy between 5 to 100 meters \(default is 10\).

{% tabs %}
{% tab title="Swift" %}
```swift
Roam.getCurrentLocation(accuracy) { (location, error) in
    //location?.coordinate.latitude           
    //location?.coordinate.longitude       
    //location?.altitude
    //  error?.code
    //  error?.message 
}
```
{% endtab %}
{% endtabs %}

