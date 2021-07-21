---
description: Get trip_list API helps to get list of trips based on various parameters.
---

# Get Trip API

{% api-method method="get" host="https://api.roam.ai/v1" path="/api/trips/" %}
{% api-method-summary %}
 Get Trips API
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
Used to get the list of trips assigned to the given user\_id.  
**E.g.**- 5d9450ace47bae6d70064a9b
{% endapi-method-parameter %}

{% api-method-parameter name="start\_date" type="string" required=true %}
Date from when trips need to be returned.  
**E.g.**- 2020-08-15
{% endapi-method-parameter %}

{% api-method-parameter name="end\_date" type="string" required=true %}
Date till when the trip list needs to be returned.  
**E.g.**- 2020-08-20
{% endapi-method-parameter %}

{% api-method-parameter name="trip\_id" type="string" required=false %}
Used to get one particular trip.  
**E.g.**- 5f7d9926e5fc233610297c76
{% endapi-method-parameter %}

{% api-method-parameter name="page\_number" type="integer" required=false %}
Used to traverse through pages of data.  
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
    "data": [
        {
            "id": "5f7d9926e5fc233610297c76",
            "project_id": "5f7d656ae5fc233611297c6c",
            "origins": [
                {
                    "id": "5f7d9926e5fc233610297c77",
                    "trip_id": "5f7d9926e5fc233610297c76",
                    "created_at": "2021-06-07T10:32:06.527",
                    "updated_at": "2021-06-07T10:32:06.538",
                    "coordinates": {
                        "type": "Point",
                        "coordinates": [
                            77.622977,
                            12.917042
                        ]
                    },
                    "loc_type": "origin"
                },
                {
                    "id": "5f7d9926e5fc233610297c78",
                    "trip_id": "5f7d9926e5fc233610297c76",
                    "created_at": "2021-06-07T10:32:06.545",
                    "updated_at": "2021-06-07T10:32:06.552",
                    "coordinates": {
                        "type": "Point",
                        "coordinates": [
                            77.650239,
                            12.924304
                        ]
                    },
                    "loc_type": "origin"
                },
                {
                    "id": "5f7d9926e5fc233610297c79",
                    "trip_id": "5f7d9926e5fc233610297c76",
                    "created_at": "2021-06-07T10:32:06.560",
                    "updated_at": "2021-06-07T10:32:06.571",
                    "coordinates": {
                        "type": "Point",
                        "coordinates": [
                            77.743206,
                            12.954302
                        ]
                    },
                    "loc_type": "origin"
                }
            ],
            "destinations": [
                {
                    "id": "5f7d9926e5fc233610297c7a",
                    "trip_id": "5f7d9926e5fc233610297c76",
                    "created_at": "2021-06-07T10:32:06.578",
                    "updated_at": "2021-06-07T10:32:06.584",
                    "coordinates": {
                        "type": "Point",
                        "coordinates": [
                            78.743206,
                            12.954302
                        ]
                    },
                    "loc_type": "destination"
                }
            ],
            "events": [
                {
                    "id": "5f7d99298fd7a058fbff9ff9",
                    "trip_id": "5f7d9926e5fc233610297c76",
                    "user_id": "5f7d95f1ffb3fb58435309de",
                    "event_type": "geospark:trip:created",
                    "created_at": "2021-06-07T10:32:09.699",
                    "is_deleted": false,
                    "event_source": "geospark:trip",
                    "event_version": "1.0"
                }
            ],
            "user_id": "5f7d95f1ffb3fb58435309de",
            "is_started": false,
            "is_ended": false,
            "is_deleted": false,
            "created_at": "2021-06-07T10:32:06.522",
            "updated_at": "2021-06-07T10:32:06.603"
        }
    ]
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

### Sample Request

```text
curl --location --request GET 'https://api.roam.ai/v1/api/trips/?user_id=5f7d95f1ffb3fb58435309de' \
--header 'Api-key: 4db3d709296a4a518a03bf15f37c55b7' \
--header 'Content-Type: application/json'
```

