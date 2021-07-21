---
description: >-
  The Get Events API lets you fetch the entry or exit events of the users from
  your event enabled geofences. The API also lets you filter by user or
  geofence, or location, and other options.
---

# Events

{% api-method method="get" host="https://api.geospark.co/v1" path="/api/event/" %}
{% api-method-summary %}
Get Events API
{% endapi-method-summary %}

{% api-method-description %}
This API is responsible for giving the list of events.
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
{% api-method-parameter name="start\_date" type="string" required=false %}
This field can be used for defining a start date from which the list of events needs to shown.  
**Input Data:** 2018-10-19
{% endapi-method-parameter %}

{% api-method-parameter name="end\_date" type="string" required=false %}
This field can be used to define a range of time till when the last document needs to be provided. 'end\_date' should always be greater than 'start\_date'. If end\_date is provided then start\_date should also be provided. If only start\_date is passed, the event list for same day will be returned.   
**Input Data:** 2018-10-20
{% endapi-method-parameter %}

{% api-method-parameter name="user\_id" type="string" required=false %}
Filters events data for the given user\_id.
{% endapi-method-parameter %}

{% api-method-parameter name="page\_number" type="integer" required=false %}
Returns the data in the page provided. A page will have a maximum of 10 entries. If the response returns an empty list in data field, it is safe to assume the pages are exhausted.
{% endapi-method-parameter %}

{% api-method-parameter name="geofence\_id" type="string" required=false %}
Returns Events only for the given geofence\_id.  
  
**Input Data:**  5bd2aee1eec1a50d8faf1293
{% endapi-method-parameter %}

{% api-method-parameter name="location\_id" type="string" required=false %}
 Used to check if there's an event associated with a particular location, identified by it's location\_id.  
  
**Input Data:**  5bd2ab9deec1a50c7fa75581
{% endapi-method-parameter %}

{% api-method-parameter name="event\_type" type="string" required=false %}
Filter by entry or exit type events.  
  
