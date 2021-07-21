---
description: >-
  The Get Trips API lets you fetch the trips data of all active ongoing and
  completed trips for your users.
---

# Trips

{% api-method method="get" host="https://api.geospark.co/v1" path="/api/trips/" %}
{% api-method-summary %}
Get Trips List API
{% endapi-method-summary %}

{% api-method-description %}
The Get Trips list API lets you fetch the list of all trips data of all active ongoing and completed trips for your users.  
**Note:** duration is in seconds and distance\_covered is in meters.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Api-Key" type="string" required=true %}
 ~~33223kjhdcscijhb5sdbsdmjsdcbj5f~~
{% endapi-method-parameter %}

{% api-method-parameter name="Content-Type" type="string" required=true %}
 application/json
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="user\_id" type="string" required=false %}
Filters the trips data for the given user\_id.
{% endapi-method-parameter %}

{% api-method-parameter name="start\_date" type="string" required=false %}
This field can be used for defining a start date from which the list of trips to be shown.  
**Input Data:** 2018-10-19
{% endapi-method-parameter %}

{% api-method-parameter name="end\_date" type="string" required=false %}
This field can be used to define a range of time till when the last document needs to be provided. 'end\_date' should always be greater than 'start\_date'.  
If end\_date is provided then start\_date should also be provided.If only start\_date is passed, the trip list for same day will be returned.  
**Input Date:** 2018-10-20
{% endapi-method-parameter %}

{% api-method-parameter name="page\_number" type="integer" required=false %}
This field can be used for getting 10 entries at a time. If the response returns an empty list in data filed, it is safe to assume the pages are exhausted.
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

