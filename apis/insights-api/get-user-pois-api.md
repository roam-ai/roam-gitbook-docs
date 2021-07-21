---
description: >-
  This API will provide the list of insights with boundary coordinates of the
  location, last visited detail, type and confidence for POIs frequently visited
  by the user.
---

# Get User POIs API

{% api-method method="get" host="https://api.roam.ai/v1/" path="api/insights/poi/" %}
{% api-method-summary %}
Get POI Insight API
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
Get POIs for the user.  
**E.g**.- 5d9450ace47bae6d70064a9b
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
        "user_id": "5f30d339b36114713d8b610e",
        "app_id": "5ed0e627372279444054d310_2",
        "insights": [
            {
                "id": "5f3fa9c6b361144e2fbb9500",
                "geometry": {
                    "type": "Polygon",
                    "coordinates": [
                        [
                            [
                                4.909168389987688,
                                52.3609200524679
                            ],
                            ...
                            ...
                            [
                                4.909486939963033,
                                52.360889240887005
                            ]
                        ]
                    ]
                },
                "last_visited": {
                    "id": "5f350a1a23c368e44d9a4854",
                    "coordinates": {
                        "type": "Point",
                        "coordinates": [
                            4.909168389987687,
                            52.36029052734375
                        ]
                    },
                    "accuracy": null,
                    "altitude": -1.8016777038574219,
                    "recorded_at": "2021-06-13T09:38:27.361",
                    "started_at": null,
                    "created_at": "2021-06-13T09:38:34.169"
                },
                "tz_offset": "+0200",
                "confidence": "Medium",
                "type": "road",
                "created_at": "2021-06-21T11:02:28.865"
            },
            {
                "id": "5f3fa9c6b361144e2fbb9501",
                "geometry": {
                    "type": "Polygon",
                    "coordinates": [
                        [
                            [
                                4.893461598938197,
                                52.35548792356163
                            ],
                            [
                                4.893780109757986,
                                52.35545711198083
                            ],
                            ...
                            ...
                            [
                                4.894067441293753,
                                52.355367693412276
                            ]
                        ]
                    ]
                },
                "last_visited": {
                    "id": "5f3bc1fa118fe82b1a623744",
                    "coordinates": {
                        "type": "Point",
                        "coordinates": [
                            4.893461598938197,
                            52.3548583984375
                        ]
                    },
                    "accuracy": null,
                    "altitude": -2.023803234100342,
                    "recorded_at": "2021-06-16T16:23:16.131",
                    "started_at": null,
                    "created_at": "2021-06-18T11:56:42.142"
                },
                "tz_offset": "+0200",
                "confidence": "Medium",
                "type": "residential",
                "created_at": "2021-06-21T11:02:29.710"
            },
            {
                "id": "5f3fa9c6b361144e2fbb9502",
                "geometry": {
                    "type": "Polygon",
                    "coordinates": [
                        [
                            [
                                4.891453618793093,
                                52.35234461301476
                            ],
                            ...
                            ...
                            [
                                4.891772106961156,
                                52.35231380143401
                            ]
                        ]
                    ]
                },
                "last_visited": {
                    "id": "5f38f7a9113938bc6862e138",
                    "coordinates": {
                        "type": "Point",
                        "coordinates": [
                            4.891453618793093,
                            52.351715087890625
                        ]
                    },
                    "accuracy": null,
                    "altitude": 1.5472954213619232,
                    "recorded_at": "2021-06-16T09:08:57.303",
                    "started_at": null,
                    "created_at": "2021-06-16T09:08:57.513"
                },
                "tz_offset": "+0200",
                "confidence": "Medium",
                "type": "house_number",
                "created_at": "2021-06-21T11:02:30.202"
            }
        ]
    }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

### Sample Request <a id="InsightsAPI-SampleRequest.3"></a>

```text
curl --location --request GET 'https://api.roam.ai/v1/api/insights/poi/?user_id=5f30d339b36114713d8b610e' \
--header 'Api-key: ee5b950fdf284474a8727409cd12bb3b'
```

