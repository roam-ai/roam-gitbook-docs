---
description: >-
  The Get Events API lets you fetch the entry or exit events of the users from
  your event enabled geofences. The API also lets you filter by user or
  geofence, location, and more.
---

# Get Events

{% api-method method="get" host="https://api.geospark.co/v3/" path="api/event/" %}
{% api-method-summary %}
Get Events API
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
Filters events data for the given user\_id.  
**E.g.**- 5d9450ace47bae6d70064a9b
{% endapi-method-parameter %}

{% api-method-parameter name="geofence\_id" type="string" required=false %}
Filters events data for the given geofence\_id.  
**E.g.**- 5eecc7491e621663c93ba2fe
{% endapi-method-parameter %}

{% api-method-parameter name="start\_date" type="string" required=true %}
Filters events data for the given data range.  
**E.g.**- 2020-08-05
{% endapi-method-parameter %}

{% api-method-parameter name="end\_date" type="string" required=true %}
Filters events data for the given date range.  
**E.g.**- 2020-08-09
{% endapi-method-parameter %}

{% api-method-parameter name="page\_number" type="integer" required=false %}
This field can be used for getting 10 entries at a time. if the response returns an empty list in the data field, it is safe to assume the pages are exhausted. If points\_encoded value is true, then this value will not be considered.  
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
        "next_page": 2,
        "pages": 3,
        "prev_page": null,
        "account_id": "5c0179df6f994031158a5646",
        "events": [
            {
                "id": "5f2c03c40401996e6d6c8ad4",
                "user_description": "postman device test",
                "user_id": "5f2be41bb3611421f252e3c3",
                "geofence_description": "365",
                "geofence_id": "5eecc7491e621663c93ba2fe",
                "location_id": "5f2be4ede3872b4e6519f8f2",
                "event_type": "motion:geofence:entry",
                "recorded_at": "2020-08-06T11:09:33.280",
                "created_at": "2020-08-06T13:21:08.283",
                "is_deleted": false
            },
            {
                "id": "5f2be6634fac5ac31f740a09",
                "user_description": "postman device test",
                "user_id": "5f2be3c5b3611421f152e0dc",
                "geofence_description": "365",
                "geofence_id": "5eecc7491e621663c93ba2fe",
                "location_id": "5f2be662e3872b4f0d138e13",
                "event_type": "motion:geofence:entry",
                "recorded_at": "2020-08-06T11:15:46.107",
                "created_at": "2020-08-06T11:15:47.285",
                "is_deleted": false
            },
            {
                "id": "5f2be5ab972cb25c216b8bc8",
                "user_description": "postman device test",
                "user_id": "5f2be41bb3611421f252e3c3",
                "geofence_description": "365",
                "geofence_id": "5eecc7491e621663c93ba2fe",
                "location_id": "5f2be4ede3872b4e6519f8f2",
                "event_type": "motion:geofence:entry",
                "recorded_at": "2020-08-06T11:09:33.280",
                "created_at": "2020-08-06T11:12:43.542",
                "is_deleted": false
            },
            {
                "id": "5f2be4ef4fac5ac31f740a08",
                "user_description": "postman device test",
                "user_id": "5f2be41bb3611421f252e3c3",
                "geofence_description": "365",
                "geofence_id": "5eecc7491e621663c93ba2fe",
                "location_id": "5f2be4ede3872b4e6519f8f2",
                "event_type": "motion:geofence:entry",
                "recorded_at": "2020-08-06T11:09:33.280",
                "created_at": "2020-08-06T11:09:35.655",
                "is_deleted": false
            },
            {
                "id": "5f2be028ad018ed53929605a",
                "user_description": "postman device test",
                "user_id": "5f2bd1e9b3611421f252e36c",
                "geofence_description": "365",
                "geofence_id": "5eecc7491e621663c93ba2fe",
                "location_id": "5f2be027e3872b4b97b61f6d",
                "event_type": "motion:geofence:entry",
                "recorded_at": "2020-08-06T10:49:11.381",
                "created_at": "2020-08-06T10:49:12.636",
                "is_deleted": false
            },
            {
                "id": "5f2bdd15cb6a6dd83389d2fe",
                "user_description": "postman device test",
                "user_id": "5f2bd4cfb3611421f252e378",
                "geofence_description": "365",
                "geofence_id": "5eecc7491e621663c93ba2fe",
                "location_id": "5f2bdd12e3872b49dc215b1f",
                "event_type": "motion:geofence:entry",
                "recorded_at": "2020-08-06T10:36:02.951",
                "created_at": "2020-08-06T10:36:05.404",
                "is_deleted": false
            },
            {
                "id": "5f2bd913b371fa62bad8fda5",
                "user_description": "postman device test",
                "user_id": "5f2bd1e9b3611421f252e36c",
                "geofence_description": "365",
                "geofence_id": "5eecc7491e621663c93ba2fe",
                "location_id": "5f2bd90fe3872b46fe340362",
                "event_type": "motion:geofence:exit",
                "recorded_at": "2020-08-06T10:18:55.914",
                "created_at": "2020-08-06T10:18:59.112",
                "is_deleted": false
            },
            {
                "id": "5f2bd565b371fa62bad8fda2",
                "user_description": "postman device test",
                "user_id": "5f2bd1e9b3611421f252e36c",
                "geofence_description": "365",
                "geofence_id": "5eecc7491e621663c93ba2fe",
                "location_id": "5f2bd562e3872b43e156a54a",
                "event_type": "motion:geofence:entry",
                "recorded_at": "2020-08-06T10:03:14.617",
                "created_at": "2020-08-06T10:03:17.245",
                "is_deleted": false
            },
            {
                "id": "5efc696e8cb244000185ea2d",
                "user_description": "location test device",
                "user_id": "5efc67c6a40ad3095d17be18",
                "geofence_description": "365",
                "geofence_id": "5eecc7491e621663c93ba2fe",
                "location_id": "5efc696ca40ad3095d17be79",
                "app_id": "5e95cbe83722794cf72ea0af_1",
                "event_type": "exit",
                "coordinates": {
                    "type": "Point",
                    "coordinates": [
                        80.08113,
                        12.91806
                    ]
                },
                "recorded_at": "2020-07-01T10:46:03.000",
                "timezone_offset": "+0530",
                "created_at": "2020-07-01T10:46:06.459",
                "is_deleted": false
            },
            {
                "id": "5efc696a8cb244000185ea29",
                "user_description": "location test device",
                "user_id": "5efc67c6a40ad3095d17be18",
                "geofence_description": "365",
                "geofence_id": "5eecc7491e621663c93ba2fe",
                "location_id": "5efc6968a40ad3096417bb5f",
                "app_id": "5e95cbe83722794cf72ea0af_1",
                "event_type": "entry",
                "coordinates": {
                    "type": "Point",
                    "coordinates": [
                        80.08572,
                        12.91959
                    ]
                },
                "recorded_at": "2020-07-01T10:46:00.000",
                "timezone_offset": "+0530",
                "created_at": "2020-07-01T10:46:02.379",
                "is_deleted": false
            }
        ]
    }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

### Sample Request <a id="EventsAPI-SampleRequest"></a>

```text
curl --location --request GET 'https://api.geospark.co/v3/api/event/?geofence_id=5eecc7491e621663c93ba2fe&start_date=2020-08-05&end_date=2020-08-09&page_number=1&user_id=5f2bd1e9b3611421f252e36c&project_id=5e95cbe83722794cf72ea0af' \
--header 'Api-Key: 50ccfe35a1ee409f9791cdee340e5864'
```

