---
description: >-
  To find out the nearest users among the group_id which will passed in url
  along with the Lat/long , radius to get the nearest user to that lat/long.
---

# Find Nearby Users from Group

{% api-method method="get" host="https://api.geospark.co" path="/v3/api/search/users/" %}
{% api-method-summary %}
Find Nearby users from Group
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Api-key" type="string" required=true %}
Auth-key  
**E.g.-** a88d1dddd5ec4be18d7009e0ed4ad59f
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="group\_id" type="string" required=true %}
To search nearest users in group\_id  
**E.g.-** 600959fdffb3fb11b5c66b58
{% endapi-method-parameter %}

{% api-method-parameter name="location" type="string" required=true %}
Origin location in \[lat, long\] format  
**E.g.-** 26.2279164,84.3574425\(lat/long\)
{% endapi-method-parameter %}

{% api-method-parameter name="radius" type="integer" required=false %}
By default radius will 1000 \(meter\)if not provided minimum 100 & maximum 10,000 \(meter\)  
**E.g.-** 500
{% endapi-method-parameter %}

{% api-method-parameter name="page\_number" type="integer" required=false %}
Used to go through all the pages of data  
**E.g.-** 1 
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
    "status": true,
    "msg": "Success.",
    "code": 200,
    "data": {
        "next_page": null,
        "pages": 1,
        "prev_page": null,
        "nearby_users": [
            {
                "app_id": "60094dd8ffb3fb482ec5cdc3_2",
                "location_id": "600a9b476ad038000063d032",
                "coordinates": {
                    "type": "Point",
                    "coordinates": [
                        84.35429382357349,
                        26.226242065573732
                    ]
                },
                "speed": 0.0,
                "altitude": 70.13278198242188,
                "activity": "MOVING",
                "recorded_at": "2021-01-22T09:30:47.584",
                "gps_status": true,
                "battery_remaining": 84,
                "app_context": "F",
                "device_manufacturer": "iPhone",
                "horizontal_accuracy": 2000.0,
                "vertical_accuracy": 16.05297088623047,
                "location_permission": true,
                "os_version": "13.3.1",
                "device_model": "iPhone 11",
                "course": -1.0,
                "created_at": "2021-01-22T09:30:47.828",
                "id": "60095951ffb3fb11b9c66ba6",
                "distance": 365.10736947707176
            },
            {
                "app_id": "60094dd8ffb3fb482ec5cdc3_1",
                "location_id": "600a9b291c65130000f9a4f3",
                "coordinates": {
                    "type": "Point",
                    "coordinates": [
                        84.3533833,
                        26.2266589
                    ]
                },
                "speed": 0.0,
                "altitude": 0.0,
                "activity": "MOVING",
                "recorded_at": "2021-01-22T09:30:17.656",
                "gps_status": true,
                "battery_remaining": 27,
                "airplane_mode": false,
                "app_context": "F",
                "device_manufacturer": "xiaomi",
                "horizontal_accuracy": 1600.0,
                "vertical_accuracy": 0.0,
                "location_permission": true,
                "os_version": "9",
                "device_model": "Redmi Note 7",
                "course": 90.0,
                "created_at": "2021-01-22T09:30:19.306",
                "id": "600a9847ffb3fb1a420702eb",
                "distance": 428.35818534137235
            }
        ]
    }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

### Sample Request <a id="Sample-Request.2"></a>

```text
curl --location --request GET 'https://test.api.geospark.co/v3/api/search/users/?radius=500&location=26.2279164,84.3574425&group_id=600959fdffb3fb11b5c66b58' \
--header 'Api-key: a88d1dddd5ec4be18d7009e0ed4ad59f'
```

