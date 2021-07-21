---
description: >-
  The Get User API provides the list of users who are using your app
  corresponding to the project secret API key provided.
---

# Get User API

{% api-method method="get" host="https://api.geospark.co/v3" path="/api/user/" %}
{% api-method-summary %}
Get User API
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
{% api-method-parameter name="group\_id" type="string" required=false %}
Used to get the list details of users that belong tot he group\_id
{% endapi-method-parameter %}

{% api-method-parameter name="user\_id" type="string" required=false %}
Used to get the details of one particular user. **Note**: This query param cannot be used along with any other.
{% endapi-method-parameter %}

{% api-method-parameter name="timezone\_offset" type="string" required=false %}
If the timezone is provided the query will be made as per the given timezone.  
**E.g**.- Asia/Kolkata
{% endapi-method-parameter %}

{% api-method-parameter name="start\_date" type="string" required=true %}
Date from when the data is to be returned.  
**E.g**.-  2020-09-10
{% endapi-method-parameter %}

{% api-method-parameter name="end\_date" type="string" required=true %}
Date till when the data is to be returned.  
**E.g.**- 2020-09-13
{% endapi-method-parameter %}

{% api-method-parameter name="page\_number" type="integer" required=false %}
This field is used for getting 10 entries at a time. If the response returns an empty list in the data field, it is safe to assume the pages are exhausted.  
If points\_encoded value is `true`, this value will not be considered.  
**E.g**.- 1
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
        "account_id": "5ede06d73722791c17f27272",
        "users": [
            {
                "id": "60058ad6ffb3fb21c905a0b4",
                "app_id": "5ef070ce1e621663c53bb3c6_2",
                "device_token": "devicetoken",
                "description": "postman device test",
                "brand": "Samsung",
                "model": "S8",
                "os_version": "8.1",
                "sdk_version": "2.1",
                "geofence_events": true,
                "motion_events": false,
                "location_events": false,
                "trips_events": true,
                "nearby_events": false,
                "location_listener": false,
                "event_listener": false,
                "metadata": {
                    "name": "Nikhil"
                },
                "is_deleted": false,
                "created_at": "2021-01-18T13:19:18.181",
                "last_location_update": {}
            }
        ]
    }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

### Sample Request <a id="UsersAPI-SampleRequest"></a>

```text
curl --location --request GET 'https://api.geospark.co/v3/api/user/?start_date=2021-01-18&end_date=2021-01-19' \
--header 'Api-Key: f4441682ed03
```