{% code title="JSON" %}
```javascript
{
    "status": true,
    "msg": "Success.",
    "code": 200,
    "data": {
        "next_page": null,
        "pages": 1,
        "prev_page": null,
        "trips": [
            {
                "id": "5d946bc45f37c6157d371d8f",
                "project_id": "5d930b99670dc8057b7b0eb3",
                "origins": [
                    {
                        "id": "5d946bc45f37c6157d371d90",
                        "trip_id": "5d946bc45f37c6157d371d8f",
                        "created_at": "2019-10-02T09:20:04.232",
                        "updated_at": "2019-10-02T09:20:11.730",
                        "coordinates": {
                            "type": "Point",
                            "coordinates": [
                                77.622977,
                                12.917042
                            ]
                        },
                        "reached": true,
                        "left": true,
                        "loc_type": "origin"
                    },
                    {
                        "id": "5d946bc45f37c6157d371d91",
                        "trip_id": "5d946bc45f37c6157d371d8f",
                        "created_at": "2019-10-02T09:20:04.245",
                        "updated_at": "2019-10-02T09:20:16.638",
                        "coordinates": {
                            "type": "Point",
                            "coordinates": [
                                77.650239,
                                12.924304
                            ]
                        },
                        "reached": true,
                        "left": true,
                        "loc_type": "origin"
                    },
                    {
                        "id": "5d946bc45f37c6157d371d92",
                        "trip_id": "5d946bc45f37c6157d371d8f",
                        "created_at": "2019-10-02T09:20:04.257",
                        "updated_at": "2019-10-02T09:20:16.710",
                        "coordinates": {
                            "type": "Point",
                            "coordinates": [
                                77.743206,
                                12.954302
                            ]
                        },
                        "reached": true,
                        "loc_type": "origin"
                    }
                ],
                "destinations": [
                    {
                        "id": "5d946bc45f37c6157d371d93",
                        "trip_id": "5d946bc45f37c6157d371d8f",
                        "created_at": "2019-10-02T09:20:04.269",
                        "updated_at": "2019-10-02T09:20:04.274",
                        "coordinates": {
                            "type": "Point",
                            "coordinates": [
                                78.743206,
                                12.954302
                            ]
                        },
                        "reached": false,
                        "loc_type": "destination"
                    }
                ],
                "events": [
                    {
                        "id": "5d946bc45f37c6157d371d94",
                        "trip_id": "5d946bc45f37c6157d371d8f",
                        "user_id": "5d946b665f37c6158337199e",
                        "event_type": "trip:created",
                        "created_at": "2019-10-02T09:20:04.287",
                        "is_deleted": false
                    },
                    {
                        "id": "5d946bc6670dc8057b7b1094",
                        "trip_id": "5d946bc45f37c6157d371d8f",
                        "user_id": "5d946b665f37c6158337199e",
                        "event_type": "trip:user_reached_origin",
                        "trip_location_id": "5d946bc45f37c6157d371d90",
                        "user_location_id": "5d946bc6670dc8057b7b1092",
                        "created_at": "2019-10-02T09:20:06.707",
                        "is_deleted": false
                    },
                    {
                        "id": "5d946bc95f37c615833719a1",
                        "trip_id": "5d946bc45f37c6157d371d8f",
                        "user_id": "5d946b665f37c6158337199e",
                        "event_type": "trip:started",
                        "user_location_id": "5d946bc95f37c6158337199f",
                        "created_at": "2019-10-02T09:20:09.523",
                        "is_deleted": false
                    },
                    {
                        "id": "5d946bcb670dc805807b0b99",
                        "trip_id": "5d946bc45f37c6157d371d8f",
                        "user_id": "5d946b665f37c6158337199e",
                        "event_type": "trip:user_left_origin",
                        "trip_location_id": "5d946bc45f37c6157d371d90",
                        "user_location_id": "5d946bcb670dc805807b0b97",
                        "created_at": "2019-10-02T09:20:11.735",
                        "is_deleted": false
                    },
                    {
                        "id": "5d946bce5f37c6157d371d97",
                        "trip_id": "5d946bc45f37c6157d371d8f",
                        "user_id": "5d946b665f37c6158337199e",
                        "event_type": "trip:user_reached_origin",
                        "trip_location_id": "5d946bc45f37c6157d371d91",
                        "user_location_id": "5d946bce5f37c6157d371d95",
                        "created_at": "2019-10-02T09:20:14.099",
                        "is_deleted": false
                    },
                    {
                        "id": "5d946bd0670dc8057b7b1097",
                        "trip_id": "5d946bc45f37c6157d371d8f",
                        "user_id": "5d946b665f37c6158337199e",
                        "event_type": "trip:user_left_origin",
                        "trip_location_id": "5d946bc45f37c6157d371d91",
                        "user_location_id": "5d946bd0670dc8057b7b1095",
                        "created_at": "2019-10-02T09:20:16.643",
                        "is_deleted": false
                    },
                    {
                        "id": "5d946bd0670dc8057b7b1098",
                        "trip_id": "5d946bc45f37c6157d371d8f",
                        "user_id": "5d946b665f37c6158337199e",
                        "event_type": "trip:user_reached_origin",
                        "trip_location_id": "5d946bc45f37c6157d371d92",
                        "user_location_id": "5d946bd0670dc8057b7b1095",
                        "created_at": "2019-10-02T09:20:16.710",
                        "is_deleted": false
                    }
                ],
                "user_id": "5d946b665f37c6158337199e",
                "is_started": true,
                "is_ended": false,
                "is_deleted": false,
                "trip_started_at": "2019-10-02T09:20:09.229",
                "is_paused": false,
                "created_at": "2019-10-02T09:20:04.229",
                "updated_at": "2019-10-02T09:20:16.718"
            },
            {
                "id": "5d946b545f37c6157d371d86",
                "project_id": "5d930b99670dc8057b7b0eb3",
                "origins": [
                    {
                        "id": "5d946b545f37c6157d371d87",
                        "trip_id": "5d946b545f37c6157d371d86",
                        "created_at": "2019-10-02T09:18:12.400",
                        "updated_at": "2019-10-02T09:18:22.777",
                        "coordinates": {
                            "type": "Point",
                            "coordinates": [
                                77.622977,
                                12.917042
                            ]
                        },
                        "reached": true,
                        "left": true,
                        "loc_type": "origin"
                    },
                    {
                        "id": "5d946b545f37c6157d371d88",
                        "trip_id": "5d946b545f37c6157d371d86",
                        "created_at": "2019-10-02T09:18:12.411",
                        "updated_at": "2019-10-02T09:18:27.624",
                        "coordinates": {
                            "type": "Point",
                            "coordinates": [
                                77.650239,
                                12.924304
                            ]
                        },
                        "reached": true,
                        "loc_type": "origin"
                    },
                    {
                        "id": "5d946b545f37c6157d371d89",
                        "trip_id": "5d946b545f37c6157d371d86",
                        "created_at": "2019-10-02T09:18:12.423",
                        "updated_at": "2019-10-02T09:18:27.691",
                        "coordinates": {
                            "type": "Point",
                            "coordinates": [
                                77.743206,
                                12.954302
                            ]
                        },
                        "reached": true,
                        "left": true,
                        "loc_type": "origin"
                    }
                ],
                "destinations": [
                    {
                        "id": "5d946b545f37c6157d371d8a",
                        "trip_id": "5d946b545f37c6157d371d86",
                        "created_at": "2019-10-02T09:18:12.434",
                        "updated_at": "2019-10-02T09:18:12.438",
                        "coordinates": {
                            "type": "Point",
                            "coordinates": [
                                78.743206,
                                12.954302
                            ]
                        },
                        "reached": false,
                        "loc_type": "destination"
                    }
                ],
                "events": [
                    {
                        "id": "5d946b545f37c6157d371d8b",
                        "trip_id": "5d946b545f37c6157d371d86",
                        "user_id": "5d946b2f670dc8057b7b108c",
                        "event_type": "trip:created",
                        "created_at": "2019-10-02T09:18:12.451",
                        "is_deleted": false
                    },
                    {
                        "id": "5d946b5a670dc805807b0b91",
                        "trip_id": "5d946b545f37c6157d371d86",
                        "user_id": "5d946b2f670dc8057b7b108c",
                        "event_type": "trip:user_reached_origin",
                        "trip_location_id": "5d946b545f37c6157d371d87",
                        "user_location_id": "5d946b5a670dc805807b0b8f",
                        "created_at": "2019-10-02T09:18:18.087",
                        "is_deleted": false
                    },
                    {
                        "id": "5d946b5c5f37c6158337199d",
                        "trip_id": "5d946b545f37c6157d371d86",
                        "user_id": "5d946b2f670dc8057b7b108c",
                        "event_type": "trip:started",
                        "user_location_id": "5d946b5c5f37c6158337199b",
                        "created_at": "2019-10-02T09:18:20.469",
                        "is_deleted": false
                    },
                    {
                        "id": "5d946b5e670dc8057b7b108f",
                        "trip_id": "5d946b545f37c6157d371d86",
                        "user_id": "5d946b2f670dc8057b7b108c",
                        "event_type": "trip:user_left_origin",
                        "trip_location_id": "5d946b545f37c6157d371d87",
                        "user_location_id": "5d946b5e670dc8057b7b108d",
                        "created_at": "2019-10-02T09:18:22.782",
                        "is_deleted": false
                    },
                    {
                        "id": "5d946b615f37c6157d371d8e",
                        "trip_id": "5d946b545f37c6157d371d86",
                        "user_id": "5d946b2f670dc8057b7b108c",
                        "event_type": "trip:user_reached_origin",
                        "trip_location_id": "5d946b545f37c6157d371d89",
                        "user_location_id": "5d946b605f37c6157d371d8c",
                        "created_at": "2019-10-02T09:18:25.016",
                        "is_deleted": false
                    },
                    {
                        "id": "5d946b63670dc805807b0b94",
                        "trip_id": "5d946b545f37c6157d371d86",
                        "user_id": "5d946b2f670dc8057b7b108c",
                        "event_type": "trip:user_reached_origin",
                        "trip_location_id": "5d946b545f37c6157d371d88",
                        "user_location_id": "5d946b63670dc805807b0b92",
                        "created_at": "2019-10-02T09:18:27.624",
                        "is_deleted": false
                    },
                    {
                        "id": "5d946b63670dc805807b0b95",
                        "trip_id": "5d946b545f37c6157d371d86",
                        "user_id": "5d946b2f670dc8057b7b108c",
                        "event_type": "trip:user_left_origin",
                        "trip_location_id": "5d946b545f37c6157d371d89",
                        "user_location_id": "5d946b63670dc805807b0b92",
                        "created_at": "2019-10-02T09:18:27.696",
                        "is_deleted": false
                    },
                    {
                        "id": "5d946b63670dc805807b0b96",
                        "trip_id": "5d946b545f37c6157d371d86",
                        "user_id": "5d946b2f670dc8057b7b108c",
                        "event_type": "trip:completed",
                        "user_location_id": "5d946b63670dc805807b0b92",
                        "created_at": "2019-10-02T09:18:27.782",
                        "is_deleted": false
                    }
                ],
                "user_id": "5d946b2f670dc8057b7b108c",
                "is_started": true,
                "is_ended": true,
                "is_deleted": false,
                "trip_started_at": "2019-10-02T09:18:20.165",
                "trip_ended_at": "2019-10-02T09:18:27.403",
                "distance_covered": 24432.62,
                "duration": 7,
                "is_paused": false,
                "created_at": "2019-10-02T09:18:12.397",
                "updated_at": "2019-10-02T09:18:27.803"
            }
        ]
    }
}
```
{% endcode %}
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

