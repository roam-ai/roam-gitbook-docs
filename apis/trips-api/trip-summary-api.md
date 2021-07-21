---
description: >-
  This API helps you to get the trip summary of given trip_id with its route,
  distance and duration.Note: distance_covered is in meters and duration is in
  seconds.
---

# Trip Summary API

{% api-method method="get" host="https://api.roam.ai/v1" path="/api/trips/summary/" %}
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
        "trip_id": "60bdebd006f8a03affc5968a",
        "user_id": "60bdebb051efb059ab7daf67",
        "project_id": "60af306a8ce7db2392eb7a75",
        "trip_status": "completed",
        "distance_covered": 129.25,
        "duration": 791,
        "route_indexes": [
            [
                1,
                6
            ],
            [
                7,
                8
            ],
            [
                9,
                10
            ],
            [
                11,
                12
            ],
            [
                13,
                14
            ],
            [
                15,
                16
            ],
            [
                17,
                18
            ],
            [
                19,
                20
            ],
            [
                21,
                22
            ],
            [
                23
            ]
        ],
        "route": [
            {
                "coordinates": {
                    "type": "Point",
                    "coordinates": [
                        85.06944606259113,
                        25.605387669529264
                    ]
                },
                "altitude": 55.26,
                "activity": "STOP",
                "recorded_at": "2021-06-07T09:50:53.344",
                "duration": 0,
                "elevation_gain": 0
            },
            {
                "coordinates": {
                    "type": "Point",
                    "coordinates": [
                        85.06933924413998,
                        25.60538919064786
                    ]
                },
                "altitude": 55.41,
                "activity": "MOVING",
                "recorded_at": "2021-06-07T09:51:17.232",
                "distance": 10.71,
                "duration": 23,
                "elevation_gain": 0
            },
            {
                "coordinates": {
                    "type": "Point",
                    "coordinates": [
                        85.06922514582031,
                        25.60543086974654
                    ]
                },
                "altitude": 55.17,
                "activity": "MOVING",
                "recorded_at": "2021-06-07T09:51:46.472",
                "distance": 23.05,
                "duration": 53,
                "elevation_gain": 0
            },
            {
                "coordinates": {
                    "type": "Point",
                    "coordinates": [
                        85.06934236442666,
                        25.605409750585785
                    ]
                },
                "altitude": 55.1,
                "activity": "MOVING",
                "recorded_at": "2021-06-07T09:51:59.177",
                "distance": 35.04,
                "duration": 65,
                "elevation_gain": 0
            },
            {
                "coordinates": {
                    "type": "Point",
                    "coordinates": [
                        85.06926644486715,
                        25.605338334863347
                    ]
                },
                "altitude": 55.2,
                "activity": "MOVING",
                "recorded_at": "2021-06-07T09:53:26.418",
                "distance": 46.04,
                "duration": 153,
                "elevation_gain": 0
            },
            {
                "coordinates": {
                    "type": "Point",
                    "coordinates": [
                        85.06948839273373,
                        25.60535318995217
                    ]
                },
                "altitude": 55.39,
                "activity": "STOP",
                "recorded_at": "2021-06-07T09:56:55.008",
                "distance": 68.36,
                "duration": 361,
                "elevation_gain": 0
            },
            {
                "coordinates": {
                    "type": "Point",
                    "coordinates": [
                        85.0696403400277,
                        25.605349751588847
                    ]
                },
                "altitude": 55.7,
                "activity": "STOP",
                "recorded_at": "2021-06-07T09:57:06.271",
                "distance": 68.36,
                "duration": 361,
                "elevation_gain": 0
            },
            {
                "coordinates": {
                    "type": "Point",
                    "coordinates": [
                        85.06963043776017,
                        25.60536547480913
                    ]
                },
                "altitude": 55.63,
                "activity": "STOP",
                "recorded_at": "2021-06-07T09:57:17.229",
                "distance": 70.37,
                "duration": 372,
                "elevation_gain": 0
            },
            {
                "coordinates": {
                    "type": "Point",
                    "coordinates": [
                        85.0696539020383,
                        25.605395658660587
                    ]
                },
                "altitude": 55.81,
                "activity": "STOP",
                "recorded_at": "2021-06-07T09:57:30.023",
                "distance": 70.37,
                "duration": 372,
                "elevation_gain": 0
            },
            {
                "coordinates": {
                    "type": "Point",
                    "coordinates": [
                        85.06974352418014,
                        25.60534320757614
                    ]
                },
                "altitude": 55.57,
                "activity": "STOP",
                "recorded_at": "2021-06-07T09:57:53.778",
                "distance": 81.08,
                "duration": 396,
                "elevation_gain": 0
            },
            {
                "coordinates": {
                    "type": "Point",
                    "coordinates": [
                        85.06974881589383,
                        25.605281419845706
                    ]
                },
                "altitude": 55.64,
                "activity": "STOP",
                "recorded_at": "2021-06-07T09:58:09.240",
                "distance": 81.08,
                "duration": 396,
                "elevation_gain": 0
            },
            {
                "coordinates": {
                    "type": "Point",
                    "coordinates": [
                        85.0696629610238,
                        25.60548954876263
                    ]
                },
                "altitude": 55.94,
                "activity": "STOP",
                "recorded_at": "2021-06-07T09:58:25.454",
                "distance": 105.77,
                "duration": 412,
                "elevation_gain": 0
            },
            {
                "coordinates": {
                    "type": "Point",
                    "coordinates": [
                        85.06961812544034,
                        25.6054897625167
                    ]
                },
                "altitude": 55.37,
                "activity": "STOP",
                "recorded_at": "2021-06-07T09:58:33.947",
                "distance": 105.77,
                "duration": 412,
                "elevation_gain": 0
            },
            {
                "coordinates": {
                    "type": "Point",
                    "coordinates": [
                        85.06957021187245,
                        25.605456725096815
                    ]
                },
                "altitude": 55.19,
                "activity": "STOP",
                "recorded_at": "2021-06-07T09:58:49.033",
                "distance": 111.82,
                "duration": 427,
                "elevation_gain": 0
            },
            {
                "coordinates": {
                    "type": "Point",
                    "coordinates": [
                        85.06954017101675,
                        25.60544866085004
                    ]
                },
                "altitude": 55.22,
                "activity": "STOP",
                "recorded_at": "2021-06-07T09:58:57.831",
                "distance": 111.82,
                "duration": 427,
                "elevation_gain": 0
            },
            {
                "coordinates": {
                    "type": "Point",
                    "coordinates": [
                        85.0694966539289,
                        25.605459740246193
                    ]
                },
                "altitude": 55.18,
                "activity": "STOP",
                "recorded_at": "2021-06-07T09:59:11.070",
                "distance": 116.35,
                "duration": 440,
                "elevation_gain": 0
            },
            {
                "coordinates": {
                    "type": "Point",
                    "coordinates": [
                        85.0694966539289,
                        25.605459740246193
                    ]
                },
                "altitude": 55.18,
                "activity": "STOP",
                "recorded_at": "2021-06-07T09:59:22.460",
                "distance": 116.35,
                "duration": 440,
                "elevation_gain": 0
            },
            {
                "coordinates": {
                    "type": "Point",
                    "coordinates": [
                        85.0694966539289,
                        25.605459740246193
                    ]
                },
                "altitude": 55.18,
                "activity": "STOP",
                "recorded_at": "2021-06-07T09:59:35.226",
                "distance": 116.35,
                "duration": 453,
                "elevation_gain": 0
            },
            {
                "coordinates": {
                    "type": "Point",
                    "coordinates": [
                        85.06940685335138,
                        25.605458887846826
                    ]
                },
                "altitude": 55.03,
                "activity": "STOP",
                "recorded_at": "2021-06-07T09:59:47.560",
                "distance": 116.35,
                "duration": 453,
                "elevation_gain": 0
            },
            {
                "coordinates": {
                    "type": "Point",
                    "coordinates": [
                        85.06931932513449,
                        25.605412577919306
                    ]
                },
                "altitude": 55.22,
                "activity": "STOP",
                "recorded_at": "2021-06-07T10:00:29.244",
                "distance": 126.53,
                "duration": 495,
                "elevation_gain": 0
            },
            {
                "coordinates": {
                    "type": "Point",
                    "coordinates": [
                        85.06932052635601,
                        25.605400950443308
                    ]
                },
                "altitude": 55.43,
                "activity": "STOP",
                "recorded_at": "2021-06-07T10:01:43.687",
                "distance": 126.53,
                "duration": 495,
                "elevation_gain": 0
            },
            {
                "coordinates": {
                    "type": "Point",
                    "coordinates": [
                        85.06932052635601,
                        25.605400950443308
                    ]
                },
                "altitude": 55.43,
                "activity": "STOP",
                "recorded_at": "2021-06-07T10:01:56.587",
                "distance": 126.53,
                "duration": 508,
                "elevation_gain": 0
            },
            {
                "coordinates": {
                    "type": "Point",
                    "coordinates": [
                        85.06934078651096,
                        25.605384688483593
                    ]
                },
                "altitude": 55.48,
                "activity": "STOP",
                "recorded_at": "2021-06-07T10:06:40.153",
                "distance": 129.25,
                "duration": 791,
                "elevation_gain": 0
            }
        ],
        "total_elevation_gain": 0
    }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

### Sample Request <a id="TripsAPI-SampleRequest.3"></a>

```text
curl --location --request GET 'https://api.roam.ai/v1/api/trips/summary/?trip_id=60bdiuy006f8a03affc5968a' \
--header 'Api-key: 63598c5b3aa84f14914013700402bbc6'
```