**Input Data:** entry or exit
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
        "next_page": 2,
        "pages": 2,
        "prev_page": null,
        "account_id": "5bbdd7a8eec1a511b246490d",
        "events": [
            {
                "id": "5bfa9599eec1a50778901421",
                "user_id": "5bdad5f7eec1a507afa2fece",
                "geofence_id": "5bc89a4feec1a50e738db301",
                "location_id": "5bfa9595eec1a5077890141e",
                "app_id": "5bbdd865eec1a511b246490e_1",
                "event_type": "entry",
                "coordinates": {
                    "type": "Point",
                    "coordinates": [
                        -0.11893,
                        51.49614
                    ]
                },
                "recorded_at": "2018-10-02T10:44:00.000",
                "timezone_offset": "+0100",
                "created_at": "2018-11-25T12:29:09.273"
            },
            {
                "id": "5bfa959aeec1a50778901422",
                "user_id": "5bdad5f7eec1a507afa2fece",
                "geofence_id": "5bc89a75eec1a50e738db302",
                "location_id": "5bfa9595eec1a5077890141e",
                "app_id": "5bbdd865eec1a511b246490e_1",
                "event_type": "entry",
                "coordinates": {
                    "type": "Point",
                    "coordinates": [
                        -0.11893,
                        51.49614
                    ]
                },
                "recorded_at": "2018-10-02T10:44:00.000",
                "timezone_offset": "+0100",
                "created_at": "2018-11-25T12:29:13.925"
            },
            {
                "id": "5bfa985beec1a507c7a12711",
                "user_id": "5bdad5f7eec1a507afa2fece",
                "geofence_id": "5bc89a4feec1a50e738db301",
                "location_id": "5bfa9854eec1a507c7a1270e",
                "app_id": "5bbdd865eec1a511b246490e_1",
                "event_type": "exit",
                "coordinates": {
                    "type": "Point",
                    "coordinates": [
                        -87.64593,
                        71.86793
                    ]
                },
                "timezone_offset": "+0100",
                "started_at": "2018-10-02T11:42:00.000",
                "ended_at": "2018-10-02T07:27:08.000",
                "created_at": "2018-11-25T12:40:52.981"
            },
            {
                "id": "5bfa985ceec1a507c7a12712",
                "user_id": "5bdad5f7eec1a507afa2fece",
                "geofence_id": "5bc89a75eec1a50e738db302",
                "location_id": "5bfa9854eec1a507c7a1270e",
                "app_id": "5bbdd865eec1a511b246490e_1",
                "event_type": "exit",
                "coordinates": {
                    "type": "Point",
                    "coordinates": [
                        -87.64593,
                        71.86793
                    ]
                },
                "timezone_offset": "+0100",
                "started_at": "2018-10-02T11:42:00.000",
                "ended_at": "2018-10-02T07:27:08.000",
                "created_at": "2018-11-25T12:40:59.632"
            },
            {
                "id": "5bfa98efeec1a507f7b5b425",
                "user_id": "5bdad5f7eec1a507afa2fece",
                "geofence_id": "5bc89a4feec1a50e738db301",
                "location_id": "5bfa98eaeec1a507f7b5b422",
                "app_id": "5bbdd865eec1a511b246490e_1",
                "event_type": "entry",
                "coordinates": {
                    "type": "Point",
                    "coordinates": [
                        -0.11893,
                        51.49614
                    ]
                },
                "recorded_at": "2018-10-02T10:44:00.000",
                "timezone_offset": "+0100",
                "created_at": "2018-11-25T12:43:22.679"
            },
            {
                "id": "5bfa98f1eec1a507f7b5b426",
                "user_id": "5bdad5f7eec1a507afa2fece",
                "geofence_id": "5bc89a75eec1a50e738db302",
                "location_id": "5bfa98eaeec1a507f7b5b422",
                "app_id": "5bbdd865eec1a511b246490e_1",
                "event_type": "entry",
                "coordinates": {
                    "type": "Point",
                    "coordinates": [
                        -0.11893,
                        51.49614
                    ]
                },
                "recorded_at": "2018-10-02T10:44:00.000",
                "timezone_offset": "+0100",
                "created_at": "2018-11-25T12:43:27.103"
            },
            {
                "id": "5bfa992aeec1a507f7b5b435",
                "user_id": "5bdad5f7eec1a507afa2fece",
                "geofence_id": "5bc89a4feec1a50e738db301",
                "location_id": "5bfa98f1eec1a507f7b5b432",
                "app_id": "5bbdd865eec1a511b246490e_1",
                "event_type": "exit",
                "coordinates": {
                    "type": "Point",
                    "coordinates": [
                        -87.64593,
                        71.86793
                    ]
                },
                "timezone_offset": "+0100",
                "started_at": "2018-10-02T11:42:00.000",
                "ended_at": "2018-10-02T07:27:08.000",
                "created_at": "2018-11-25T12:43:29.353"
            },
            {
                "id": "5bfa992deec1a507f7b5b436",
                "user_id": "5bdad5f7eec1a507afa2fece",
                "geofence_id": "5bc89a75eec1a50e738db302",
                "location_id": "5bfa98f1eec1a507f7b5b432",
                "app_id": "5bbdd865eec1a511b246490e_1",
                "event_type": "exit",
                "coordinates": {
                    "type": "Point",
                    "coordinates": [
                        -87.64593,
                        71.86793
                    ]
                },
                "timezone_offset": "+0100",
                "started_at": "2018-10-02T11:42:00.000",
                "ended_at": "2018-10-02T07:27:08.000",
                "created_at": "2018-11-25T12:44:26.586"
            },
            {
                "id": "5bfa9961eec1a5080f9bb823",
                "user_id": "5bdad5f7eec1a507afa2fece",
                "geofence_id": "5bc89a4feec1a50e738db301",
                "location_id": "5bfa995ceec1a5080f9bb820",
                "app_id": "5bbdd865eec1a511b246490e_1",
                "event_type": "entry",
                "coordinates": {
                    "type": "Point",
                    "coordinates": [
                        -0.11893,
                        51.49614
                    ]
                },
                "recorded_at": "2018-10-02T10:44:00.000",
                "timezone_offset": "+0100",
                "created_at": "2018-11-25T12:45:21.302"
            },
            {
                "id": "5bfa9962eec1a5080f9bb824",
                "user_id": "5bdad5f7eec1a507afa2fece",
                "geofence_id": "5bc89a75eec1a50e738db302",
                "location_id": "5bfa995ceec1a5080f9bb820",
                "app_id": "5bbdd865eec1a511b246490e_1",
                "event_type": "entry",
                "coordinates": {
                    "type": "Point",
                    "coordinates": [
                        -0.11893,
                        51.49614
                    ]
                },
                "recorded_at": "2018-10-02T10:44:00.000",
                "timezone_offset": "+0100",
                "created_at": "2018-11-25T12:45:22.602"
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
```text
  curl -X GET \
    'https://api.geospark.co/v1/api/event/?geofence_id=5bc89a4feec1a50e738db301&location_id=5bd2ab9deec1a50c7fa75581&event_type=entry&page_number=1' \
    -H 'Api-Key: 2fd72b3b94b149018957eae89c2d1c86'
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
 var settings = {
    "async": true,
    "crossDomain": true,
    "url": "https://api.geospark.co/v1/api/event/?geofence_id=5bc89a4feec1a50e738db301&location_id=5bd2ab9deec1a50c7fa75581&event_type=entry&page_number=1",
    "method": "GET",
    "headers": {
      "Api-Key": "2fd72b3b94b149018957eae89c2d1c86"
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

  url = "https://api.geospark.co/v1/api/event/"

  querystring = {"geofence_id":"5bc89a4feec1a50e738db301","location_id":"5bd2ab9deec1a50c7fa75581","event_type":"entry","page_number":"1"}

  headers = {
      'Api-Key': "2fd72b3b94b149018957eae89c2d1c86"
      }

  response = requests.request("GET", url, headers=headers, params=querystring)

  print(response.text)
```
{% endtab %}

{% tab title="Java" %}
```java
 OkHttpClient client = new OkHttpClient();

  Request request = new Request.Builder()
    .url("https://api.geospark.co/v1/api/event/?geofence_id=5bc89a4feec1a50e738db301&location_id=5bd2ab9deec1a50c7fa75581&event_type=entry&page_number=1")
    .get()
    .addHeader("Api-Key", "2fd72b3b94b149018957eae89c2d1c86")
    .build();

  Response response = client.newCall(request).execute(); 
```
{% endtab %}

{% tab title="Swift" %}
```swift
  import Foundation

  let headers = [
    "Api-Key": "2fd72b3b94b149018957eae89c2d1c86"
  ]

  let request = NSMutableURLRequest(url: NSURL(string: "https://api.geospark.co/v1/api/event/?geofence_id=5bc89a4feec1a50e738db301&location_id=5bd2ab9deec1a50c7fa75581&event_type=entry&page_number=1")! as URL,
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

{% tab title="Go" %}
```go
  package main

  import (
    "fmt"
    "net/http"
    "io/ioutil"
  )

  func main() {

    url := "https://api.geospark.co/v1/api/event/?geofence_id=5bc89a4feec1a50e738db301&location_id=5bd2ab9deec1a50c7fa75581&event_type=entry&page_number=1"

    req, _ := http.NewRequest("GET", url, nil)

    req.Header.Add("Api-Key", "2fd72b3b94b149018957eae89c2d1c86")

    res, _ := http.DefaultClient.Do(req)

    defer res.Body.Close()
    body, _ := ioutil.ReadAll(res.Body)

    fmt.Println(res)
    fmt.Println(string(body))

  }
```
{% endtab %}
{% endtabs %}

