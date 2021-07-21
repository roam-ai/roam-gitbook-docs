---
description: >-
  The Get User API provides the list of users who are using your app
  corresponding to the project secret API key provided.
---

# Get User API

{% api-method method="get" host="https://api.roam.ai/v1" path="/api/user/" %}
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
        "account_id": "60af304c51efb03cdde65042",
        "users": [
            {
                "id": "60b90f1006f8a064fefae2f6",
                "app_id": "60af306a8ce7db2392eb7a75_1",
                "device_token": "d1_nRSCRgMI:APA91bFgVQ8BJqVJsuGF7CbFDfyiMSLgL6c0mW_GHVfeBcjEraRA6lJfreGqKSMzsvNE7ARJn-8V8_mbyL_Bwyy0ScKtjauarg84MyZlgRahszRVPr69-FgdvSx5xi699YGcXz8nfTnb",
                "description": "tiiuhb",
                "brand": "xiaomi",
                "model": "Redmi Note 7",
                "os_version": "28",
                "sdk_version": "3.1.6",
                "device_arn": "arn:aws:sns:us-east-1:218937252071:endpoint/GCM/app_60af306a8ce7db2392eb7a75_1_a678d41d-a66f-442b-90e5-1564b6c88c34/5b73758f-cc96-373a-a2dc-400d8c8f5685",
                "geofence_events": true,
                "motion_events": false,
                "location_events": true,
                "trips_events": true,
                "nearby_events": true,
                "location_listener": true,
                "event_listener": true,
                "is_deleted": false,
                "created_at": "2021-06-03T17:19:12.287",
                "last_location_update": {
                    "id": "60ba01c6498a3c7f94302f90",
                    "location_id": "60b9fffa1409b700002b0a84",
                    "coordinates": {
                        "type": "Point",
                        "coordinates": [
                            85.0689329,
                            25.6052153
                        ]
                    },
                    "speed": 0.0,
                    "altitude": -10.53686590172557,
                    "activity": "MOVING",
                    "recorded_at": "2021-06-04T10:27:06.716",
                    "gps_status": true,
                    "battery_remaining": 59,
                    "app_context": "B",
                    "horizontal_accuracy": 68.4000015258789,
                    "vertical_accuracy": 3.0,
                    "location_permission": true,
                    "course": 241.92620849609375,
                    "source": "HTTPS",
                    "created_at": "2021-06-04T10:34:46.491"
                }
            },
            {
                "id": "60b90eea8ce7db0d651df5fe",
                "app_id": "60af306a8ce7db2392eb7a75_1",
                "device_token": "d1_nRSCRgMI:APA91bFgVQ8BJqVJsuGF7CbFDfyiMSLgL6c0mW_GHVfeBcjEraRA6lJfreGqKSMzsvNE7ARJn-8V8_mbyL_Bwyy0ScKtjauarg84MyZlgRahszRVPr69-FgdvSx5xi699YGcXz8nfTnb",
                "description": "yyy",
                "brand": "xiaomi",
                "model": "Redmi Note 7",
                "os_version": "28",
                "sdk_version": "3.1.6",
                "device_arn": "arn:aws:sns:us-east-1:218937252071:endpoint/GCM/app_60af306a8ce7db2392eb7a75_1_a678d41d-a66f-442b-90e5-1564b6c88c34/5b73758f-cc96-373a-a2dc-400d8c8f5685",
                "geofence_events": true,
                "motion_events": false,
                "location_events": true,
                "trips_events": true,
                "nearby_events": true,
                "location_listener": true,
                "event_listener": true,
                "is_deleted": false,
                "created_at": "2021-06-03T17:18:34.128",
                "last_location_update": {
                    "id": "60b90ef7c97ac210f948652c",
                    "location_id": "60b90ef456b5e30000c28d4d",
                    "coordinates": {
                        "type": "Point",
                        "coordinates": [
                            85.0693901,
                            25.6053019
                        ]
                    },
                    "speed": 0.0,
                    "altitude": -10.436359168943534,
                    "activity": "MOVING",
                    "recorded_at": "2021-06-03T17:18:44.862",
                    "gps_status": true,
                    "battery_remaining": 75,
                    "app_context": "B",
                    "horizontal_accuracy": 12.505999565124512,
                    "vertical_accuracy": 3.0,
                    "location_permission": true,
                    "course": 104.81282806396484,
                    "source": "HTTPS",
                    "created_at": "2021-06-03T17:18:47.092"
                }
            },
            {
                "id": "60b90e9f8ce7db70981df5e8",
                "app_id": "60af306a8ce7db2392eb7a75_1",
                "device_token": "d1_nRSCRgMI:APA91bFgVQ8BJqVJsuGF7CbFDfyiMSLgL6c0mW_GHVfeBcjEraRA6lJfreGqKSMzsvNE7ARJn-8V8_mbyL_Bwyy0ScKtjauarg84MyZlgRahszRVPr69-FgdvSx5xi699YGcXz8nfTnb",
                "description": "ttt",
                "brand": "xiaomi",
                "model": "Redmi Note 7",
                "os_version": "28",
                "sdk_version": "3.1.6",
                "device_arn": "arn:aws:sns:us-east-1:218937252071:endpoint/GCM/app_60af306a8ce7db2392eb7a75_1_a678d41d-a66f-442b-90e5-1564b6c88c34/5b73758f-cc96-373a-a2dc-400d8c8f5685",
                "geofence_events": true,
                "motion_events": false,
                "location_events": true,
                "trips_events": true,
                "nearby_events": true,
                "location_listener": true,
                "event_listener": true,
                "is_deleted": false,
                "created_at": "2021-06-03T17:17:19.612",
                "last_location_update": {
                    "id": "60b90ee0c97ac210f94862d2",
                    "location_id": "60b90ed856b5e30000c28d4a",
                    "coordinates": {
                        "type": "Point",
                        "coordinates": [
                            85.0693876,
                            25.6053024
                        ]
                    },
                    "speed": 0.0,
                    "altitude": -10.454078130984048,
                    "activity": "MOVING",
                    "recorded_at": "2021-06-03T17:18:16.317",
                    "gps_status": true,
                    "battery_remaining": 75,
                    "app_context": "B",
                    "horizontal_accuracy": 3.802000045776367,
                    "vertical_accuracy": 3.0,
                    "location_permission": true,
                    "course": 126.63764190673828,
                    "source": "HTTPS",
                    "created_at": "2021-06-03T17:18:24.413"
                }
            },
            {
                "id": "60b90e778ce7db0d651df5c1",
                "app_id": "60af306a8ce7db2392eb7a75_1",
                "device_token": "d1_nRSCRgMI:APA91bFgVQ8BJqVJsuGF7CbFDfyiMSLgL6c0mW_GHVfeBcjEraRA6lJfreGqKSMzsvNE7ARJn-8V8_mbyL_Bwyy0ScKtjauarg84MyZlgRahszRVPr69-FgdvSx5xi699YGcXz8nfTnb",
                "description": "ravi",
                "brand": "xiaomi",
                "model": "Redmi Note 7",
                "os_version": "28",
                "sdk_version": "3.1.6",
                "device_arn": "arn:aws:sns:us-east-1:218937252071:endpoint/GCM/app_60af306a8ce7db2392eb7a75_1_a678d41d-a66f-442b-90e5-1564b6c88c34/5b73758f-cc96-373a-a2dc-400d8c8f5685",
                "geofence_events": true,
                "motion_events": false,
                "location_events": true,
                "trips_events": true,
                "nearby_events": true,
                "location_listener": true,
                "event_listener": true,
                "is_deleted": false,
                "created_at": "2021-06-03T17:16:39.652",
                "last_location_update": {
                    "id": "60b90e8bc97ac210f9485a9c",
                    "location_id": "60b90e8856b5e30000c28d47",
                    "coordinates": {
                        "type": "Point",
                        "coordinates": [
                            85.069405,
                            25.6053002
                        ]
                    },
                    "speed": 0.0,
                    "altitude": -10.697812527899808,
                    "activity": "MOVING",
                    "recorded_at": "2021-06-03T17:16:56.886",
                    "gps_status": true,
                    "battery_remaining": 75,
                    "app_context": "B",
                    "horizontal_accuracy": 13.935999870300293,
                    "vertical_accuracy": 3.0,
                    "location_permission": true,
                    "course": 289.4035949707031,
                    "source": "HTTPS",
                    "created_at": "2021-06-03T17:16:59.408"
                }
            },
            {
                "id": "60b90dd651efb070950db2e9",
                "app_id": "60af306a8ce7db2392eb7a75_1",
                "device_token": "d1_nRSCRgMI:APA91bFgVQ8BJqVJsuGF7CbFDfyiMSLgL6c0mW_GHVfeBcjEraRA6lJfreGqKSMzsvNE7ARJn-8V8_mbyL_Bwyy0ScKtjauarg84MyZlgRahszRVPr69-FgdvSx5xi699YGcXz8nfTnb",
                "description": "raj",
                "brand": "xiaomi",
                "model": "Redmi Note 7",
                "os_version": "28",
                "sdk_version": "3.1.6",
                "device_arn": "arn:aws:sns:us-east-1:218937252071:endpoint/GCM/app_60af306a8ce7db2392eb7a75_1_a678d41d-a66f-442b-90e5-1564b6c88c34/5b73758f-cc96-373a-a2dc-400d8c8f5685",
                "geofence_events": true,
                "motion_events": false,
                "location_events": true,
                "trips_events": true,
                "nearby_events": true,
                "location_listener": true,
                "event_listener": true,
                "is_deleted": false,
                "created_at": "2021-06-03T17:13:58.830",
                "last_location_update": {
                    "id": "60b90e2dc97ac210f94851b8",
                    "location_id": "60b90e2b56b5e30000c28d45",
                    "coordinates": {
                        "type": "Point",
                        "coordinates": [
                            85.0694115,
                            25.6053059
                        ]
                    },
                    "speed": 0.0,
                    "altitude": -5.697860646978246,
                    "activity": "STOP",
                    "recorded_at": "2021-06-03T17:15:23.947",
                    "gps_status": true,
                    "battery_remaining": 75,
                    "app_context": "B",
                    "horizontal_accuracy": 28.729000091552734,
                    "vertical_accuracy": 7.07392692565918,
                    "location_permission": true,
                    "course": 39.287315368652344,
                    "source": "HTTPS",
                    "created_at": "2021-06-03T17:15:25.614"
                }
            },
            {
                "id": "60b90c688ce7db709c1df98a",
                "app_id": "60af306a8ce7db2392eb7a75_1",
                "device_token": "d1_nRSCRgMI:APA91bFgVQ8BJqVJsuGF7CbFDfyiMSLgL6c0mW_GHVfeBcjEraRA6lJfreGqKSMzsvNE7ARJn-8V8_mbyL_Bwyy0ScKtjauarg84MyZlgRahszRVPr69-FgdvSx5xi699YGcXz8nfTnb",
                "description": "nikhil",
                "brand": "xiaomi",
                "model": "Redmi Note 7",
                "os_version": "28",
                "sdk_version": "3.1.6",
                "device_arn": "arn:aws:sns:us-east-1:218937252071:endpoint/GCM/app_60af306a8ce7db2392eb7a75_1_a678d41d-a66f-442b-90e5-1564b6c88c34/5b73758f-cc96-373a-a2dc-400d8c8f5685",
                "geofence_events": true,
                "motion_events": false,
                "location_events": true,
                "trips_events": true,
                "nearby_events": true,
                "location_listener": true,
                "event_listener": true,
                "is_deleted": false,
                "created_at": "2021-06-03T17:07:52.086",
                "last_location_update": {
                    "id": "60b90dd2a742058ec1fa4de1",
                    "location_id": "60b90dce56b5e30000c28d42",
                    "coordinates": {
                        "type": "Point",
                        "coordinates": [
                            85.0693941,
                            25.6053027
                        ]
                    },
                    "speed": 0.0,
                    "altitude": -10.587453258919219,
                    "activity": "MOVING",
                    "recorded_at": "2021-06-03T17:13:50.867",
                    "gps_status": true,
                    "battery_remaining": 75,
                    "app_context": "B",
                    "horizontal_accuracy": 4.288000106811523,
                    "vertical_accuracy": 3.0,
                    "location_permission": true,
                    "course": 121.61729431152344,
                    "source": "HTTPS",
                    "created_at": "2021-06-03T17:13:54.377"
                }
            },
            {
                "id": "60b89cd706f8a06fb1fae098",
                "app_id": "60af306a8ce7db2392eb7a75_1",
                "device_token": "cyv7qo-5XDw:APA91bGFPNoHCmY26ckS34g4qze0Y6J6EQPNq2fsQyStd4oU6-dZTKjJ5PvxWEGtHFl6YVpk5wbBgXBbsNzCcG4uwWfhMCFtw3zT5n2NgBEL55XwVE0gmfx7CprmJkZCZDi3mbl_9kcW",
                "device_uuid": "03611b89-b17a-4c75-bde1-86f7411df774",
                "description": "ram",
                "brand": "xiaomi",
                "model": "Redmi Note 7",
                "os_version": "28",
                "sdk_version": "3.1.3",
                "device_arn": "arn:aws:sns:us-east-1:218937252071:endpoint/GCM/app_60af306a8ce7db2392eb7a75_1_a678d41d-a66f-442b-90e5-1564b6c88c34/81c4df96-3e2e-3592-a9a7-fd96e1092d1f",
                "geofence_events": true,
                "motion_events": false,
                "location_events": true,
                "trips_events": true,
                "nearby_events": true,
                "location_listener": true,
                "event_listener": true,
                "is_deleted": false,
                "created_at": "2021-06-03T09:11:51.516",
                "last_location_update": {
                    "id": "60b90c03a742058ec1fa1d2c",
                    "location_id": "60b90c0156b5e30000628b90",
                    "coordinates": {
                        "type": "Point",
                        "coordinates": [
                            85.0693781,
                            25.6053302
                        ]
                    },
                    "speed": 3.0,
                    "altitude": -10.6220032343052,
                    "activity": "MOVING",
                    "recorded_at": "2021-06-03T17:06:09.865",
                    "gps_status": false,
                    "battery_remaining": 77,
                    "app_context": "B",
                    "horizontal_accuracy": 9.64799976348877,
                    "vertical_accuracy": 3.0,
                    "location_permission": true,
                    "course": 11.085373878479004,
                    "source": "HTTPS",
                    "created_at": "2021-06-03T17:06:11.106"
                }
            },
            {
                "id": "60b89cb306f8a06fb3fae0a8",
                "app_id": "60af306a8ce7db2392eb7a75_1",
                "device_token": "cyv7qo-5XDw:APA91bGFPNoHCmY26ckS34g4qze0Y6J6EQPNq2fsQyStd4oU6-dZTKjJ5PvxWEGtHFl6YVpk5wbBgXBbsNzCcG4uwWfhMCFtw3zT5n2NgBEL55XwVE0gmfx7CprmJkZCZDi3mbl_9kcW",
                "description": "raju",
                "brand": "xiaomi",
                "model": "Redmi Note 7",
                "os_version": "28",
                "sdk_version": "3.1.3",
                "device_arn": "arn:aws:sns:us-east-1:218937252071:endpoint/GCM/app_60af306a8ce7db2392eb7a75_1_a678d41d-a66f-442b-90e5-1564b6c88c34/81c4df96-3e2e-3592-a9a7-fd96e1092d1f",
                "geofence_events": true,
                "motion_events": false,
                "location_events": true,
                "trips_events": true,
                "nearby_events": true,
                "location_listener": true,
                "event_listener": true,
                "is_deleted": false,
                "created_at": "2021-06-03T09:11:15.569",
                "last_location_update": {
                    "id": "60b89cbd738eafe5bb7feef7",
                    "location_id": "60b89cb64319ec000069d0a8",
                    "coordinates": {
                        "type": "Point",
                        "coordinates": [
                            85.0693555,
                            25.6054544
                        ]
                    },
                    "speed": 0.0,
                    "altitude": -10.98783069403458,
                    "activity": "MOVING",
                    "recorded_at": "2021-06-03T09:11:18.960",
                    "gps_status": true,
                    "battery_remaining": 87,
                    "app_context": "F",
                    "horizontal_accuracy": 34.400001525878906,
                    "vertical_accuracy": 3.0,
                    "location_permission": true,
                    "course": 0.0,
                    "source": "HTTPS",
                    "created_at": "2021-06-03T09:11:25.465"
                }
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
curl --location --request GET 'https://api.roam.ai/v1/api/user/?start_date=2021-06-01&end_date=2021-06-06' \
--header 'Api-Key: 761f129e9d3a4de380baa6f4f0e7ab05'
```

