---
description: >-
  This API helps you to get the trip summary of given trip_id with its route,
  distance and duration.Note: distance_covered is in meters and duration is in
  seconds.
---

# Trip Summary API

{% api-method method="get" host="https://api.geospark.co/" path="v3/api/trips/summary/" %}
{% api-method-summary %}
Trip Summary API
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Api-key" type="string" required=true %}
Auth-key  
**E.g**.- 33223kjhdcscijhb5sdbsdmjsdcbj5f
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="trip\_id" type="string" required=true %}
Trip\_id of the trip.  
**E.g.**- 5cd0299d77aebe2d78758d32
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
        "trip_id": "<TRIP-ID>",
        "user_id": "<USER-ID>",
        "project_id": "<PROJECT-ID>",
        "trip_status": "completed",
        "distance_covered": 2938.974,
        "duration": 336,
        "route_indexes": [
            [
                1,
                43
            ],
            [
                44
            ]
        ],
        "route": [
            {
                "coordinates": {
                    "type": "Point",
                    "coordinates": [
                        77.7012468,
                        12.9727756
                    ]
                },
                "altitude": 803.7,
                "activity": "STOP",
                "recorded_at": "2020-08-25T06:01:51.875"
            },
            {
                "coordinates": {
                    "type": "Point",
                    "coordinates": [
                        77.70124362,
                        12.97277827
                    ]
                },
                "altitude": 796.26,
                "activity": "MOVING",
                "recorded_at": "2020-08-25T06:01:54.547"
            },
            {
                "coordinates": {
                    "type": "Point",
                    "coordinates": [
                        77.70124358,
                        12.97277814
                    ]
                },
                "altitude": 796.8,
                "activity": "MOVING",
                "recorded_at": "2020-08-25T06:01:55.668"
            },
            ......
            ......
            {
                "coordinates": {
                    "type": "Point",
                    "coordinates": [
                        77.7007289,
                        12.9736034
                    ]
                },
                "altitude": 807.3,
                "activity": "STOP",
                "recorded_at": "2020-08-25T06:28:57.152"
            }
        ]
    }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

### Sample Request <a id="TripsAPI-SampleRequest.3"></a>

```text
curl --location --request GET 'https://api.geospark.co/v3/api/trips/summary/?trip_id=5f44a2fce289b825457e5497' \
--header 'Api-key: <API-KEY>'
```

