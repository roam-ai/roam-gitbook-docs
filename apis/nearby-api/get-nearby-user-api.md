---
description: >-
  The Get Nearby User API provides the list of users who are currently present
  within the given radius.
---

# Get Nearby User API

{% api-method method="get" host="https://api.geospark.co/v3/" path="api/search/users/" %}
{% api-method-summary %}
Get Nearby User API
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
{% api-method-parameter name="user\_id" type="string" required=false %}
Filters nearby user data for the given user\_id’s last known location.  
**E.g.**- 5d9450ace47bae6d70064a9b
{% endapi-method-parameter %}

{% api-method-parameter name="page\_number" type="integer" required=false %}
Used to look through all pages of data.  
**E.g.**- 1
{% endapi-method-parameter %}

{% api-method-parameter name="radius" type="integer" required=false %}
Search in the radius provided.   
**E.g**.- 10000
{% endapi-method-parameter %}

{% api-method-parameter name="location" type="string" required=false %}
Origin location in \[long, lat\] format.  
**E.g.**- 12.98046, 80.16492
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
        "users": [
            {
                "id": "5f5330d0163d9737ab23899a",
                "app_id": "5ed0e627372279444054d310_2",
                "coordinates": {
                    "type": "Point",
                    "coordinates": [
                        4.897948967438289,
                        52.354913586773314
                    ]
                },
                "activity": "MOVING",
                "battery_remaining": 87,
                "created_at": "2020-09-30T07:25:55.251"
            },
            {
                "id": "5f30d339b36114713d8b610e",
                "app_id": "5ed0e627372279444054d310_2",
                "coordinates": {
                    "type": "Point",
                    "coordinates": [
                        4.892291634692569,
                        52.351104736328125
                    ]
                },
                "activity": "MOVING",
                "battery_remaining": 19,
                "created_at": "2020-08-26T07:29:41.080"
            },
            {
                "id": "5f281dd8b3611402f3f79fe1",
                "app_id": "5ed0e627372279444054d310_2",
                "coordinates": {
                    "type": "Point",
                    "coordinates": [
                        4.891523594247752,
                        52.3529052734375
                    ]
                },
                "activity": "STOP",
                "accuracy": 31.336468528914295,
                "timezone_offset": "+0200",
                "net_stat": true,
                "gps_stat": true,
                "motion_stat": false,
                "app_stat": "BACKGROUND",
                "battery_remaining": 75,
                "bat_stat": "Unplugged",
                "created_at": "2020-08-10T04:09:13.792"
            },
            {
                "id": "5f192614b361140ffbc21d3a",
                "app_id": "5ed0e627372279444054d310_2",
                "coordinates": {
                    "type": "Point",
                    "coordinates": [
                        4.891241524471621,
                        52.352149972864474
                    ]
                },
                "activity": "MOVING",
                "accuracy": 1414.0,
                "timezone_offset": "+0200",
                "net_stat": true,
                "gps_stat": true,
                "motion_stat": false,
                "app_stat": "BACKGROUND",
                "battery_remaining": 58,
                "bat_stat": "Unplugged",
                "created_at": "2020-07-30T18:16:23.085"
            }
        ]
    }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

### Sample Request <a id="NearbyAPI-SampleRequest.1"></a>

```text
curl --location --request GET 'https://api.geospark.co/v3/api/search/users/?user_id=5f2bd1e9b3611421f252e36c&radius=10000' \
--header 'Api-key: 9aab5c7882df4560a3d9418cb69dddef'
```

