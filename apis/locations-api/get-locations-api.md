---
description: >-
  The Get Location API provides the list of locations of the users who are using
  your app for a specified project corresponding to the project secret API key
  provided by you.
---

# Get Locations API

{% api-method method="get" host="https://api.geospark.co/v3" path="/api/location/" %}
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
        "app_id": "6012750cffb3fb5f8b7a6357_2",
        "user_id": "605adaf0ffb3fb48ea2eb92c",
        "locations": [
            {
                "course": -1,
                "location_permission": true,
                "vertical_accuracy": 2.5521220092941714,
                "tz_offset": "+0530",
                "speed": 0,
                "app_context": "B",
                "battery_remaining": 92,
                "battery_status": "unplugged",
                "horizontal_accuracy": 278,
                "tracking_mode": "active",
                "altitude": 426.68877856027643,
                "network_status": true,
                "activity": "MOVING",
                "coordinates": {
                    "type": "Point",
                    "coordinates": [
                        77.01117712478731,
                        11.052713503082805
                    ]
                },
                "created_at": "2021-05-31T19:25:07.929",
                "recorded_at": "2021-05-31T18:48:57.233",
                "id": "60b52f99d3350c0000796c29"
            },
            {
                "location_permission": true,
                "network_status": true,
                "app_context": "B",
                "course": -1,
                "tz_offset": "+0530",
                "speed": 0,
                "vertical_accuracy": 2.5521220092941714,
                "altitude": 426.68877856027643,
                "tracking_mode": "active",
                "battery_remaining": 92,
                "battery_status": "unplugged",
                "horizontal_accuracy": 278,
                "activity": "MOVING",
                "coordinates": {
                    "type": "Point",
                    "coordinates": [
                        77.01117712478731,
                        11.052713503082805
                    ]
                },
                "created_at": "2021-05-31T19:25:08.132",
                "recorded_at": "2021-05-31T18:48:54.523",
                "id": "60b52f966111b00000897ed8"
            },
            {
                "location_permission": true,
                "network_status": true,
                "app_context": "B",
                "course": -1,
                "speed": 106,
                "tz_offset": "+0530",
                "vertical_accuracy": 2.5521220092941714,
                "altitude": 426.68877856027643,
                "tracking_mode": "active",
                "battery_remaining": 92,
                "battery_status": "unplugged",
                "horizontal_accuracy": 278,
                "activity": "MOVING",
                "coordinates": {
                    "type": "Point",
                    "coordinates": [
                        77.01117712478731,
                        11.052713503082805
                    ]
                },
                "created_at": "2021-05-31T19:25:08.025",
                "recorded_at": "2021-05-31T18:48:52.485",
                "id": "60b52f948165b30000d164f9"
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
curl --location --request GET https://api.geospark.co/v3/api/location/?start_date=2021-05-31T18:48:52&end_date=2021-05-31T18:48:58&user_id=605adaf0ffb3fb48ea2eb92c' \
--header 'Api-Key: xxxxxxxxxxxxxxxxxxxxxxx'
```