### Sample Call

{% tabs %}
{% tab title="cURL" %}
```javascript
curl -X GET \
  'https://api.geospark.co/v1/api/trips/?start_date=2019-07-15&end_date=2019-07-20&page_number=1' \
  -H 'Api-key: cbdd0c41a4e5461e97d1fbedb67f159e' \
  -H 'Content-Type: application/json' \
  -H 'cache-control: no-cache'
```
{% endtab %}

{% tab title="Go" %}
```go
package main

import (
    "fmt"
    "net/http"
    "io/ioutil"
)

func main() {

    url := "https://api.geospark.co/v1/api/trips/?start_date=2019-07-15&end_date=2019-07-20&page_number=1"

    req, _ := http.NewRequest("GET", url, nil)

    req.Header.Add("Api-key", "cbdd0c41a4e5461e97d1fbedb67f159e")
    req.Header.Add("Content-Type", "application/json")
    req.Header.Add("cache-control", "no-cache")
    req.Header.Add("Postman-Token", "d98447b6-3b33-412f-9903-189ac7b3c218")

    res, _ := http.DefaultClient.Do(req)

    defer res.Body.Close()
    body, _ := ioutil.ReadAll(res.Body)

    fmt.Println(res)
    fmt.Println(string(body))

}
```
{% endtab %}

{% tab title="Java" %}
```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api.geospark.co/v1/api/trips/?start_date=2019-07-15&end_date=2019-07-20&page_number=1")
  .get()
  .addHeader("Api-key", "cbdd0c41a4e5461e97d1fbedb67f159e")
  .addHeader("Content-Type", "application/json")
  .addHeader("cache-control", "no-cache")
  .addHeader("Postman-Token", "17e0dadb-4df6-4eb3-890b-61a5ed2ea775")
  .build();

Response response = client.newCall(request).execute();
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api.geospark.co/v1/api/trips/?start_date=2019-07-15&end_date=2019-07-20&page_number=1",
  "method": "GET",
  "headers": {
    "Api-key": "cbdd0c41a4e5461e97d1fbedb67f159e",
    "Content-Type": "application/json",
    "cache-control": "no-cache",
    "Postman-Token": "d6231fbc-2e1f-44a4-9bb1-13afd7e28744"
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```
{% endtab %}

{% tab title="Python" %}
```python
import requests

url = "https://api.geospark.co/v1/api/trips/"

querystring = {"start_date":"2019-07-15","end_date":"2019-07-20","page_number":"1"}

headers = {
    'Api-key': "cbdd0c41a4e5461e97d1fbedb67f159e",
    'Content-Type': "application/json",
    'cache-control': "no-cache",
    'Postman-Token': "08493f58-1a66-40c8-8069-8aa1f197087e"
    }

response = requests.request("GET", url, headers=headers, params=querystring)

print(response.text)
```
{% endtab %}

{% tab title="Swift" %}
```swift
import Foundation

let headers = [
  "Api-key": "cbdd0c41a4e5461e97d1fbedb67f159e",
  "Content-Type": "application/json",
  "cache-control": "no-cache",
  "Postman-Token": "28ee3922-9836-42df-ab44-d0b455326db4"
]

let request = NSMutableURLRequest(url: NSURL(string: "https://api.geospark.co/v1/api/trips/?start_date=2019-07-15&end_date=2019-07-20&page_number=1")! as URL,
                                        cachePolicy: .useProtocolCachePolicy,
                                    timeoutInterval: 10.0)
request.httpMethod = "GET"
request.allHTTPHeaderFields = headers

let session = URLSession.shared
let dataTask = session.dataTask(with: request as URLRequest, completionHandler: { (data, response, error) -> Void in
  if (error != nil) {
    print(error)
  } else {
    let httpResponse = response as? HTTPURLResponse
    print(httpResponse)
  }
})

dataTask.resume()
```
{% endtab %}
{% endtabs %}

{% api-method method="get" host="https://api.geospark.co/v1" path="/api/trips/" %}
{% api-method-summary %}
Get Trip API
{% endapi-method-summary %}

{% api-method-description %}
This API gives you the trip data of the given trip\_id.   
**Note:** Duration is in seconds and distance\_covered is in meters. 
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Api-Key" type="string" required=true %}
~~`33223kjhdcscijhb5sdbsdmjsdcbj5f`~~
{% endapi-method-parameter %}

