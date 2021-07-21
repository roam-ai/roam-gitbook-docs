---
description: >-
  This API will provide the list of insights with boundary coordinates of the
  location, last visited detail, type and confidence for the user’s work.
---

# Get User Work Location API

{% api-method method="get" host="https://api.geospark.co/v3/" path="api/insights/work/" %}
{% api-method-summary %}
Get Work Insight API
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
Get Work location for the user.  
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
        "work": [
            {
                "id": "5f3fa9c6b361144e2fbb94ff",
                "geometry": {
                    "type": "Polygon",
                    "coordinates": [
                        [
                            [
                                4.907285075174389,
                                52.36281525332162
                            ],
                            ...
                            ...
                            [
                                4.907603638813551,
                                52.36278444174071
                            ]
                        ]
                    ]
                },
                "last_visited": {
                    "id": "5f3bc1fc118fe82b1a623751",
                    "coordinates": {
                        "type": "Point",
                        "coordinates": [
                            4.907237518324856,
                            52.36199951171875
                        ]
                    },
                    "accuracy": null,
                    "altitude": -0.5668405294418335,
                    "recorded_at": "2020-08-17T08:31:24.594",
                    "started_at": null,
                    "created_at": "2020-08-18T11:56:44.237"
                },
                "tz_offset": "+0200",
                "confidence": "Medium",
                "type": "work",
                "created_at": "2020-08-21T11:02:28.295"
            }
        ]
    }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

### Sample Request <a id="InsightsAPI-SampleRequest.2"></a>

```text
curl --location --request GET 'https://api.geospark.co/v3/api/insights/work/?user_id=5f30d339b36114713d8b610e' \
--header 'Api-key: ee5b950fdf284474a8727409cd12bb3b'
```

