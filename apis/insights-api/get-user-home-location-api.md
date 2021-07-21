---
description: >-
  This API will provide the list of insights with boundary coordinates of the
  location, last visited detail, type and confidence for the user's home.
---

# Get User Home Location API

{% api-method method="get" host="https://api.geospark.co/v3" path="/api/insights/home/" %}
{% api-method-summary %}
Get Home Insight API
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
{% api-method-parameter name="user\_id" type="string" required=true %}
Get Home location for the user.  
**E.g.**- 5d9450ace47bae6d70064a9b
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
        "home": [
            {
                "id": "5f3fa9c6b361144e2fbb94fe",
                "geometry": {
                    "type": "Polygon",
                    "coordinates": [
                        [
                            [
                                4.891497893193696,
                                52.353609136438145
                            ],
                            ...
                            ...
                            [
                                4.891816390473826,
                                52.353578324857374
                            ]                       
                        ]
                    ]
                },
                "last_visited": {
                    "id": "5f36a5529b3043b3240c2c92",
                    "coordinates": {
                        "type": "Point",
                        "coordinates": [
                            4.891546992613287,
                            52.353057861328125
                        ]
                    },
                    "accuracy": null,
                    "altitude": 1.3552925316616893,
                    "recorded_at": "2020-08-14T14:53:06.320",
                    "started_at": null,
                    "created_at": "2020-08-14T14:53:06.505"
                },
                "tz_offset": "+0200",
                "confidence": "Medium",
                "type": "home",
                "created_at": "2020-08-21T11:02:27.831"
            }
        ]
    }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

### Sample Request <a id="InsightsAPI-SampleRequest.1"></a>

```text
curl --location --request GET 'https://api.geospark.co/v3/api/insights/home/?user_id=5f30d339b36114713d8b610e' \
--header 'Api-key: ee5b950fdf28
```