{% api-method-parameter name="Content-Type" type="string" required=true %}
application/json
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="trip\_id" type="string" required=true %}
5c40560ea1426005bd908213
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
            "id": "5d946bc45f37c6157d371d8f",
            "project_id": "5d930b99670dc8057b7b0eb3",
            "origins": [
                {
                    "id": "5d946bc45f37c6157d371d90",
                    "trip_id": "5d946bc45f37c6157d371d8f",
                    "created_at": "2019-10-02T09:20:04.232",
                    "updated_at": "2019-10-02T09:20:11.730",
                    "coordinates": {
                        "type": "Point",
                        "coordinates": [
                            77.622977,
                            12.917042
                        ]
                    },
                    "reached": true,
                    "left": true,
                    "loc_type": "origin"
                },
                {
                    "id": "5d946bc45f37c6157d371d91",
                    "trip_id": "5d946bc45f37c6157d371d8f",
                    "created_at": "2019-10-02T09:20:04.245",
                    "updated_at": "2019-10-02T09:20:16.638",
                    "coordinates": {
                        "type": "Point",
                        "coordinates": [
                            77.650239,
                            12.924304
                        ]
                    },
                    "reached": true,
                    "left": true,
                    "loc_type": "origin"
                },
                {
                    "id": "5d946bc45f37c6157d371d92",
                    "trip_id": "5d946bc45f37c6157d371d8f",
                    "created_at": "2019-10-02T09:20:04.257",
                    "updated_at": "2019-10-02T09:20:16.710",
                    "coordinates": {
                        "type": "Point",
                        "coordinates": [
                            77.743206,
                            12.954302
                        ]
                    },
                    "reached": true,
                    "loc_type": "origin"
                }
            ],
            "destinations": [
                {
                    "id": "5d946bc45f37c6157d371d93",
                    "trip_id": "5d946bc45f37c6157d371d8f",
                    "created_at": "2019-10-02T09:20:04.269",
                    "updated_at": "2019-10-02T09:20:04.274",
                    "coordinates": {
                        "type": "Point",
                        "coordinates": [
                            78.743206,
                            12.954302
                        ]
                    },
                    "reached": false,
                    "loc_type": "destination"
                }
            ],
            "events": [
                {
                    "id": "5d946bc45f37c6157d371d94",
                    "trip_id": "5d946bc45f37c6157d371d8f",
                    "user_id": "5d946b665f37c6158337199e",
                    "event_type": "trip:created",
                    "created_at": "2019-10-02T09:20:04.287",
                    "is_deleted": false
                },
                {
                    "id": "5d946bc6670dc8057b7b1094",
                    "trip_id": "5d946bc45f37c6157d371d8f",
                    "user_id": "5d946b665f37c6158337199e",
                    "event_type": "trip:user_reached_origin",
                    "trip_location_id": "5d946bc45f37c6157d371d90",
                    "user_location_id": "5d946bc6670dc8057b7b1092",
                    "created_at": "2019-10-02T09:20:06.707",
                    "is_deleted": false
                },
                {
                    "id": "5d946bc95f37c615833719a1",
                    "trip_id": "5d946bc45f37c6157d371d8f",
                    "user_id": "5d946b665f37c6158337199e",
                    "event_type": "trip:started",
                    "user_location_id": "5d946bc95f37c6158337199f",
                    "created_at": "2019-10-02T09:20:09.523",
                    "is_deleted": false
                },
                {
                    "id": "5d946bcb670dc805807b0b99",
                    "trip_id": "5d946bc45f37c6157d371d8f",
                    "user_id": "5d946b665f37c6158337199e",
                    "event_type": "trip:user_left_origin",
                    "trip_location_id": "5d946bc45f37c6157d371d90",
                    "user_location_id": "5d946bcb670dc805807b0b97",
                    "created_at": "2019-10-02T09:20:11.735",
                    "is_deleted": false
                },
                {
                    "id": "5d946bce5f37c6157d371d97",
                    "trip_id": "5d946bc45f37c6157d371d8f",
                    "user_id": "5d946b665f37c6158337199e",
                    "event_type": "trip:user_reached_origin",
                    "trip_location_id": "5d946bc45f37c6157d371d91",
                    "user_location_id": "5d946bce5f37c6157d371d95",
                    "created_at": "2019-10-02T09:20:14.099",
                    "is_deleted": false
                },
                {
                    "id": "5d946bd0670dc8057b7b1097",
                    "trip_id": "5d946bc45f37c6157d371d8f",
                    "user_id": "5d946b665f37c6158337199e",
                    "event_type": "trip:user_left_origin",
                    "trip_location_id": "5d946bc45f37c6157d371d91",
                    "user_location_id": "5d946bd0670dc8057b7b1095",
                    "created_at": "2019-10-02T09:20:16.643",
                    "is_deleted": false
                },
                {
                    "id": "5d946bd0670dc8057b7b1098",
                    "trip_id": "5d946bc45f37c6157d371d8f",
                    "user_id": "5d946b665f37c6158337199e",
                    "event_type": "trip:user_reached_origin",
                    "trip_location_id": "5d946bc45f37c6157d371d92",
                    "user_location_id": "5d946bd0670dc8057b7b1095",
                    "created_at": "2019-10-02T09:20:16.710",
                    "is_deleted": false
                }
            ],
            "user_id": "5d946b665f37c6158337199e",
            "is_started": true,
            "is_ended": false,
            "is_deleted": false,
            "trip_started_at": "2019-10-02T09:20:09.229",
            "is_paused": false,
            "created_at": "2019-10-02T09:20:04.229",
            "updated_at": "2019-10-02T09:20:16.718"
        }
    ]
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

### Sample Call

{% tabs %}
{% tab title="cURL" %}
```javascript
curl -X GET \
  'https://api.geospark.co/v1/api/trips/?trip_id=5d947fcb96940667bc0a1a5e' \
  -H 'Api-key: cbdd0c41a4e5461e97d1fbedb67f159e' \
  -H 'Content-Type: application/json' \
  -H 'Postman-Token: cd0dc842-4ece-4f27-a9e2-62032ac47b94' \
  -H 'cache-control: no-cache'
```
{% endtab %}

{% tab title="Go" %}
```go
package main

import (
    "fmt"
    "net/http"
    "io/ioutil"
)

func main() {

    url := "https://api.geospark.co/v1/api/trips/?trip_id=5d947fcb96940667bc0a1a5e"

    req, _ := http.NewRequest("GET", url, nil)

    req.Header.Add("Api-key", "cbdd0c41a4e5461e97d1fbedb67f159e")
    req.Header.Add("Content-Type", "application/json")
    req.Header.Add("cache-control", "no-cache")
    req.Header.Add("Postman-Token", "42708f37-b525-487d-a52d-b82fb80e49c6")

    res, _ := http.DefaultClient.Do(req)

    defer res.Body.Close()
    body, _ := ioutil.ReadAll(res.Body)

    fmt.Println(res)
    fmt.Println(string(body))

}
```
{% endtab %}

{% tab title="Java" %}
```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api.geospark.co/v1/api/trips/?trip_id=5d947fcb96940667bc0a1a5e")
  .get()
  .addHeader("Api-key", "cbdd0c41a4e5461e97d1fbedb67f159e")
  .addHeader("Content-Type", "application/json")
  .addHeader("cache-control", "no-cache")
  .addHeader("Postman-Token", "d8b20d6e-fca5-4c93-8c7f-807c40a56c7c")
  .build();

Response response = client.newCall(request).execute();
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api.geospark.co/v1/api/trips/?trip_id=5d947fcb96940667bc0a1a5e",
  "method": "GET",
  "headers": {
    "Api-key": "cbdd0c41a4e5461e97d1fbedb67f159e",
    "Content-Type": "application/json",
    "cache-control": "no-cache",
    "Postman-Token": "d12cf88d-1c44-449e-b1ce-c6f737f16982"
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```
{% endtab %}

