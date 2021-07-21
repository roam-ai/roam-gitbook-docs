---
description: >-
  The Get Location API provides the list of locations of the users who are using
  your app for a specified project corresponding to the project secret API key
  provided by you.
---

# Get Locations API

{% api-method method="get" host="https://api.roam.ai/v1" path="/api/location/" %}
{% api-method-summary %}
Get Locations API
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Api-key" type="string" required=true %}
Auth-key  
**E.g.**- 33223kjhdcscijhb5sdbsdmjsdcbj5f
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="user\_id" type="string" required=true %}
user\_id for which the locations have to be returned.  
**E.g.**- 5d9450ace47bae6d70064a9b
{% endapi-method-parameter %}

{% api-method-parameter name="start\_date" type="string" required=true %}
Date from when the location is to be fetched.  
**E.g.**- 2021-05-31T18:48:52
{% endapi-method-parameter %}

{% api-method-parameter name="end\_date" type="string" required=false %}
Date till when the location is to be returned.  
**E.g.**- 2021-05-31T18:48:58
{% endapi-method-parameter %}

{% api-method-parameter name="timezone\_offset" type="string" required=false %}
 If the timezone is provided the response will be returned as the provided local timezone.  
If the timezone is not provided, the response will be returned in UTC.  
If points\_encoded value is`true`, then this value will be UTC by default.  
**E.g**.- Asia/Kolkata
{% endapi-method-parameter %}

{% api-method-parameter name="page\_number" type="integer" required=false %}
This field is used for getting 10 entries at a time.   
If the response returns an empty list in the data field, the pages are exhausted.   
If points\_encoded value is`true`, then this value will not be considered.  
**E.g.**- 1
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
        "app_id": "60af306a8ce7db2392eb7a75_1",
        "user_id": "60b90dd651efb070950db2e9",
        "locations": [
            {
                "altitude": -5.697860646978246,
                "speed": 0,
                "vertical_accuracy": 7.07392692565918,
                "horizontal_accuracy": 28.729000091552734,
                "course": 39.287315368652344,
                "tz_offset": "+0530",
                "app_context": "B",
                "network_status": true,
                "battery_status": "unknown",
                "battery_remaining": 75,
                "location_permission": true,
                "tracking_mode": "active",
                "activity": "STOP",
                "address": "Danapur, Dinapur-Cum-Khagaul, Patna, Bihar, 801506, India",
                "coordinates": {
                    "type": "Point",
                    "coordinates": [
                        85.0694115,
                        25.6053059
                    ]
                },
                "created_at": "2021-06-03T17:15:25.614",
                "recorded_at": "2021-06-03T17:15:23.947",
                "id": "60b90e2b56b5e30000c28d45"
            },
            {
                "altitude": -10.507820826362291,
                "speed": 5,
                "vertical_accuracy": 3,
                "horizontal_accuracy": 27.020000457763672,
                "course": 311.1860656738281,
                "tz_offset": "+0530",
                "app_context": "B",
                "network_status": true,
                "battery_status": "unknown",
                "battery_remaining": 75,
                "location_permission": true,
                "tracking_mode": "active",
                "activity": "MOVING",
                "coordinates": {
                    "type": "Point",
                    "coordinates": [
                        85.0694087,
                        25.6053061
                    ]
                },
                "created_at": "2021-06-03T17:14:16.478",
                "recorded_at": "2021-06-03T17:14:11.856",
                "id": "60b90de356b5e30000c28d44"
            },
            {
                "altitude": -10.501007290029905,
                "speed": 9,
                "vertical_accuracy": 3,
                "horizontal_accuracy": 48.900001525878906,
                "course": 128.67137145996094,
                "tz_offset": "+0530",
                "app_context": "B",
                "network_status": true,
                "battery_status": "unknown",
                "battery_remaining": 75,
                "location_permission": true,
                "tracking_mode": "active",
                "activity": "MOVING",
                "coordinates": {
                    "type": "Point",
                    "coordinates": [
                        85.0697134,
                        25.605072
                    ]
                },
                "created_at": "2021-06-03T17:14:11.475",
                "recorded_at": "2021-06-03T17:14:09.901",
                "id": "60b90de156b5e30000c28d43"
            }
        ]
    }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

### Sample Request

```http
curl --location --request GET 'https://api.roam.ai/v1/api/location/?user_id=60b90dd651efb079950db2e9&start_date=2021-06-03T00:00:00' \
--header 'Api-Key: 63598c5b3aa84f14914013709402bbc0'
```