{% tab title="Python" %}
```python
import requests

url = "https://api.geospark.co/v1/api/trips/"

querystring = {"trip_id":"5d947fcb96940667bc0a1a5e"}

headers = {
    'Api-key': "cbdd0c41a4e5461e97d1fbedb67f159e",
    'Content-Type': "application/json",
    'cache-control': "no-cache",
    'Postman-Token': "86e46e9c-129d-42a0-9cfe-96fa5cba910f"
    }

response = requests.request("GET", url, headers=headers, params=querystring)

print(response.text)
```
{% endtab %}

{% tab title="Swift" %}
```swift
import Foundation

let headers = [
  "Api-key": "cbdd0c41a4e5461e97d1fbedb67f159e",
  "Content-Type": "application/json",
  "cache-control": "no-cache",
  "Postman-Token": "510d1be2-8024-48d7-aef1-91630f506470"
]

let request = NSMutableURLRequest(url: NSURL(string: "https://api.geospark.co/v1/api/trips/?trip_id=5d947fcb96940667bc0a1a5e")! as URL,
                                        cachePolicy: .useProtocolCachePolicy,
                                    timeoutInterval: 10.0)
request.httpMethod = "GET"
request.allHTTPHeaderFields = headers

let session = URLSession.shared
let dataTask = session.dataTask(with: request as URLRequest, completionHandler: { (data, response, error) -> Void in
  if (error != nil) {
    print(error)
  } else {
    let httpResponse = response as? HTTPURLResponse
    print(httpResponse)
  }
})

dataTask.resume()
```
{% endtab %}
{% endtabs %}

{% api-method method="post" host="https://api.geospark.co/v1" path="/api/trips/" %}
{% api-method-summary %}
Create Trip API
{% endapi-method-summary %}

{% api-method-description %}
This API helps you to create a new trip with origin, destination and user.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Api-Key" type="string" required=true %}
Your API Key Here
{% endapi-method-parameter %}

{% api-method-parameter name="Content-Type" type="string" required=true %}
application/json
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="user\_id" type="string" required=true %}
User id of the device to be assigned this trip
{% endapi-method-parameter %}

{% api-method-parameter name="origins" type="array" required=false %}
Origin location in \[long, lat\] format  
Eg. \[\[77.677270, 12.914131\]\]
{% endapi-method-parameter %}

{% api-method-parameter name="destinations" type="array" required=false %}
Destination location in \[long, lat\] format  
Eg. \[\[77.700475, 12.957005\]\]
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
    "status": true,
    "msg": "Success.",
    "code": 201,
    "data": [
        {
            "id": "5d946da25f37c6157d371d98",
            "origins": [
                {
                    "id": "5d946da25f37c6157d371d99",
                    "trip_id": "5d946da25f37c6157d371d98",
                    "created_at": "2019-10-02T09:28:02.952",
                    "updated_at": "2019-10-02T09:28:02.956",
                    "coordinates": {
                        "type": "Point",
                        "coordinates": [
                            77.622977,
                            12.917042
                        ]
                    },
                    "reached": false,
                    "loc_type": "origin"
                },
                {
                    "id": "5d946da25f37c6157d371d9a",
                    "trip_id": "5d946da25f37c6157d371d98",
                    "created_at": "2019-10-02T09:28:02.964",
                    "updated_at": "2019-10-02T09:28:02.968",
                    "coordinates": {
                        "type": "Point",
                        "coordinates": [
                            77.650239,
                            12.924304
                        ]
                    },
                    "reached": false,
                    "loc_type": "origin"
                }
            ],
            "destinations": [
                {
                    "id": "5d946da25f37c6157d371d9b",
                    "trip_id": "5d946da25f37c6157d371d98",
                    "created_at": "2019-10-02T09:28:02.976",
                    "updated_at": "2019-10-02T09:28:02.981",
                    "coordinates": {
                        "type": "Point",
                        "coordinates": [
                            78.743206,
                            12.954302
                        ]
                    },
                    "reached": false,
                    "loc_type": "destination"
                },
                {
                    "id": "5d946da25f37c6157d371d9c",
                    "trip_id": "5d946da25f37c6157d371d98",
                    "created_at": "2019-10-02T09:28:02.988",
                    "updated_at": "2019-10-02T09:28:02.993",
                    "coordinates": {
                        "type": "Point",
                        "coordinates": [
                            77.743206,
                            12.954302
                        ]
                    },
                    "reached": false,
                    "loc_type": "destination"
                }
            ],
            "events": [
                {
                    "id": "5d946da35f37c6157d371d9d",
                    "trip_id": "5d946da25f37c6157d371d98",
                    "user_id": "5d946b665f37c6158337199e",
                    "event_type": "trip:created",
                    "created_at": "2019-10-02T09:28:03.006",
                    "is_deleted": false
                }
            ],
            "user_id": "5d946b665f37c6158337199e",
            "is_started": false,
            "is_ended": false,
            "is_deleted": false,
            "is_paused": false,
            "created_at": "2019-10-02T09:28:02.949",
            "updated_at": "2019-10-02T09:28:03.015",
            "trip_tracking_url": "https://trips.gs/NWQ5NDZkYTI1ZjM3YzYxNTdkMzcxZDk4fHNmZHNnZHNh"
        }
    ]
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

### Sample Call

{% tabs %}
{% tab title="cURL" %}
```javascript
curl -X POST \
  https://api.geospark.co/v1/api/trips/ \
  -H 'Api-key: cbdd0c41a4e5461e97d1fbedb67f159e' \
  -H 'Content-Type: application/json' \
  -H 'Postman-Token: 8f013cd3-b87c-4264-ba35-4c4f5d946572' \
  -H 'cache-control: no-cache' \
  -d '{
    "user_id": "5d9450ace47bae6d70064a9b",
    "origins": [[77.622977,12.917042],[77.650239,12.924304], [77.743206, 12.954302]],
     "destinations":[[78.743206, 12.954302]]
}'
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api.geospark.co/v1/api/trips/",
  "method": "POST",
  "headers": {
    "Api-key": "cbdd0c41a4e5461e97d1fbedb67f159e",
    "Content-Type": "application/json",
  },
  "processData": false,
  "data": "{\n\t\"user_id\": \"5d9450ace47bae6d70064a9b\",\n\t\"origins\": [[77.622977,12.917042],[77.650239,12.924304], [77.743206, 12.954302]],\n     \"destinations\":[[78.743206, 12.954302]]\n}\n"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```
{% endtab %}

{% tab title="Python" %}
```python
import requests

url = "https://api.geospark.co/v1/api/trips/"

payload = "{\n\t\"user_id\": \"5d9450ace47bae6d70064a9b\",\n\t\"origins\": [[77.622977,12.917042],[77.650239,12.924304], [77.743206, 12.954302]],\n     \"destinations\":[[78.743206, 12.954302]]\n}\n"
headers = {
    'Api-key': "cbdd0c41a4e5461e97d1fbedb67f159e",
    'Content-Type': "application/json"
    }

response = requests.request("POST", url, data=payload, headers=headers)

print(response.text)
```
{% endtab %}

{% tab title="Java" %}
```java
OkHttpClient client = new OkHttpClient();

MediaType mediaType = MediaType.parse("application/json");
RequestBody body = RequestBody.create(mediaType, "{\n\t\"user_id\": \"5d9450ace47bae6d70064a9b\",\n\t\"origins\": [[77.622977,12.917042],[77.650239,12.924304], [77.743206, 12.954302]],\n     \"destinations\":[[78.743206, 12.954302]]\n}\n");
Request request = new Request.Builder()
  .url("https://api.geospark.co/v1/api/trips/")
  .post(body)
  .addHeader("Api-key", "cbdd0c41a4e5461e97d1fbedb67f159e")
  .addHeader("Content-Type", "application/json")
  .build();

Response response = client.newCall(request).execute();
```
{% endtab %}

{% tab title="Swift" %}
```swift
import Foundation

let headers = [
  "Api-key": "cbdd0c41a4e5461e97d1fbedb67f159e",
  "Content-Type": "application/json"
]
let parameters = [
  "user_id": "5d9450ace47bae6d70064a9b",
  "origins": [[77.622977, 12.917042], [77.650239, 12.924304], [77.743206, 12.954302]],
  "destinations": [[78.743206, 12.954302]]
] as [String : Any]

let postData = JSONSerialization.data(withJSONObject: parameters, options: [])

let request = NSMutableURLRequest(url: NSURL(string: "https://api.geospark.co/v1/api/trips/")! as URL,
                                        cachePolicy: .useProtocolCachePolicy,
                                    timeoutInterval: 10.0)
request.httpMethod = "POST"
request.allHTTPHeaderFields = headers
request.httpBody = postData as Data

let session = URLSession.shared
let dataTask = session.dataTask(with: request as URLRequest, completionHandler: { (data, response, error) -> Void in
  if (error != nil) {
    print(error)
  } else {
    let httpResponse = response as? HTTPURLResponse
    print(httpResponse)
  }
})

dataTask.resume()
```
{% endtab %}

{% tab title="Go" %}
```go
package main

import (
    "fmt"
    "strings"
    "net/http"
    "io/ioutil"
)

func main() {

    url := "https://api.geospark.co/v1/api/trips/"

    payload := strings.NewReader("{\n\t\"user_id\": \"5d9450ace47bae6d70064a9b\",\n\t\"origins\": [[77.622977,12.917042],[77.650239,12.924304], [77.743206, 12.954302]],\n     \"destinations\":[[78.743206, 12.954302]]\n}\n")

    req, _ := http.NewRequest("POST", url, payload)

    req.Header.Add("Api-key", "cbdd0c41a4e5461e97d1fbedb67f159e")
    req.Header.Add("Content-Type", "application/json")

    res, _ := http.DefaultClient.Do(req)

    defer res.Body.Close()
    body, _ := ioutil.ReadAll(res.Body)

    fmt.Println(res)
    fmt.Println(string(body))

}
```
{% endtab %}
{% endtabs %}

{% api-method method="put" host="https://api.geospark.co/v1" path="/api/trips/" %}
{% api-method-summary %}
Update Trip API
{% endapi-method-summary %}

{% api-method-description %}
This API helps you to update the origin, destination or user\_id for given trip\_id.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Api-Key" type="string" required=true %}
Your API Key Here
{% endapi-method-parameter %}

{% api-method-parameter name="Content-Type" type="string" required=true %}
application/json
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="trip\_id" type="string" required=true %}
Trip id which needs to be modified.  
Eg. 5cd0299d77aebe2d78758d32
{% endapi-method-parameter %}

{% api-method-parameter name="destinations" type="array" required=false %}
Destination location in \[long, lat\] format  
Eg. \[\[77.700475, 12.957005\]\]
{% endapi-method-parameter %}

{% api-method-parameter name="origins" type="array" required=false %}
Origin location in \[long, lat\] format  
Eg. \[\[77.677270, 12.914132\]\]
{% endapi-method-parameter %}

{% api-method-parameter name="user\_id" type="string" required=false %}
User id of the device to be assigned to this trip.  
Eg. 5ccea6ed77aebe1f28fbcc24
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
    "status": true,
    "msg": "Success.",
    "code": 201,
    "data": [
        {
            "id": "5d946da25f37c6157d371d98",
            "origins": [
                {
                    "id": "5d946da25f37c6157d371d99",
                    "trip_id": "5d946da25f37c6157d371d98",
                    "created_at": "2019-10-02T09:28:02.952",
                    "updated_at": "2019-10-02T09:28:02.956",
                    "coordinates": {
                        "type": "Point",
                        "coordinates": [
                            77.622977,
                            12.917042
                        ]
                    },
                    "reached": false,
                    "loc_type": "origin"
                },
                {
                    "id": "5d946da25f37c6157d371d9a",
                    "trip_id": "5d946da25f37c6157d371d98",
                    "created_at": "2019-10-02T09:28:02.964",
                    "updated_at": "2019-10-02T09:28:02.968",
                    "coordinates": {
                        "type": "Point",
                        "coordinates": [
                            77.650239,
                            12.924304
                        ]
                    },
                    "reached": false,
                    "loc_type": "origin"
                }
            ],
            "destinations": [
                {
                    "id": "5d946da25f37c6157d371d9b",
                    "trip_id": "5d946da25f37c6157d371d98",
                    "created_at": "2019-10-02T09:28:02.976",
                    "updated_at": "2019-10-02T09:28:02.981",
                    "coordinates": {
                        "type": "Point",
                        "coordinates": [
                            78.743206,
                            12.954302
                        ]
                    },
                    "reached": false,
                    "loc_type": "destination"
                },
                {
                    "id": "5d946da25f37c6157d371d9c",
                    "trip_id": "5d946da25f37c6157d371d98",
                    "created_at": "2019-10-02T09:28:02.988",
                    "updated_at": "2019-10-02T09:28:02.993",
                    "coordinates": {
                        "type": "Point",
                        "coordinates": [
                            77.743206,
                            12.954302
                        ]
                    },
                    "reached": false,
                    "loc_type": "destination"
                }
            ],
            "events": [
                {
                    "id": "5d946da35f37c6157d371d9d",
                    "trip_id": "5d946da25f37c6157d371d98",
                    "user_id": "5d946b665f37c6158337199e",
                    "event_type": "trip:created",
                    "created_at": "2019-10-02T09:28:03.006",
                    "is_deleted": false
                },
                {
                    "id": "5d946e615f37c6157d371d9e",
                    "trip_id": "5d946da25f37c6157d371d98",
                    "user_id": "5d946b665f37c6158337199e",
                    "event_type": "trip:user_updated",
                    "created_at": "2019-10-02T09:31:13.698",
                    "is_deleted": false
                }
            ],
            "user_id": "5d946e5b670dc8057b7b1099",
            "is_started": false,
            "is_ended": false,
            "is_deleted": false,
            "is_paused": false,
            "created_at": "2019-10-02T09:28:02.949",
            "updated_at": "2019-10-02T09:31:13.780"
        }
    ]
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

### Sample Call

{% tabs %}
{% tab title="cURL" %}
```javascript
curl -X PUT \
  https://api.geospark.co/v1/api/trips/ \
  -H 'Api-key: cbdd0c41a4e5461e97d1fbedb67f159e' \
  -H 'Content-Type: application/json' \
  -H 'Postman-Token: e002841e-d873-4a9e-ac3b-c33418effe82' \
  -H 'cache-control: no-cache' \
  -d '{
    "trip_id": "5d947fcb96940667bc0a1a5e",
    "user_id": "5d9450ace47bae6d70064a9b",
    "origins": [[77.622977,12.917042]],
    "destinations":[[78.743206, 12.954302]]
}'
```
{% endtab %}

{% tab title="Go" %}
```go
package main

import (
    "fmt"
    "strings"
    "net/http"
    "io/ioutil"
)

func main() {

    url := "https://api.geospark.co/v1/api/trips/"

    payload := strings.NewReader("{\n\t\"trip_id\": \"5d947fcb96940667bc0a1a5e\",\n\t\"user_id\": \"5d9450ace47bae6d70064a9b\",\n\t\"origins\": [[77.622977,12.917042]],\n    \"destinations\":[[78.743206, 12.954302]]\n}")

    req, _ := http.NewRequest("PUT", url, payload)

    req.Header.Add("Api-key", "cbdd0c41a4e5461e97d1fbedb67f159e")
    req.Header.Add("Content-Type", "application/json")
    req.Header.Add("cache-control", "no-cache")
    req.Header.Add("Postman-Token", "53c232c1-8868-4cf0-b043-8f2b9ef6bb2c")

    res, _ := http.DefaultClient.Do(req)

    defer res.Body.Close()
    body, _ := ioutil.ReadAll(res.Body)

    fmt.Println(res)
    fmt.Println(string(body))

}
```
{% endtab %}

{% tab title="Java" %}
```java
OkHttpClient client = new OkHttpClient();

MediaType mediaType = MediaType.parse("application/json");
RequestBody body = RequestBody.create(mediaType, "{\n\t\"trip_id\": \"5d947fcb96940667bc0a1a5e\",\n\t\"user_id\": \"5d9450ace47bae6d70064a9b\",\n\t\"origins\": [[77.622977,12.917042]],\n    \"destinations\":[[78.743206, 12.954302]]\n}");
Request request = new Request.Builder()
  .url("https://api.geospark.co/v1/api/trips/")
  .put(body)
  .addHeader("Api-key", "cbdd0c41a4e5461e97d1fbedb67f159e")
  .addHeader("Content-Type", "application/json")
  .addHeader("cache-control", "no-cache")
  .addHeader("Postman-Token", "12a29a6b-5d04-4253-80df-86a90979ab00")
  .build();

Response response = client.newCall(request).execute();
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api.geospark.co/v1/api/trips/",
  "method": "PUT",
  "headers": {
    "Api-key": "cbdd0c41a4e5461e97d1fbedb67f159e",
    "Content-Type": "application/json",
    "cache-control": "no-cache",
    "Postman-Token": "e3acd160-d1f5-4a34-8481-78ad656b8ca7"
  },
  "processData": false,
  "data": "{\n\t\"trip_id\": \"5d947fcb96940667bc0a1a5e\",\n\t\"user_id\": \"5d9450ace47bae6d70064a9b\",\n\t\"origins\": [[77.622977,12.917042]],\n    \"destinations\":[[78.743206, 12.954302]]\n}"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```
{% endtab %}

{% tab title="Python" %}
```python
import requests

url = "https://api.geospark.co/v1/api/trips/"

payload = "{\n\t\"trip_id\": \"5d947fcb96940667bc0a1a5e\",\n\t\"user_id\": \"5d9450ace47bae6d70064a9b\",\n\t\"origins\": [[77.622977,12.917042]],\n    \"destinations\":[[78.743206, 12.954302]]\n}"
headers = {
    'Api-key': "cbdd0c41a4e5461e97d1fbedb67f159e",
    'Content-Type': "application/json",
    'cache-control': "no-cache",
    'Postman-Token': "52f0adb7-b2b6-4a4a-bd1c-f8bb53d9b3cc"
    }

response = requests.request("PUT", url, data=payload, headers=headers)

print(response.text)
```
{% endtab %}

{% tab title="Swift" %}
```swift
import Foundation

let headers = [
  "Api-key": "cbdd0c41a4e5461e97d1fbedb67f159e",
  "Content-Type": "application/json",
  "cache-control": "no-cache",
  "Postman-Token": "df8e003a-ed8d-432f-9828-78eaadebc035"
]
let parameters = [
  "trip_id": "5d947fcb96940667bc0a1a5e",
  "user_id": "5d9450ace47bae6d70064a9b",
  "origins": [[77.622977, 12.917042]],
  "destinations": [[78.743206, 12.954302]]
] as [String : Any]

let postData = JSONSerialization.data(withJSONObject: parameters, options: [])

let request = NSMutableURLRequest(url: NSURL(string: "https://api.geospark.co/v1/api/trips/")! as URL,
                                        cachePolicy: .useProtocolCachePolicy,
                                    timeoutInterval: 10.0)
request.httpMethod = "PUT"
request.allHTTPHeaderFields = headers
request.httpBody = postData as Data

let session = URLSession.shared
let dataTask = session.dataTask(with: request as URLRequest, completionHandler: { (data, response, error) -> Void in
  if (error != nil) {
    print(error)
  } else {
    let httpResponse = response as? HTTPURLResponse
    print(httpResponse)
  }
})

dataTask.resume()
```
{% endtab %}
{% endtabs %}

{% api-method method="get" host="https://api.geospark.co/v1" path="/api/trips/summary/" %}
{% api-method-summary %}
Trip Summary API
{% endapi-method-summary %}

{% api-method-description %}
This API helps you to get the trip summary of given trip\_id with its route, distance and duration.  
**Note:** distance\_covered is in meters and duration is in seconds.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Api-Key" type="string" required=true %}
Your API Key Here
{% endapi-method-parameter %}

{% api-method-parameter name="Content-Type" type="string" required=true %}
application/json
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="trip\_id" type="string" required=true %}
 Trip\_id of the trip.  
Eg.  5e661dc1323y7jbckdbljsbds
{% endapi-method-parameter %}

{% api-method-parameter name="mapmatched" type="boolean" required=false %}
this is false by default and true returns map matched route points.
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
        "trip_id": "5e5e22e037227918f1b839b4",
        "user_id": "5e5e22d837227918f1b839b3",
        "project_id": "5e5cfafa37227918f8b838e1",
        "distance_covered": 3449,
        "duration": 14,
        "trip_status": "completed",
        "route": [
            {
                "activity": "BICYCLE",
                "coordinates": {
                    "type": "Point",
                    "coordinates": [
                        77.622115,
                        12.91713
                    ]
                },
                "recorded_at": "2020-03-03T09:26:58.633000"
            },
            {
                "activity": "BICYCLE",
                "coordinates": {
                    "type": "Point",
                    "coordinates": [
                        77.622579,
                        12.917294
                    ]
                },
                "recorded_at": "2020-03-03T09:26:58.988000"
            },
            {
                "activity": "BICYCLE",
                "coordinates": {
                    "type": "Point",
                    "coordinates": [
                        77.639228,
                        12.916307
                    ]
                },
                "recorded_at": "2020-03-03T09:27:06.456000"
            },
            {
                "activity": "BICYCLE",
                "coordinates": {
                    "type": "Point",
                    "coordinates": [
                        77.639523,
                        12.916419
                    ]
                },
                "recorded_at": "2020-03-03T09:27:06.812000"
            },
            {
                "activity": "BICYCLE",
                "coordinates": {
                    "type": "Point",
                    "coordinates": [
                        77.639755,
                        12.916529
                    ]
                },
                "recorded_at": "2020-03-03T09:27:07.168000"
            },
            {
                "activity": "WALK",
                "coordinates": {
                    "type": "Point",
                    "coordinates": [
                        77.650239,
                        12.924304
                    ]
                },
                "recorded_at": "2020-03-03T09:27:12.858000"
            }
        ]
    }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

### Sample Call

{% tabs %}
{% tab title="cURL" %}
```javascript
curl --location --request GET 'https://api.geospark.co/v1/api/trips/summary/?trip_id=5e60e52421497749c95efb56&mapmatched=true' \
--header 'Api-key: 0dcc328d6bc947e0b39722813cfb5f71' \
--header 'Content-Type: application/json'
```
{% endtab %}

{% tab title="Go" %}
```go
package main

import (
  "fmt"
  "net/http"
  "io/ioutil"
)

func main() {

  url := "https://api.geospark.co/v1/api/trips/summary/?trip_id=5e60e52421497749c95efb56&mapmatched=true"
  method := "GET"

  client := &http.Client {
  }
  req, err := http.NewRequest(method, url, nil)

  if err != nil {
    fmt.Println(err)
  }
  req.Header.Add("Api-key", "0dcc328d6bc947e0b39722813cfb5f71")
  req.Header.Add("Content-Type", "application/json")

  res, err := client.Do(req)
  defer res.Body.Close()
  body, err := ioutil.ReadAll(res.Body)

  fmt.Println(string(body))
}
```
{% endtab %}

{% tab title="Java" %}
```java
OkHttpClient client = new OkHttpClient().newBuilder()
  .build();
Request request = new Request.Builder()
  .url("https://api.geospark.co/v1/api/trips/summary/?trip_id=5e60e52421497749c95efb56&mapmatched=true")
  .method("GET", null)
  .addHeader("Api-key", "0dcc328d6bc947e0b39722813cfb5f71")
  .addHeader("Content-Type", "application/json")
  .build();
Response response = client.newCall(request).execute();
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
var settings = {
  "url": "https://api.geospark.co/v1/api/trips/summary/?trip_id=5e60e52421497749c95efb56&mapmatched=true",
  "method": "GET",
  "timeout": 0,
  "headers": {
    "Api-key": "0dcc328d6bc947e0b39722813cfb5f71",
    "Content-Type": "application/json"
  },
};

$.ajax(settings).done(function (response) {
  console.log(response);
});
```
{% endtab %}

{% tab title="Python" %}
```python
import requests

url = "https://api.geospark.co/v1/api/trips/summary/?trip_id=5e60e52421497749c95efb56&mapmatched=true"

payload = {}
headers = {
  'Api-key': '0dcc328d6bc947e0b39722813cfb5f71',
  'Content-Type': 'application/json'
}

response = requests.request("GET", url, headers=headers, data = payload)

print(response.text.encode('utf8'))

```
{% endtab %}

{% tab title="Swift" %}
```swift
import Foundation

var semaphore = DispatchSemaphore (value: 0)

var request = URLRequest(url: URL(string: "https://api.geospark.co/v1/api/trips/summary/?trip_id=5e60e52421497749c95efb56&mapmatched=true")!,timeoutInterval: Double.infinity)
request.addValue("0dcc328d6bc947e0b39722813cfb5f71", forHTTPHeaderField: "Api-key")
request.addValue("application/json", forHTTPHeaderField: "Content-Type")

request.httpMethod = "GET"

let task = URLSession.shared.dataTask(with: request) { data, response, error in 
  guard let data = data else {
    print(String(describing: error))
    return
  }
  print(String(data: data, encoding: .utf8)!)
  semaphore.signal()
}

task.resume()
semaphore.wait()

```
{% endtab %}
{% endtabs %}

