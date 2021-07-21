---
description: >-
  This set of APIs will help in fetching the user data, user location data,
  insights and update the user events.
---

# Users, Locations and Insights

{% hint style="info" %}
* Pass your secret API key in the header
* API parameter **page\_number**, gives a maximum of 10 entries per page in response
* Suffix of **app\_id** represents **device platform** , i.e. **"\_1" for android and "\_2" for iOS**
* For list APIs the **"next\_page"** and **"prev\_page"** fields will be **"null"** if not present. and **"pages"** will be **0** if not present.
{% endhint %}

{% api-method method="get" host=" https://api.geospark.co/v1" path="/api/user/" %}
{% api-method-summary %}
Get User API
{% endapi-method-summary %}

{% api-method-description %}
Get User API provides the list of users who are using your app corresponding to the project secret API key provided.  
**Note:** speed is in km/hr, accuracy and altitude is in meters.  
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Content-Type" type="string" required=true %}
 application/json
{% endapi-method-parameter %}

{% api-method-parameter name="Api-Key" type="string" required=true %}
 ~~33223kjhdcscijhb5sdbsdmjsdcbj5f~~
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="user\_id" type="string" required=false %}
For searching a particular user.   
**Note: Use this field for only searching. No other field should be combined with it.  
  
E.g.**  `/api/user/?user_id=5c2f43e8fb979679beba0cce`  
  
**Input Data:**  5bd2aee1eec1a55d8faf1193
{% endapi-method-parameter %}

{% api-method-parameter name="timezone\_offset" type="string" required=false %}
If timezone is provided then the response will be returned as per provided local timezone.   
If the timezone is not passed, response will be returned in UTC.  
  
**Input Data:**  Asia/Kolkata
{% endapi-method-parameter %}

{% api-method-parameter name="start\_date" type="string" required=false %}
This field can be used for defining a start date from which the list of users needs to shown.  
  
**Input Data:**  2018-10-19  
{% endapi-method-parameter %}

{% api-method-parameter name="end\_date" type="string" required=false %}
This field can be used to define a range of time till when the last document needs to be provided. 'end\_date' should always be greater than 'start\_date'.   
If end\_date is provided then start\_date should also be provided. If only start\_date is passed, the user list for same day will be returned.  
  
**Input Data:** 2018-10-20
{% endapi-method-parameter %}

{% api-method-parameter name="page\_number" type="integer" required=false %}
This field can be used for getting 10 entries at a time. if the response returns an empty list in data field, it is safe to assume the pages are exhausted.
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
        "account_id": "5d15e6029694061560ed8d64",
        "users": [
            {
                "id": "5d947b80e47bae6d700650cd",
                "app_id": "5d15e65a9694061560ed8de7_1",
                "device_token": "c6IDEE9eq7A:APA91bEg_q3zDuKNmlwIsSdDAdycCxrM-xGA8FcCRwIrTt5gCXCbAQWg2pUc25dB_-MbWeBrEEtgkCN0lbkwjuqNhls7pDotBSzdHTsyLOPVJ8i2dnrGSWj8aLHHYwCkX5xRCey2SeEe",
                "device_uuid": "51ad2d53-9057-49c3-93cf-a4817045bf48",
                "description": "James",
                "brand": "asus",
                "model": "ASUS_Z012DB",
                "os_version": "26",
                "sdk_version": "2.1.1",
                "device_arn": "arn:aws:sns:us-east-1:218937252071:endpoint/GCM/app_5d15e65a9694061560ed8de7_1_ddba9c68-dee2-4e33-8258-ff7f7515a672/4f497606-3ae6-3c1d-99f6-a015af4fd42d",
                "geofence_events": true,
                "motion_events": true,
                "trips_events": true,
                "is_deleted": false,
                "created_at": "2019-10-02T15:57:11.970",
                "last_location_update": {
                    "id": "5d947b82e47bae6d700650ce",
                    "coordinates": {
                        "type": "Point",
                        "coordinates": [
                            77.6354213,
                            12.9143926
                        ]
                    },
                    "speed": 0.0,
                    "accuracy": 26.04800033569336,
                    "altitude": 795.8999633789062,
                    "activity": "WALK",
                    "recorded_at": "2019-10-02T10:27:14.053",
                    "timezone_offset": "+0530",
                    "net_stat": true,
                    "gps_stat": true,
                    "motion_stat": true,
                    "app_stat": "MANUAL",
                    "battery_remaining": 57,
                    "bat_stat": "Unknown",
                    "bat_saver_mode": false,
                    "location_permission": true,
                    "airplane_mode": false,
                    "created_at": "2019-10-02T10:27:14.256"
                }
            },
            {
                "id": "5d94703396940667bc0a1732",
                "app_id": "5d15e65a9694061560ed8de7_1",
                "device_token": "d1QlKpq-QJU:APA91bFCKZIG3Ypi6n6Z5zZyo6w-E0ZJg6GRxoT7aImxURvlFDtlRkGllykc6g3kW7C0aPDYN2L8ouMr--WVDrJA3tU0pHRA-ENuNc0PIZUqipqKNfmq4NfELNGIjzRGJPtypK0PIKIs",
                "device_uuid": "3da30854-1525-48a8-812d-bb17c797df47",
                "description": "sujith",
                "brand": "samsung",
                "model": "SM-G950F",
                "os_version": "28",
                "sdk_version": "2.1.1",
                "device_arn": "arn:aws:sns:us-east-1:218937252071:endpoint/GCM/app_5d15e65a9694061560ed8de7_1_ddba9c68-dee2-4e33-8258-ff7f7515a672/76560c7e-dfed-3b0f-85a8-8df5b7d75e19",
                "geofence_events": true,
                "motion_events": true,
                "trips_events": true,
                "is_deleted": false,
                "created_at": "2019-10-02T15:08:59.020",
                "last_location_update": {
                    "id": "5d94703596940667bc0a1736",
                    "coordinates": {
                        "type": "Point",
                        "coordinates": [
                            77.6353995,
                            12.9144113
                        ]
                    },
                    "speed": 0.0,
                    "accuracy": 28.9419994354248,
                    "altitude": 795.899963378906,
                    "activity": "STOP",
                    "address": "GeoSpark, 164, 9th Main Road, Sector 5, HSR Layout Ward, Bommanahalli Zone, Bengaluru, Bangalore Urban, Karnataka, 560102, India"
                    "timezone_offset": "+0530",
                    "started_at": "2019-10-02T09:38:59.883",
                    "ended_at": "2019-10-02T09:39:00.512",
                    "net_stat": true,
                    "gps_stat": true,
                    "motion_stat": true,
                    "app_stat": "FOREGROUND",
                    "battery_remaining": 94,
                    "bat_stat": "Unknown",
                    "bat_saver_mode": false,
                    "location_permission": true,
                    "airplane_mode": false,
                    "created_at": "2019-10-02T09:39:01.371"
                }
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
    'https://api.geospark.co/v1/api/user/?start_date=2019-01-10&end_date=2019-01-12&timezone_offset=Asia/Kolkata' \
    -H 'Api-Key: 28c44e3f33de40fbafa0f9dad776b6b2'  
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
  var settings = {
    "async": true,
    "crossDomain": true,
    "url": "https://api.geospark.co/v1/api/user/?start_date=2019-01-10&end_date=2019-01-12&timezone_offset=Asia/Kolkata"",
    "method": "GET",
    "headers": {
      "Api-Key": "28c44e3f33de40fbafa0f9dad776b6b2"
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

  url = "https://api.geospark.co/v1/api/user/"

  querystring = {"start_date":"2019-01-10","end_date":"2019-01-12","timezone_offset":"Asia/Kolkata"}

  headers = {
      'Api-Key': "28c44e3f33de40fbafa0f9dad776b6b2"
      }

  response = requests.request("GET", url, headers=headers, params=querystring)

  print(response.text)
```
{% endtab %}

{% tab title="Java" %}
```java
  OkHttpClient client = new OkHttpClient();

  Request request = new Request.Builder()
    .url("https://api.geospark.co/v1/api/user/?start_date=2019-01-10&end_date=2019-01-12&timezone_offset=Asia/Kolkata")
    .get()
    .addHeader("Api-Key", "28c44e3f33de40fbafa0f9dad776b6b2")
    .build();

  Response response = client.newCall(request).execute();
```
{% endtab %}

{% tab title="Swift" %}
```swift
  import Foundation

  let headers = [
    "Api-Key": "28c44e3f33de40fbafa0f9dad776b6b2"
  ]

  let request = NSMutableURLRequest(url: NSURL(string: "https://api.geospark.co/v1/api/user/?start_date=2019-01-10&end_date=2019-01-12&timezone_offset=Asia/Kolkata")! as URL,
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

    url := "https://api.geospark.co/v1/api/user/?start_date=2019-01-10&end_date=2019-01-12&timezone_offset=Asia/Kolkata"

    req, _ := http.NewRequest("GET", url, nil)

    req.Header.Add("Api-Key", "28c44e3f33de40fbafa0f9dad776b6b2")

    res, _ := http.DefaultClient.Do(req)

    defer res.Body.Close()
    body, _ := ioutil.ReadAll(res.Body)

    fmt.Println(res)
    fmt.Println(string(body))
  }
```
{% endtab %}
{% endtabs %}

{% api-method method="get" host=" https://api.geospark.co/v1" path="/api/location/" %}
{% api-method-summary %}
Get Location API
{% endapi-method-summary %}

{% api-method-description %}
Get Location API provides the list of locations of the users who are using your app for a specified project corresponding to the project secret API key provided by you.  
**Note:** speed is in km/hr, accuracy and altitude is in meters.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Content-Type" type="string" required=true %}
 application/json
{% endapi-method-parameter %}

{% api-method-parameter name="Api-Key" type="string" required=true %}
 ~~33223kjhdcscijhb5sdbsdmjsdcbj5f~~
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="points\_encoded" type="boolean" required=false %}
This field can be used to get the location data in encoded polyline and time aware polyline. This returns only the data for current date and to get the other data using start\_date and end\_date is recommended. It's false by default. points\_encoded and timezone-offset are exclusive and can't be used together.
{% endapi-method-parameter %}

{% api-method-parameter name="user\_id" type="string" required=true %}
Filters the location data for the given user\_id.  
  
**Input Data:** 5bb3177a02a89b3c7a6a8d4f
{% endapi-method-parameter %}

{% api-method-parameter name="timezone\_offset" type="string" required=false %}
If timezone is provided then the response will be returned as per provided local timezone.   
If the timezone is not passed, response will be returned in UTC. If points\_encoded value is true, then this value will be UTC by default.  
  
**Input Data:** Asia/Kolkata
{% endapi-method-parameter %}

{% api-method-parameter name="start\_date" type="string" required=false %}
This field can be used for defining a start date from which the list of user's locations needs to shown.  
  
**Input Data:** 2018-10-19
{% endapi-method-parameter %}

{% api-method-parameter name="end\_date" type="string" required=false %}
This field can be used to define a range of time till when the last document needs to be provided. 'end\_date' should always be greater than 'start\_date'.   
If end\_date is provided then start\_date should also be provided. If only start\_date is passed, the user list for same day will be returned.  
   
**Input Data:** 2018-10-20
{% endapi-method-parameter %}

{% api-method-parameter name="page\_number" type="integer" required=false %}
This field can be used for getting 10 entries at a time. if the response returns an empty list in data field, it is safe to assume the pages are exhausted. If points\_encoded value is true, then this value will not be considered.
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
        "pages": 15,
        "prev_page": null,
        "app_id": "5d68c56255c9d50640802ff8_2",
        "user_id": "5d931e4896940667bc0834dd",
        "locations": [
            {
                "id": "5d93696096940667bc0893fe",
                "coordinates": {
                    "type": "Point",
                    "coordinates": [
                        77.63033406133458,
                        13.01788769586474
                    ]
                },
                "speed": 0.0,
                "accuracy": 10.0,
                "altitude": 897.4580940078257,
                "activity": "STOP",
                "address": "GeoSpark, 164, 9th Main Road, Sector 5, HSR Layout Ward, Bommanahalli Zone, Bengaluru, Bangalore Urban, Karnataka, 560102, India"
                "timezone_offset": "+0530",
                "started_at": "2019-10-01T14:57:05.444",
                "ended_at": "2019-10-01T14:57:35.986",
                "net_stat": true,
                "gps_stat": true,
                "motion_stat": true,
                "app_stat": "BACKGROUND",
                "battery_remaining": 98,
                "bat_stat": "Charging",
                "created_at": "2019-10-01T14:57:36.300"
            },
            {
                "id": "5d93692b96940667bc08939a",
                "coordinates": {
                    "type": "Point",
                    "coordinates": [
                        77.63077092364209,
                        13.017818061647022
                    ]
                },
                "speed": 18.0,
                "accuracy": 5.0,
                "altitude": 902.267219543457,
                "activity": "DRIVE",
                "timezone_offset": "+0530",
                "net_stat": true,
                "gps_stat": true,
                "motion_stat": true,
                "app_stat": "BACKGROUND",
                "battery_remaining": 97,
                "bat_stat": "Charging",
                "created_at": "2019-10-01T14:56:43.420",
                "recorded_at": "2019-10-01T14:56:43.092"
            },
            {
                "id": "5d93690396940667bc089332",
                "coordinates": {
                    "type": "Point",
                    "coordinates": [
                        77.63258644386906,
                        13.017401564878428
                    ]
                },
                "speed": 20.0,
                "accuracy": 5.0,
                "altitude": 902.8652420043945,
                "activity": "DRIVE",
                "timezone_offset": "+0530",
                "net_stat": true,
                "gps_stat": true,
                "motion_stat": true,
                "app_stat": "BACKGROUND",
                "battery_remaining": 97,
                "bat_stat": "Charging",
                "created_at": "2019-10-01T14:56:03.421",
                "recorded_at": "2019-10-01T14:56:03.078"
            },
            {
                "id": "5d9368e196940667bc0892e5",
                "coordinates": {
                    "type": "Point",
                    "coordinates": [
                        77.63434211730737,
                        13.016522638511859
                    ]
                },
                "speed": 22.0,
                "accuracy": 10.0,
                "altitude": 907.4284744262695,
                "activity": "DRIVE",
                "timezone_offset": "+0530",
                "net_stat": true,
                "gps_stat": true,
                "motion_stat": true,
                "app_stat": "BACKGROUND",
                "battery_remaining": 97,
                "bat_stat": "Charging",
                "created_at": "2019-10-01T14:55:29.285",
                "recorded_at": "2019-10-01T14:55:29.082"
            },
            {
                "id": "5d9368ca96940667bc0892b9",
                "coordinates": {
                    "type": "Point",
                    "coordinates": [
                        77.63618052012998,
                        13.01624611952623
                    ]
                },
                "speed": 15.0,
                "accuracy": 5.0,
                "altitude": 909.6889724731445,
                "activity": "DRIVE",
                "timezone_offset": "+0530",
                "net_stat": true,
                "gps_stat": true,
                "motion_stat": true,
                "app_stat": "BACKGROUND",
                "battery_remaining": 97,
                "bat_stat": "Charging",
                "created_at": "2019-10-01T14:55:06.267",
                "recorded_at": "2019-10-01T14:55:06.081"
            },
            {
                "id": "5d93688f96940667bc089232",
                "coordinates": {
                    "type": "Point",
                    "coordinates": [
                        77.6364021391822,
                        13.017499802693466
                    ]
                },
                "speed": 23.0,
                "accuracy": 10.0,
                "altitude": 908.5708084106445,
                "activity": "DRIVE",
                "timezone_offset": "+0530",
                "net_stat": true,
                "gps_stat": true,
                "motion_stat": true,
                "app_stat": "BACKGROUND",
                "battery_remaining": 97,
                "bat_stat": "Charging",
                "created_at": "2019-10-01T14:54:07.437",
                "recorded_at": "2019-10-01T14:54:07.086"
            },
            {
                "id": "5d93686de47bae6d7004c5d3",
                "coordinates": {
                    "type": "Point",
                    "coordinates": [
                        77.63686545491203,
                        13.01945139072632
                    ]
                },
                "speed": 19.0,
                "accuracy": 10.068562831803998,
                "altitude": 909.973518371582,
                "activity": "DRIVE",
                "timezone_offset": "+0530",
                "net_stat": true,
                "gps_stat": true,
                "motion_stat": true,
                "app_stat": "BACKGROUND",
                "battery_remaining": 97,
                "bat_stat": "Charging",
                "created_at": "2019-10-01T14:53:33.295",
                "recorded_at": "2019-10-01T14:53:33.091"
            },
            {
                "id": "5d93684596940667bc0891b4",
                "coordinates": {
                    "type": "Point",
                    "coordinates": [
                        77.63702449676983,
                        13.021435016003837
                    ]
                },
                "speed": 10.0,
                "accuracy": 11.166095059679792,
                "altitude": 910.216194152832,
                "activity": "DRIVE",
                "timezone_offset": "+0530",
                "net_stat": true,
                "gps_stat": true,
                "motion_stat": true,
                "app_stat": "BACKGROUND",
                "battery_remaining": 97,
                "bat_stat": "Charging",
                "created_at": "2019-10-01T14:52:53.272",
                "recorded_at": "2019-10-01T14:52:53.101"
            },
            {
                "id": "5d93680ae47bae6d7004c4c5",
                "coordinates": {
                    "type": "Point",
                    "coordinates": [
                        77.63657012402616,
                        13.02296174115325
                    ]
                },
                "speed": 0.0,
                "accuracy": 10.0,
                "altitude": 902.1354044576965,
                "activity": "STOP",
                "address": "GeoSpark, 164, 9th Main Road, Sector 5, HSR Layout Ward, Bommanahalli Zone, Bengaluru, Bangalore Urban, Karnataka, 560102, India"
                "timezone_offset": "+0530",
                "started_at": "2019-10-01T14:51:23.087",
                "ended_at": "2019-10-01T14:51:53.976",
                "net_stat": true,
                "gps_stat": true,
                "motion_stat": true,
                "app_stat": "BACKGROUND",
                "battery_remaining": 97,
                "bat_stat": "Charging",
                "created_at": "2019-10-01T14:51:54.176"
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
  'http://api.geospark.co/v1/api/location/?user_id=5c90e5b19533a37823dd4331' \
  -H 'Api-Key: aef49fac20f9475ebb880319b0c54d00' \
  -H 'Postman-Token: 99aa945c-7fbd-4642-ab9c-ca17e66d2579' \
  -H 'cache-control: no-cache'

```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
  var settings = {
    "async": true,
    "crossDomain": true,
    "url": "https://api.geospark.co/v1/api/location/?user_id=5bb3177a02a89b3c7a6a8d4f&start_date=2019-01-06&end_date=2019-01-09&page_number=1",
    "method": "GET",
    "headers": {
      "Api-Key": "eade6d3a72924eb895a19feb44895372"
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

  url = "https://api.geospark.co/v1/api/location/"

  querystring = {"user_id":"5bb3177a02a89b3c7a6a8d4f","start_date":"2019-01-06","end_date":"2019-01-09","page_number":"1"}

  headers = {
      'Api-Key': "eade6d3a72924eb895a19feb44895372"
      }

  response = requests.request("GET", url, headers=headers, params=querystring)

  print(response.text)
```
{% endtab %}

{% tab title="Java" %}
```java
  OkHttpClient client = new OkHttpClient();

  Request request = new Request.Builder()
    .url("https://api.geospark.co/v1/api/location/?user_id=5bb3177a02a89b3c7a6a8d4f&start_date=2019-01-06&end_date=2019-01-09&page_number=1")
    .get()
    .addHeader("Api-Key", "eade6d3a72924eb895a19feb44895372")
    .build();

  Response response = client.newCall(request).execute();
```
{% endtab %}

{% tab title="Swift" %}
```swift
  import Foundation

  let headers = [
    "Api-Key": "eade6d3a72924eb895a19feb44895372"
  ]

  let request = NSMutableURLRequest(url: NSURL(string: "https://api.geospark.co/v1/api/location/?user_id=5bb3177a02a89b3c7a6a8d4f&start_date=2019-01-06&end_date=2019-01-09&page_number=1")! as URL,
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

    url := "https://api.geospark.co/v1/api/location/?user_id=5bb3177a02a89b3c7a6a8d4f&start_date=2019-01-06&end_date=2019-01-09&page_number=1"

    req, _ := http.NewRequest("GET", url, nil)

    req.Header.Add("Api-Key", "eade6d3a72924eb895a19feb44895372")

    res, _ := http.DefaultClient.Do(req)

    defer res.Body.Close()
    body, _ := ioutil.ReadAll(res.Body)

    fmt.Println(res)
    fmt.Println(string(body))

  }
```
{% endtab %}
{% endtabs %}

{% api-method method="put" host="https://" path="api.geospark.co/v1/api/user/" %}
{% api-method-summary %}
 Update User API
{% endapi-method-summary %}

{% api-method-description %}
This API lets you enable or disable the events for the given user\_id.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="content-type" type="string" required=false %}
application/json
{% endapi-method-parameter %}

{% api-method-parameter name="Api-key" type="string" required=false %}
~~33223kjhdcscijhb5sdbsdmjsdcbj5f~~
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="user\_id" type="string" required=true %}
User id which need to be updated.
{% endapi-method-parameter %}

{% api-method-parameter name="motion\_events" type="boolean" required=false %}
Turn on/off events for change in activity.
{% endapi-method-parameter %}

{% api-method-parameter name="geofence\_events" type="boolean" required=false %}
Turn on/off geofence events.
{% endapi-method-parameter %}

{% api-method-parameter name="trips\_events" type="boolean" required=false %}
Turn on/off trips events.
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
    "code": 200,
    "data": {
        "id": "5d948d735f37c615833719d2",
        "account_id": "5d01de8aaa6ad90610ac7aaf",
        "app_id": "5d948d61670dc805827b09b5_2",
        "device_token": "devicetoken",
        "device_uuid": null,
        "description": "postman device test",
        "brand": "Samsung",
        "model": "S8",
        "group_id": null,
        "os_version": "8.1",
        "sdk_version": "2.1",
        "device_arn": null,
        "geofence_events": true,
        "motion_events": true,
        "trips_events": true,
        "metadata": null,
        "is_deleted": false,
        "created_at": "2019-10-02T11:43:47.765",
        "updated_at": "2019-10-02T12:20:34.749"
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
curl -X PUT \
  http://api.geospark.co/v1/api/user/ \
  -H 'Api-Key: cbdd0c41a4e5461e97d1fbedb67f159f' \
  -H 'Content-Type: application/json' \
  -d '{    
    "user_id": "5d948d735f37c615833719d2",
    "geofence_events": true,
    "motion_events": true,
    "trips_events": true
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

    url := "http://api.geospark.co/v1/api/user/"

    payload := strings.NewReader("{\t\n\t\"user_id\": \"5d948d735f37c615833719d2\",\n\t\"geofence_events\": true,\n\t\"motion_events\": true,\n\t\"trips_events\": true\n}")

    req, _ := http.NewRequest("PUT", url, payload)

    req.Header.Add("Api-Key", "cbdd0c41a4e5461e97d1fbedb67f159f")
    req.Header.Add("Content-Type", "application/json")

    res, _ := http.DefaultClient.Do(req)

    defer res.Body.Close()
    body, _ := ioutil.ReadAll(res.Body)

    fmt.Println(res)
    fmt.Println(string(body))

}
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "http://api.geospark.co/v1/api/user/",
  "method": "PUT",
  "headers": {
    "Api-Key": "cbdd0c41a4e5461e97d1fbedb67f159f",
    "Content-Type": "application/json"
  },
  "processData": false,
  "data": "{\t\n\t\"user_id\": \"5d948d735f37c615833719d2\",\n\t\"geofence_events\": true,\n\t\"motion_events\": true,\n\t\"trips_events\": true\n}"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```
{% endtab %}

{% tab title="Python" %}
```python
import requests

url = "http://api.geospark.co/v1/api/user/"

payload = "{\t\n\t\"user_id\": \"5d948d735f37c615833719d2\",\n\t\"geofence_events\": true,\n\t\"motion_events\": true,\n\t\"trips_events\": true\n}"
headers = {
    'Api-Key': "cbdd0c41a4e5461e97d1fbedb67f159f",
    'Content-Type': "application/json"
    }

response = requests.request("PUT", url, data=payload, headers=headers)

print(response.text)
```
{% endtab %}

{% tab title="Java" %}
```java
OkHttpClient client = new OkHttpClient();

MediaType mediaType = MediaType.parse("application/json");
RequestBody body = RequestBody.create(mediaType, "{\t\n\t\"user_id\": \"5d948d735f37c615833719d2\",\n\t\"geofence_events\": true,\n\t\"motion_events\": true,\n\t\"trips_events\": true\n}");
Request request = new Request.Builder()
  .url("http://api.geospark.co/v1/api/user/")
  .put(body)
  .addHeader("Api-Key", "cbdd0c41a4e5461e97d1fbedb67f159f")
  .addHeader("Content-Type", "application/json")
  .build();

Response response = client.newCall(request).execute();
```
{% endtab %}
{% endtabs %}

{% api-method method="post" host=" https://api.geospark.co/v1" path="/api/user/nearby/" %}
{% api-method-summary %}
Get Nearby Users API
{% endapi-method-summary %}

{% api-method-description %}
This API will provide the list of near by users for the provided user\_id or given location point based on the users latest location update.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Content-Type" type="string" required=true %}
 application/json
{% endapi-method-parameter %}

{% api-method-parameter name="Api-Key" type="string" required=true %}
 ~~33223kjhdcscijhb5sdbsdmjsdcbj5f~~
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="user\_id" type="string" required=false %}
user\_id to find the users around
{% endapi-method-parameter %}

{% api-method-parameter name="radius" type="integer" required=false %}
Default is taken as 1000 metres
{% endapi-method-parameter %}

{% api-method-parameter name="geometry" type="object" required=false %}
 { "coordinates":   
\[ 81.162067, 16.871602 \],   
"type": "Point" // Can be a polygon   
}
{% endapi-method-parameter %}

{% api-method-parameter name="page" type="integer" required=false %}
2
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Returns the list of users falling under the radius of location point or polygon provided based on their latest location update. When user\_id is passed as reference of location point, the response involves the location details of reference user\_id also.  
**Note:** id is the user\_id of the users.
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
        "nearby_user_locations": [
            {
                "id": "5e859a87a15ceb1f5abd25a8",
                "app_id": "5e85988fa15ceb1f59bd1b9e_2",
                "coordinates": {
                    "type": "Point",
                    "coordinates": [
                        77.623,
                        12.9010648962431
                    ]
                },
                "activity": "WALK",
                "accuracy": 65.0,
                "timezone_offset": "+0200",
                "net_stat": true,
                "gps_stat": true,
                "motion_stat": true,
                "app_stat": "BACKGROUND",
                "battery_remaining": 50,
                "bat_stat": "Unplugged",
                "created_at": "2020-04-02T07:55:55.024",
                "device_token": "devicetokenjsdfuyafsdu"
            },
            {
                "id": "5e8598bda15ceb1f5abd25a1",
                "app_id": "5e85988fa15ceb1f59bd1b9e_2",
                "coordinates": {
                    "type": "Point",
                    "coordinates": [
                        77.623,
                        12.9010648962431
                    ]
                },
                "activity": "WALK",
                "accuracy": 65.0,
                "timezone_offset": "+0200",
                "net_stat": true,
                "gps_stat": true,
                "motion_stat": true,
                "app_stat": "BACKGROUND",
                "battery_remaining": 50,
                "bat_stat": "Unplugged",
                "created_at": "2020-04-02T07:48:17.150"
            },
            {
                "id": "5e85989d14d2310740c41645",
                "app_id": "5e85988fa15ceb1f59bd1b9e_2",
                "coordinates": {
                    "type": "Point",
                    "coordinates": [
                        77.635536,
                        12.914478
                    ]
                },
                "activity": "STOP",
                "accuracy": 65.0,
                "timezone_offset": "+0200",
                "started_at": "2020-04-02T07:47:54.711",
                "ended_at": "2020-04-02T07:47:54.711",
                "net_stat": true,
                "gps_stat": true,
                "motion_stat": true,
                "app_stat": "BACKGROUND",
                "battery_remaining": 3,
                "bat_stat": "Charging",
                "created_at": "2020-04-02T07:47:54.869",
                "device_token": "devicetoken"
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
curl --location --request POST 'https://api.geospark.co/v1/api/user/nearby/' \
--header 'Api-Key: a75f0408ea944ec78a4b0fdb92ac34c4' \
--header 'Content-Type: application/json' \
--data-raw '{
	"radius": 3000,
	"geometry": {
		"type": "Point",
		"coordinates": [77.65195, 12.91655]
	}
	
}'
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
var settings = {
  "url": "https://api.geospark.co/v1/api/user/nearby/",
  "method": "POST",
  "timeout": 0,
  "headers": {
    "Api-Key": "a75f0408ea944ec78a4b0fdb92ac34c4",
    "Content-Type": "application/json"
  },
  "data": JSON.stringify({"radius":3000,"geometry":{"type":"Point","coordinates":[77.65195,12.91655]}}),
};

$.ajax(settings).done(function (response) {
  console.log(response);
});
```
{% endtab %}

{% tab title="Python" %}
```python
import requests

url = "https://api.geospark.co/v1/api/user/nearby/"

payload = "{\n\t\"radius\": 3000,\n\t\"geometry\": {\n\t\t\"type\": \"Point\",\n\t\t\"coordinates\": [77.65195, 12.91655]\n\t}\n\t\n}"
headers = {
  'Api-Key': 'a75f0408ea944ec78a4b0fdb92ac34c4',
  'Content-Type': 'application/json'
}

response = requests.request("POST", url, headers=headers, data = payload)

print(response.text.encode('utf8'))

```
{% endtab %}

{% tab title="Java" %}
```java
OkHttpClient client = new OkHttpClient().newBuilder()
  .build();
MediaType mediaType = MediaType.parse("application/json");
RequestBody body = RequestBody.create(mediaType, "{\n\t\"radius\": 3000,\n\t\"geometry\": {\n\t\t\"type\": \"Point\",\n\t\t\"coordinates\": [77.65195, 12.91655]\n\t}\n\t\n}");
Request request = new Request.Builder()
  .url("https://api.geospark.co/v1/api/user/nearby/")
  .method("POST", body)
  .addHeader("Api-Key", "a75f0408ea944ec78a4b0fdb92ac34c4")
  .addHeader("Content-Type", "application/json")
  .build();
Response response = client.newCall(request).execute();
```
{% endtab %}

{% tab title="Swift" %}
```swift
import Foundation

var semaphore = DispatchSemaphore (value: 0)

let parameters = "{\n\t\"radius\": 3000,\n\t\"geometry\": {\n\t\t\"type\": \"Point\",\n\t\t\"coordinates\": [77.65195, 12.91655]\n\t}\n\t\n}"
let postData = parameters.data(using: .utf8)

var request = URLRequest(url: URL(string: "https://api.geospark.co/v1/api/user/nearby/")!,timeoutInterval: Double.infinity)
request.addValue("a75f0408ea944ec78a4b0fdb92ac34c4", forHTTPHeaderField: "Api-Key")
request.addValue("application/json", forHTTPHeaderField: "Content-Type")

request.httpMethod = "POST"
request.httpBody = postData

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

  url := "https://api.geospark.co/v1/api/user/nearby/"
  method := "POST"

  payload := strings.NewReader("{\n	\"radius\": 3000,\n	\"geometry\": {\n		\"type\": \"Point\",\n		\"coordinates\": [77.65195, 12.91655]\n	}\n	\n}")

  client := &http.Client {
  }
  req, err := http.NewRequest(method, url, payload)

  if err != nil {
    fmt.Println(err)
  }
  req.Header.Add("Api-Key", "a75f0408ea944ec78a4b0fdb92ac34c4")
  req.Header.Add("Content-Type", "application/json")

  res, err := client.Do(req)
  defer res.Body.Close()
  body, err := ioutil.ReadAll(res.Body)

  fmt.Println(string(body))
}
```
{% endtab %}
{% endtabs %}

{% api-method method="post" host=" https://api.geospark.co/v1" path="/api/insights/" %}
{% api-method-summary %}
Get User Insights API
{% endapi-method-summary %}

{% api-method-description %}
This API will provide the list of insights with boundary coordinates of the location, last visited detail, type and confidence for each.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Content-Type" type="string" required=true %}
 application/json
{% endapi-method-parameter %}

{% api-method-parameter name="Api-Key" type="string" required=true %}
 ~~33223kjhdcscijhb5sdbsdmjsdcbj5f~~
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="user\_id" type="string" required=false %}
user\_id to find the users around
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
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
    "code": 201,
    "data": [
        {
            "user_id": "5eb94798fc0bfe6584414ec0",
            "geometry": {
                "type": "Polygon",
                "coordinates": [
                    [
                        [
                            76.91802960000003,
                            15.15829215322974
                        ],
                        [
                            76.9182311463149,
                            15.158261341987622
                        ],
                        [
                            76.91841296371013,
                            15.158171924305728
                        ],
                        [
                            76.91855725453212,
                            15.158032653076313
                        ],
                        [
                            76.91864989458988,
                            15.157857161219924
                        ],
                        [
                            76.91868181572923,
                            15.157662627168717
                        ],
                        [
                            76.9186498934488,
                            15.157468093296442
                        ],
                        [
                            76.91855725268583,
                            15.157292601908491
                        ],
                        [
                            76.91841296186385,
                            15.1571533312581
                        ],
                        [
                            76.91823114517382,
                            15.157063914044647
                        ],
                        [
                            76.91802960000003,
                            15.157033102981456
                        ],
                        [
                            76.91782805482622,
                            15.157063914044647
                        ],
                        [
                            76.91764623813619,
                            15.1571533312581
                        ],
                        [
                            76.91750194731421,
                            15.157292601908491
                        ],
                        [
                            76.91740930655124,
                            15.157468093296442
                        ],
                        [
                            76.9173773842708,
                            15.157662627168717
                        ],
                        [
                            76.91740930541016,
                            15.157857161219924
                        ],
                        [
                            76.91750194546792,
                            15.158032653076313
                        ],
                        [
                            76.91764623628991,
                            15.158171924305728
                        ],
                        [
                            76.91782805368514,
                            15.158261341987622
                        ]
                    ]
                ]
            },
            "is_poi": false,
            "last_visited_on": "2020-05-22T16:07:59.001",
            "timezone_offset": "+0530",
            "confidence": "Medium",
            "dataset": {
                "start_time": "2020-04-14T05:20:39.176885",
                "end_time": "2020-05-26T05:20:39.176885",
                "is_weekend": true
            },
            "location_significance": {
                "is_home": true,
                "is_work": false,
                "number_of_visits": 7
            },
            "location_place": {
                "geometry": {
                    "type": "Point",
                    "coordinates": [
                        76.91802960000001,
                        15.157662628105598
                    ]
                },
                "type": "city",
                "name": "Ballari"
            },
            "created_at": "2020-05-26T05:20:45.388",
            "app_id": "5bf3f5d7dd938814bce3545e_1",
            "id": "5ecca735609ea47b89d3d8d3"
        },
        {
            "user_id": "5eb94798fc0bfe6584414ec0",
            "geometry": {
                "type": "Polygon",
                "coordinates": [
                    [
                        [
                            77.636846,
                            12.914286525124147
                        ],
                        [
                            77.63704558227211,
                            12.914255713895772
                        ],
                        [
                            77.637225627905,
                            12.914166296249864
                        ],
                        [
                            77.63736851269373,
                            12.91402702506493
                        ],
                        [
                            77.63746025007966,
                            12.913851533244525
                        ],
                        [
                            77.63749186025221,
                            12.913656999207062
                        ],
                        [
                            77.6374602491233,
                            12.913462465321038
                        ],
                        [
                            77.63736851114632,
                            12.913286973897105
                        ],
                        [
                            77.6372256263576,
                            12.913147703202235
                        ],
                        [
                            77.63704558131576,
                            12.913058285952799
                        ],
                        [
                            77.636846,
                            12.913027474875864
                        ],
                        [
                            77.63664641868425,
                            12.913058285952799
                        ],
                        [
                            77.6364663736424,
                            12.913147703202235
                        ],
                        [
                            77.63632348885368,
                            12.913286973897105
                        ],
                        [
                            77.63623175087672,
                            12.913462465321038
                        ],
                        [
                            77.6362001397478,
                            12.913656999207062
                        ],
                        [
                            77.63623174992036,
                            12.913851533244525
                        ],
                        [
                            77.63632348730627,
                            12.91402702506493
                        ],
                        [
                            77.636466372095,
                            12.914166296249864
                        ],
                        [
                            77.63664641772789,
                            12.914255713895772
                        ]
                    ]
                ]
            },
            "is_poi": false,
            "last_visited_on": "2020-05-15T15:52:53.637",
            "timezone_offset": "+0530",
            "confidence": "Medium",
            "dataset": {
                "start_time": "2020-04-14T05:20:39.176885",
                "end_time": "2020-05-26T05:20:39.176885",
                "is_weekend": true
            },
            "location_significance": {
                "is_home": false,
                "is_work": true,
                "number_of_visits": 5
            },
            "location_place": {
                "geometry": {
                    "type": "Point",
                    "coordinates": [
                        77.636846,
                        12.913657000000006
                    ]
                },
                "type": "amenity",
                "name": "Apollo Clinic"
            },
            "created_at": "2020-05-26T05:20:45.894",
            "app_id": "5bf3f5d7dd938814bce3545e_1",
            "id": "5ecca735609ea47b89d3d8d4"
        },
        {
            "user_id": "5eb94798fc0bfe6584414ec0",
            "geometry": {
                "type": "Polygon",
                "coordinates": [
                    [
                        [
                            76.91378795461243,
                            15.156527562632935
                        ],
                        [
                            76.91398949924582,
                            15.15649675139083
                        ],
                        [
                            76.91417131512415,
                            15.15640733370896
                        ],
                        [
                            76.91431560474238,
                            15.156268062479587
                        ],
                        [
                            76.91440824402731,
                            15.156092570623224
                        ],
                        [
                            76.91444016490047,
                            15.155898036572028
                        ],
                        [
                            76.91440824288641,
                            15.155703502699737
                        ],
                        [
                            76.91431560289634,
                            15.15552801131176
                        ],
                        [
                            76.91417131327813,
                            15.155388740661339
                        ],
                        [
                            76.9139894981049,
                            15.155299323447853
                        ],
                        [
                            76.91378795461243,
                            15.155268512384652
                        ],
                        [
                            76.91358641111997,
                            15.155299323447853
                        ],
                        [
                            76.91340459594674,
                            15.155388740661339
                        ],
                        [
                            76.91326030632852,
                            15.15552801131176
                        ],
                        [
                            76.91316766633847,
                            15.155703502699737
                        ],
                        [
                            76.9131357443244,
                            15.155898036572028
                        ],
                        [
                            76.91316766519755,
                            15.156092570623224
                        ],
                        [
                            76.91326030448248,
                            15.156268062479587
                        ],
                        [
                            76.91340459410071,
                            15.15640733370896
                        ],
                        [
                            76.91358640997905,
                            15.15649675139083
                        ]
                    ]
                ]
            },
            "is_poi": true,
            "last_visited_on": "2020-05-25T15:45:45.645",
            "timezone_offset": "+0530",
            "confidence": "Medium",
            "dataset": {
                "start_time": "2020-04-14T05:20:39.176885",
                "end_time": "2020-05-26T05:20:39.176885",
                "is_weekend": true
            },
            "location_significance": {
                "is_home": false,
                "is_work": false,
                "number_of_visits": 4
            },
            "location_place": {
                "geometry": {
                    "type": "Point",
                    "coordinates": [
                        76.91378795461243,
                        15.155898037508797
                    ]
                },
                "type": "city",
                "name": "Ballari"
            },
            "created_at": "2020-05-26T05:20:46.391",
            "app_id": "5bf3f5d7dd938814bce3545e_1",
            "id": "5ecca735609ea47b89d3d8d5"
        },
        {
            "user_id": "5eb94798fc0bfe6584414ec0",
            "geometry": {
                "type": "Polygon",
                "coordinates": [
                    [
                        [
                            76.887238644259,
                            15.161517684393285
                        ],
                        [
                            76.88744019364809,
                            15.161486873151143
                        ],
                        [
                            76.88762201381655,
                            15.161397455469203
                        ],
                        [
                            76.88776630683934,
                            15.161258184239724
                        ],
                        [
                            76.88785894831001,
                            15.161082692383285
                        ],
                        [
                            76.88789086993613,
                            15.160888158332057
                        ],
                        [
                            76.88785894716867,
                            15.160693624459798
                        ],
                        [
                            76.88776630499262,
                            15.160518133071898
                        ],
                        [
                            76.88762201196984,
                            15.160378862421574
                        ],
                        [
                            76.88744019250674,
                            15.160289445208175
                        ],
                        [
                            76.887238644259,
                            15.160258634145
                        ],
                        [
                            76.88703709601127,
                            15.160289445208175
                        ],
                        [
                            76.88685527654818,
                            15.160378862421574
                        ],
                        [
                            76.88671098352539,
                            15.160518133071898
                        ],
                        [
                            76.88661834134935,
                            15.160693624459798
                        ],
                        [
                            76.88658641858187,
                            15.160888158332057
                        ],
                        [
                            76.886618340208,
                            15.161082692383285
                        ],
                        [
                            76.88671098167868,
                            15.161258184239724
                        ],
                        [
                            76.88685527470145,
                            15.161397455469203
                        ],
                        [
                            76.88703709486991,
                            15.161486873151143
                        ]
                    ]
                ]
            },
            "is_poi": true,
            "last_visited_on": "2020-05-25T13:53:29.529",
            "timezone_offset": "+0530",
            "confidence": "Medium",
            "dataset": {
                "start_time": "2020-04-14T05:20:39.176885",
                "end_time": "2020-05-26T05:20:39.176885",
                "is_weekend": true
            },
            "location_significance": {
                "is_home": false,
                "is_work": false,
                "number_of_visits": 8
            },
            "location_place": {
                "geometry": {
                    "type": "Point",
                    "coordinates": [
                        76.887238644259,
                        15.160888159269144
                    ]
                },
                "type": "amenity",
                "name": "Gowda Canteen"
            },
            "created_at": "2020-05-26T05:20:46.890",
            "app_id": "5bf3f5d7dd938814bce3545e_1",
            "id": "5ecca735609ea47b89d3d8d6"
        },
        {
            "user_id": "5eb94798fc0bfe6584414ec0",
            "geometry": {
                "type": "Polygon",
                "coordinates": [
                    [
                        [
                            76.9124758,
                            15.154857125124147
                        ],
                        [
                            76.9126773430418,
                            15.15482631388205
                        ],
                        [
                            76.91285915748439,
                            15.15473689620021
                        ],
                        [
                            76.91300344596323,
                            15.15459762497087
                        ],
                        [
                            76.91309608451667,
                            15.154422133114533
                        ],
                        [
                            76.9131280051378,
                            15.154227599063349
                        ],
                        [
                            76.91309608337589,
                            15.154033065191049
                        ],
                        [
                            76.91300344411741,
                            15.153857573803043
                        ],
                        [
                            76.91285915563859,
                            15.153718303152587
                        ],
                        [
                            76.91267734190103,
                            15.153628885939076
                        ],
                        [
                            76.9124758,
                            15.153598074875863
                        ],
                        [
                            76.91227425809896,
                            15.153628885939076
                        ],
                        [
                            76.91209244436142,
                            15.153718303152587
                        ],
                        [
                            76.9119481558826,
                            15.153857573803043
                        ],
                        [
                            76.9118555166241,
                            15.154033065191049
                        ],
                        [
                            76.91182359486218,
                            15.154227599063349
                        ],
                        [
                            76.91185551548334,
                            15.154422133114533
                        ],
                        [
                            76.91194815403678,
                            15.15459762497087
                        ],
                        [
                            76.9120924425156,
                            15.15473689620021
                        ],
                        [
                            76.91227425695818,
                            15.15482631388205
                        ]
                    ]
                ]
            },
            "is_poi": true,
            "last_visited_on": "2020-05-21T03:15:48.811",
            "timezone_offset": "+0530",
            "confidence": "Medium",
            "dataset": {
                "start_time": "2020-04-14T05:20:39.176885",
                "end_time": "2020-05-26T05:20:39.176885",
                "is_weekend": true
            },
            "location_significance": {
                "is_home": false,
                "is_work": false,
                "number_of_visits": 1
            },
            "location_place": {
                "geometry": {
                    "type": "Point",
                    "coordinates": [
                        76.9124758,
                        15.154227600000006
                    ]
                },
                "type": "amenity",
                "name": "Ballari Fire Station"
            },
            "created_at": "2020-05-26T05:20:47.390",
            "app_id": "5bf3f5d7dd938814bce3545e_1",
            "id": "5ecca735609ea47b89d3d8d7"
        },
        {
            "user_id": "5eb94798fc0bfe6584414ec0",
            "geometry": {
                "type": "Polygon",
                "coordinates": [
                    [
                        [
                            76.87543486155393,
                            15.169135448164067
                        ],
                        [
                            76.87563641820628,
                            15.169104636921876
                        ],
                        [
                            76.87581824492699,
                            15.16901521923981
                        ],
                        [
                            76.87596254314948,
                            15.16887594801018
                        ],
                        [
                            76.87605518795836,
                            15.168700456153614
                        ],
                        [
                            76.87608711073452,
                            15.16850592210234
                        ],
                        [
                            76.87605518681639,
                            15.168311388230126
                        ],
                        [
                            76.87596254130172,
                            15.168135896842353
                        ],
                        [
                            76.87581824307922,
                            15.167996626192183
                        ],
                        [
                            76.87563641706431,
                            15.167907208978907
                        ],
                        [
                            76.87543486155393,
                            15.16787639791578
                        ],
                        [
                            76.87523330604353,
                            15.167907208978907
                        ],
                        [
                            76.87505148002862,
                            15.167996626192183
                        ],
                        [
                            76.87490718180612,
                            15.168135896842353
                        ],
                        [
                            76.87481453629145,
                            15.168311388230126
                        ],
                        [
                            76.87478261237332,
                            15.16850592210234
                        ],
                        [
                            76.87481453514948,
                            15.168700456153614
                        ],
                        [
                            76.87490717995836,
                            15.16887594801018
                        ],
                        [
                            76.87505147818085,
                            15.16901521923981
                        ],
                        [
                            76.87523330490156,
                            15.169104636921876
                        ]
                    ]
                ]
            },
            "is_poi": true,
            "last_visited_on": "2020-05-22T15:11:23.883",
            "timezone_offset": "+0530",
            "confidence": "Medium",
            "dataset": {
                "start_time": "2020-04-14T05:20:39.176885",
                "end_time": "2020-05-26T05:20:39.176885",
                "is_weekend": true
            },
            "location_significance": {
                "is_home": false,
                "is_work": false,
                "number_of_visits": 1
            },
            "location_place": {
                "geometry": {
                    "type": "Point",
                    "coordinates": [
                        76.87543486155391,
                        15.168505923039925
                    ]
                },
                "type": "city",
                "name": "Ballari"
            },
            "created_at": "2020-05-26T05:20:47.887",
            "app_id": "5bf3f5d7dd938814bce3545e_1",
            "id": "5ecca735609ea47b89d3d8d8"
        },
        {
            "user_id": "5eb94798fc0bfe6584414ec0",
            "geometry": {
                "type": "Polygon",
                "coordinates": [
                    [
                        [
                            76.9243626,
                            15.153013025124148
                        ],
                        [
                            76.92456414128499,
                            15.152982213882057
                        ],
                        [
                            76.92474595414276,
                            15.15289279620025
                        ],
                        [
                            76.92489024136391,
                            15.152753524970944
                        ],
                        [
                            76.92498287910992,
                            15.15257803311464
                        ],
                        [
                            76.92501479945291,
                            15.152383499063466
                        ],
                        [
                            76.9249828779693,
                            15.152188965191154
                        ],
                        [
                            76.92489023951835,
                            15.15201347380312
                        ],
                        [
                            76.9247459522972,
                            15.151874203152623
                        ],
                        [
                            76.92456414014437,
                            15.151784785939087
                        ],
                        [
                            76.9243626,
                            15.15175397487586
                        ],
                        [
                            76.92416105985562,
                            15.151784785939087
                        ],
                        [
                            76.92397924770279,
                            15.151874203152623
                        ],
                        [
                            76.92383496048164,
                            15.15201347380312
                        ],
                        [
                            76.92374232203069,
                            15.152188965191154
                        ],
                        [
                            76.92371040054708,
                            15.152383499063466
                        ],
                        [
                            76.92374232089007,
                            15.15257803311464
                        ],
                        [
                            76.92383495863609,
                            15.152753524970944
                        ],
                        [
                            76.92397924585723,
                            15.15289279620025
                        ],
                        [
                            76.924161058715,
                            15.152982213882057
                        ]
                    ]
                ]
            },
            "is_poi": true,
            "last_visited_on": "2020-05-21T07:47:13.603",
            "timezone_offset": "+0530",
            "confidence": "Medium",
            "dataset": {
                "start_time": "2020-04-14T05:20:39.176885",
                "end_time": "2020-05-26T05:20:39.176885",
                "is_weekend": true
            },
            "location_significance": {
                "is_home": false,
                "is_work": false,
                "number_of_visits": 1
            },
            "location_place": {
                "geometry": {
                    "type": "Point",
                    "coordinates": [
                        76.9243626,
                        15.152383500000003
                    ]
                },
                "type": "city",
                "name": "Ballari"
            },
            "created_at": "2020-05-26T05:20:48.394",
            "app_id": "5bf3f5d7dd938814bce3545e_1",
            "id": "5ecca735609ea47b89d3d8d9"
        },
        {
            "user_id": "5eb94798fc0bfe6584414ec0",
            "geometry": {
                "type": "Polygon",
                "coordinates": [
                    [
                        [
                            76.8993015,
                            15.159676725124145
                        ],
                        [
                            76.89950304763441,
                            15.159645913882018
                        ],
                        [
                            76.89968486621999,
                            15.159556496200098
                        ],
                        [
                            76.8998291579866,
                            15.159417224970658
                        ],
                        [
                            76.89992179865082,
                            15.159241733114246
                        ],
                        [
                            76.89995371999913,
                            15.159047199063036
                        ],
                        [
                            76.89992179750963,
                            15.15885266519077
                        ],
                        [
                            76.89982915614014,
                            15.158677173802838
                        ],
                        [
                            76.89968486437351,
                            15.158537903152476
                        ],
                        [
                            76.89950304649324,
                            15.158448485939045
                        ],
                        [
                            76.8993015,
                            15.158417674875858
                        ],
                        [
                            76.89909995350679,
                            15.158448485939045
                        ],
                        [
                            76.8989181356265,
                            15.158537903152476
                        ],
                        [
                            76.89877384385987,
                            15.158677173802838
                        ],
                        [
                            76.89868120249038,
                            15.15885266519077
                        ],
                        [
                            76.8986492800009,
                            15.159047199063036
                        ],
                        [
                            76.8986812013492,
                            15.159241733114246
                        ],
                        [
                            76.89877384201341,
                            15.159417224970658
                        ],
                        [
                            76.89891813378003,
                            15.159556496200098
                        ],
                        [
                            76.89909995236562,
                            15.159645913882018
                        ]
                    ]
                ]
            },
            "is_poi": true,
            "last_visited_on": "2020-05-22T15:46:18.753",
            "timezone_offset": "+0530",
            "confidence": "Medium",
            "dataset": {
                "start_time": "2020-04-14T05:20:39.176885",
                "end_time": "2020-05-26T05:20:39.176885",
                "is_weekend": true
            },
            "location_significance": {
                "is_home": false,
                "is_work": false,
                "number_of_visits": 1
            },
            "location_place": {
                "geometry": {
                    "type": "Point",
                    "coordinates": [
                        76.8993015,
                        15.159047200000002
                    ]
                },
                "type": "road",
                "name": "Airport Road"
            },
            "created_at": "2020-05-26T05:20:48.888",
            "app_id": "5bf3f5d7dd938814bce3545e_1",
            "id": "5ecca735609ea47b89d3d8da"
        },
        {
            "user_id": "5eb94798fc0bfe6584414ec0",
            "geometry": {
                "type": "Polygon",
                "coordinates": [
                    [
                        [
                            76.90395209999998,
                            15.149470925124145
                        ],
                        [
                            76.90415363791122,
                            15.149440113882077
                        ],
                        [
                            76.90433544772551,
                            15.149350696200328
                        ],
                        [
                            76.90447973253143,
                            15.149211424971094
                        ],
                        [
                            76.90457236872685,
                            15.149035933114844
                        ],
                        [
                            76.90460428853564,
                            15.148841399063693
                        ],
                        [
                            76.90457236758652,
                            15.148646865191361
                        ],
                        [
                            76.90447973068635,
                            15.148471373803263
                        ],
                        [
                            76.90433544588043,
                            15.1483321031527
                        ],
                        [
                            76.90415363677089,
                            15.148242685939106
                        ],
                        [
                            76.90395209999998,
                            15.148211874875855
                        ],
                        [
                            76.9037505632291,
                            15.148242685939106
                        ],
                        [
                            76.90356875411955,
                            15.1483321031527
                        ],
                        [
                            76.90342446931363,
                            15.148471373803263
                        ],
                        [
                            76.90333183241346,
                            15.148646865191361
                        ],
                        [
                            76.90329991146433,
                            15.148841399063693
                        ],
                        [
                            76.90333183127314,
                            15.149035933114844
                        ],
                        [
                            76.90342446746855,
                            15.149211424971094
                        ],
                        [
                            76.90356875227447,
                            15.149350696200328
                        ],
                        [
                            76.90375056208876,
                            15.149440113882077
                        ]
                    ]
                ]
            },
            "is_poi": true,
            "last_visited_on": "2020-05-13T13:32:44.331",
            "timezone_offset": "+0530",
            "confidence": "Medium",
            "dataset": {
                "start_time": "2020-04-14T05:20:39.176885",
                "end_time": "2020-05-26T05:20:39.176885",
                "is_weekend": true
            },
            "location_significance": {
                "is_home": false,
                "is_work": false,
                "number_of_visits": 1
            },
            "location_place": {
                "geometry": {
                    "type": "Point",
                    "coordinates": [
                        76.9039521,
                        15.1488414
                    ]
                },
                "type": "city",
                "name": "Ballari"
            },
            "created_at": "2020-05-26T05:20:49.394",
            "app_id": "5bf3f5d7dd938814bce3545e_1",
            "id": "5ecca735609ea47b89d3d8db"
        },
        {
            "user_id": "5eb94798fc0bfe6584414ec0",
            "geometry": {
                "type": "Polygon",
                "coordinates": [
                    [
                        [
                            76.9066455,
                            15.15419202512414
                        ],
                        [
                            76.90684704240815,
                            15.154161213882045
                        ],
                        [
                            76.90702885627913,
                            15.154071796200217
                        ],
                        [
                            76.90717314430434,
                            15.153932524970886
                        ],
                        [
                            76.90726578256657,
                            15.153757033114562
                        ],
                        [
                            76.90729770308738,
                            15.153562499063382
                        ],
                        [
                            76.90726578142583,
                            15.15336796519108
                        ],
                        [
                            76.90717314245862,
                            15.153192473803061
                        ],
                        [
                            76.9070288544334,
                            15.153053203152592
                        ],
                        [
                            76.90684704126744,
                            15.15296378593907
                        ],
                        [
                            76.9066455,
                            15.152932974875851
                        ],
                        [
                            76.90644395873255,
                            15.15296378593907
                        ],
                        [
                            76.90626214556657,
                            15.153053203152592
                        ],
                        [
                            76.90611785754137,
                            15.153192473803061
                        ],
                        [
                            76.90602521857414,
                            15.15336796519108
                        ],
                        [
                            76.90599329691261,
                            15.153562499063382
                        ],
                        [
                            76.90602521743342,
                            15.153757033114562
                        ],
                        [
                            76.90611785569565,
                            15.153932524970886
                        ],
                        [
                            76.90626214372087,
                            15.154071796200217
                        ],
                        [
                            76.90644395759185,
                            15.154161213882045
                        ]
                    ]
                ]
            },
            "is_poi": true,
            "last_visited_on": "2020-05-22T13:20:08.068",
            "timezone_offset": "+0530",
            "confidence": "Medium",
            "dataset": {
                "start_time": "2020-04-14T05:20:39.176885",
                "end_time": "2020-05-26T05:20:39.176885",
                "is_weekend": true
            },
            "location_significance": {
                "is_home": false,
                "is_work": false,
                "number_of_visits": 1
            },
            "location_place": {
                "geometry": {
                    "type": "Point",
                    "coordinates": [
                        76.9066455,
                        15.153562499999996
                    ]
                },
                "type": "amenity",
                "name": "Vasavi School"
            },
            "created_at": "2020-05-26T05:20:49.891",
            "app_id": "5bf3f5d7dd938814bce3545e_1",
            "id": "5ecca735609ea47b89d3d8dc"
        },
        {
            "user_id": "5eb94798fc0bfe6584414ec0",
            "geometry": {
                "type": "Polygon",
                "coordinates": [
                    [
                        [
                            76.9165876,
                            15.157125725124141
                        ],
                        [
                            76.91678914520335,
                            15.157094913882025
                        ],
                        [
                            76.91697096159588,
                            15.157005496200153
                        ],
                        [
                            76.91711525162214,
                            15.156866224970763
                        ],
                        [
                            76.91720789116903,
                            15.156690733114392
                        ],
                        [
                            76.91723981213241,
                            15.156496199063193
                        ],
                        [
                            76.91720789002807,
                            15.15630166519091
                        ],
                        [
                            76.917115249776,
                            15.156126173802939
                        ],
                        [
                            76.91697095974975,
                            15.155986903152527
                        ],
                        [
                            76.91678914406239,
                            15.155897485939056
                        ],
                        [
                            76.9165876,
                            15.155866674875853
                        ],
                        [
                            76.91638605593762,
                            15.155897485939056
                        ],
                        [
                            76.91620424025025,
                            15.155986903152527
                        ],
                        [
                            76.916059950224,
                            15.156126173802939
                        ],
                        [
                            76.91596730997193,
                            15.15630166519091
                        ],
                        [
                            76.91593538786759,
                            15.156496199063193
                        ],
                        [
                            76.91596730883097,
                            15.156690733114392
                        ],
                        [
                            76.91605994837788,
                            15.156866224970763
                        ],
                        [
                            76.91620423840413,
                            15.157005496200153
                        ],
                        [
                            76.91638605479666,
                            15.157094913882025
                        ]
                    ]
                ]
            },
            "is_poi": true,
            "last_visited_on": "2020-05-16T15:06:10.350",
            "timezone_offset": "+0530",
            "confidence": "Medium",
            "dataset": {
                "start_time": "2020-04-14T05:20:39.176885",
                "end_time": "2020-05-26T05:20:39.176885",
                "is_weekend": true
            },
            "location_significance": {
                "is_home": false,
                "is_work": false,
                "number_of_visits": 1
            },
            "location_place": {
                "geometry": {
                    "type": "Point",
                    "coordinates": [
                        76.9165876,
                        15.1564962
                    ]
                },
                "type": "city",
                "name": "Ballari"
            },
            "created_at": "2020-05-26T05:20:50.386",
            "app_id": "5bf3f5d7dd938814bce3545e_1",
            "id": "5ecca735609ea47b89d3d8dd"
        },
        {
            "user_id": "5eb94798fc0bfe6584414ec0",
            "geometry": {
                "type": "Polygon",
                "coordinates": [
                    [
                        [
                            76.9126296818709,
                            15.15499671365647
                        ],
                        [
                            76.9128312250457,
                            15.154965902414364
                        ],
                        [
                            76.91301303960826,
                            15.154876484732526
                        ],
                        [
                            76.9131573281823,
                            15.154737213503182
                        ],
                        [
                            76.91324996679687,
                            15.154561721646841
                        ],
                        [
                            76.91328188743907,
                            15.15436718759566
                        ],
                        [
                            76.91324996565608,
                            15.154172653723359
                        ],
                        [
                            76.91315732633646,
                            15.153997162335353
                        ],
                        [
                            76.91301303776243,
                            15.153857891684902
                        ],
                        [
                            76.9128312239049,
                            15.153768474471395
                        ],
                        [
                            76.9126296818709,
                            15.153737663408178
                        ],
                        [
                            76.91242813983689,
                            15.153768474471395
                        ],
                        [
                            76.91224632597938,
                            15.153857891684902
                        ],
                        [
                            76.91210203740533,
                            15.153997162335353
                        ],
                        [
                            76.91200939808573,
                            15.154172653723359
                        ],
                        [
                            76.91197747630274,
                            15.15436718759566
                        ],
                        [
                            76.91200939694494,
                            15.154561721646841
                        ],
                        [
                            76.91210203555951,
                            15.154737213503182
                        ],
                        [
                            76.91224632413355,
                            15.154876484732526
                        ],
                        [
                            76.91242813869611,
                            15.154965902414364
                        ]
                    ]
                ]
            },
            "is_poi": true,
            "last_visited_on": "2020-05-17T15:13:27.469",
            "timezone_offset": "+0530",
            "confidence": "Medium",
            "dataset": {
                "start_time": "2020-04-14T05:20:39.176885",
                "end_time": "2020-05-26T05:20:39.176885",
                "is_weekend": true
            },
            "location_significance": {
                "is_home": false,
                "is_work": false,
                "number_of_visits": 2
            },
            "location_place": {
                "geometry": {
                    "type": "Point",
                    "coordinates": [
                        76.9126296818709,
                        15.154367188532326
                    ]
                },
                "type": "amenity",
                "name": "Ballari Fire Station"
            },
            "created_at": "2020-05-26T05:20:50.888",
            "app_id": "5bf3f5d7dd938814bce3545e_1",
            "id": "5ecca735609ea47b89d3d8de"
        },
        {
            "user_id": "5eb94798fc0bfe6584414ec0",
            "geometry": {
                "type": "Polygon",
                "coordinates": [
                    [
                        [
                            76.9148691,
                            15.156886225124147
                        ],
                        [
                            76.91507064497512,
                            15.156855413882033
                        ],
                        [
                            76.91525246116178,
                            15.156765996200164
                        ],
                        [
                            76.91539675102467,
                            15.156626724970781
                        ],
                        [
                            76.91548939046667,
                            15.156451233114414
                        ],
                        [
                            76.91552131139392,
                            15.156256699063213
                        ],
                        [
                            76.91548938932573,
                            15.156062165190926
                        ],
                        [
                            76.91539674917857,
                            15.155886673802952
                        ],
                        [
                            76.9152524593157,
                            15.155747403152533
                        ],
                        [
                            76.91507064383418,
                            15.15565798593906
                        ],
                        [
                            76.9148691,
                            15.155627174875855
                        ],
                        [
                            76.91466755616582,
                            15.15565798593906
                        ],
                        [
                            76.91448574068431,
                            15.155747403152533
                        ],
                        [
                            76.91434145082142,
                            15.155886673802952
                        ],
                        [
                            76.91424881067427,
                            15.156062165190926
                        ],
                        [
                            76.91421688860608,
                            15.156256699063213
                        ],
                        [
                            76.91424880953333,
                            15.156451233114414
                        ],
                        [
                            76.91434144897534,
                            15.156626724970781
                        ],
                        [
                            76.91448573883822,
                            15.156765996200164
                        ],
                        [
                            76.91466755502488,
                            15.156855413882033
                        ]
                    ]
                ]
            },
            "is_poi": true,
            "last_visited_on": "2020-05-16T02:20:46.178",
            "timezone_offset": "+0530",
            "confidence": "Medium",
            "dataset": {
                "start_time": "2020-04-14T05:20:39.176885",
                "end_time": "2020-05-26T05:20:39.176885",
                "is_weekend": true
            },
            "location_significance": {
                "is_home": false,
                "is_work": false,
                "number_of_visits": 1
            },
            "location_place": {
                "geometry": {
                    "type": "Point",
                    "coordinates": [
                        76.9148691,
                        15.1562567
                    ]
                },
                "type": "city",
                "name": "Ballari"
            },
            "created_at": "2020-05-26T05:20:51.388",
            "app_id": "5bf3f5d7dd938814bce3545e_1",
            "id": "5ecca735609ea47b89d3d8df"
        },
        {
            "user_id": "5eb94798fc0bfe6584414ec0",
            "geometry": {
                "type": "Polygon",
                "coordinates": [
                    [
                        [
                            76.9181009,
                            15.15845022512414
                        ],
                        [
                            76.9183024464655,
                            15.158419413882022
                        ],
                        [
                            76.91848426399663,
                            15.158329996200125
                        ],
                        [
                            76.91862855492647,
                            15.15819072497071
                        ],
                        [
                            76.91872119505345,
                            15.158015233114318
                        ],
                        [
                            76.91875311621669,
                            15.157820699063109
                        ],
                        [
                            76.91872119391236,
                            15.157626165190832
                        ],
                        [
                            76.91862855308015,
                            15.157450673802884
                        ],
                        [
                            76.91848426215033,
                            15.1573114031525
                        ],
                        [
                            76.91830244532441,
                            15.157221985939046
                        ],
                        [
                            76.9181009,
                            15.157191174875857
                        ],
                        [
                            76.91789935467557,
                            15.157221985939046
                        ],
                        [
                            76.91771753784965,
                            15.1573114031525
                        ],
                        [
                            76.91757324691983,
                            15.157450673802884
                        ],
                        [
                            76.91748060608762,
                            15.157626165190832
                        ],
                        [
                            76.91744868378332,
                            15.157820699063109
                        ],
                        [
                            76.91748060494655,
                            15.158015233114318
                        ],
                        [
                            76.91757324507353,
                            15.15819072497071
                        ],
                        [
                            76.91771753600337,
                            15.158329996200125
                        ],
                        [
                            76.9178993535345,
                            15.158419413882022
                        ]
                    ]
                ]
            },
            "is_poi": true,
            "last_visited_on": "2020-05-23T03:41:27.048",
            "timezone_offset": "+0530",
            "confidence": "Medium",
            "dataset": {
                "start_time": "2020-04-14T05:20:39.176885",
                "end_time": "2020-05-26T05:20:39.176885",
                "is_weekend": true
            },
            "location_significance": {
                "is_home": false,
                "is_work": false,
                "number_of_visits": 1
            },
            "location_place": {
                "geometry": {
                    "type": "Point",
                    "coordinates": [
                        76.9181009,
                        15.157820699999998
                    ]
                },
                "type": "city",
                "name": "Ballari"
            },
            "created_at": "2020-05-26T05:20:51.888",
            "app_id": "5bf3f5d7dd938814bce3545e_1",
            "id": "5ecca735609ea47b89d3d8e0"
        },
        {
            "user_id": "5eb94798fc0bfe6584414ec0",
            "geometry": {
                "type": "Polygon",
                "coordinates": [
                    [
                        [
                            76.88724563111576,
                            15.161604362927786
                        ],
                        [
                            76.88744718058746,
                            15.161573551685644
                        ],
                        [
                            76.88762900083047,
                            15.161484134003697
                        ],
                        [
                            76.8877732939124,
                            15.161344862774223
                        ],
                        [
                            76.88786593542103,
                            15.161169370917774
                        ],
                        [
                            76.88789785706024,
                            15.16097483686655
                        ],
                        [
                            76.8878659342797,
                            15.160780302994292
                        ],
                        [
                            76.88777329206567,
                            15.160604811606394
                        ],
                        [
                            76.88762899898374,
                            15.160465540956075
                        ],
                        [
                            76.88744717944611,
                            15.160376123742674
                        ],
                        [
                            76.88724563111576,
                            15.160345312679501
                        ],
                        [
                            76.88704408278541,
                            15.160376123742674
                        ],
                        [
                            76.88686226324778,
                            15.160465540956075
                        ],
                        [
                            76.88671797016585,
                            15.160604811606394
                        ],
                        [
                            76.88662532795182,
                            15.160780302994292
                        ],
                        [
                            76.88659340517127,
                            15.16097483686655
                        ],
                        [
                            76.88662532681047,
                            15.161169370917774
                        ],
                        [
                            76.88671796831912,
                            15.161344862774223
                        ],
                        [
                            76.88686226140105,
                            15.161484134003697
                        ],
                        [
                            76.88704408164405,
                            15.161573551685644
                        ]
                    ]
                ]
            },
            "is_poi": true,
            "last_visited_on": "2020-05-24T13:41:20.553",
            "timezone_offset": "+0530",
            "confidence": "Medium",
            "dataset": {
                "start_time": "2020-04-14T05:20:39.176885",
                "end_time": "2020-05-26T05:20:39.176885",
                "is_weekend": true
            },
            "location_significance": {
                "is_home": false,
                "is_work": false,
                "number_of_visits": 3
            },
            "location_place": {
                "geometry": {
                    "type": "Point",
                    "coordinates": [
                        76.88724563111576,
                        15.160974837803646
                    ]
                },
                "type": "amenity",
                "name": "Gowda Canteen"
            },
            "created_at": "2020-05-26T05:20:52.392",
            "app_id": "5bf3f5d7dd938814bce3545e_1",
            "id": "5ecca735609ea47b89d3d8e1"
        },
        {
            "user_id": "5eb94798fc0bfe6584414ec0",
            "geometry": {
                "type": "Polygon",
                "coordinates": [
                    [
                        [
                            76.87041059999999,
                            15.175085825124146
                        ],
                        [
                            76.8706121623287,
                            15.175055013881922
                        ],
                        [
                            76.87079399417003,
                            15.174965596199755
                        ],
                        [
                            76.87093829645613,
                            15.174826324970006
                        ],
                        [
                            76.87103094387389,
                            15.174650833113342
                        ],
                        [
                            76.87106286754879,
                            15.174456299062035
                        ],
                        [
                            76.8710309427314,
                            15.174261765189863
                        ],
                        [
                            76.87093829460757,
                            15.174086273802182
                        ],
                        [
                            76.87079399232145,
                            15.173947003152131
                        ],
                        [
                            76.87061216118622,
                            15.173857585938947
                        ],
                        [
                            76.87041059999999,
                            15.17382677487586
                        ],
                        [
                            76.87020903881377,
                            15.173857585938947
                        ],
                        [
                            76.87002720767853,
                            15.173947003152131
                        ],
                        [
                            76.86988290539242,
                            15.174086273802182
                        ],
                        [
                            76.86979025726859,
                            15.174261765189863
                        ],
                        [
                            76.86975833245121,
                            15.174456299062035
                        ],
                        [
                            76.86979025612611,
                            15.174650833113342
                        ],
                        [
                            76.86988290354385,
                            15.174826324970006
                        ],
                        [
                            76.87002720582996,
                            15.174965596199755
                        ],
                        [
                            76.87020903767129,
                            15.175055013881922
                        ]
                    ]
                ]
            },
            "is_poi": true,
            "last_visited_on": "2020-05-16T11:55:35.439",
            "timezone_offset": "+0530",
            "confidence": "Medium",
            "dataset": {
                "start_time": "2020-04-14T05:20:39.176885",
                "end_time": "2020-05-26T05:20:39.176885",
                "is_weekend": true
            },
            "location_significance": {
                "is_home": false,
                "is_work": false,
                "number_of_visits": 1
            },
            "location_place": {
                "geometry": {
                    "type": "Point",
                    "coordinates": [
                        76.8704106,
                        15.174456300000003
                    ]
                },
                "type": "village",
                "name": "Allipura"
            },
            "created_at": "2020-05-26T05:20:52.905",
            "app_id": "5bf3f5d7dd938814bce3545e_1",
            "id": "5ecca735609ea47b89d3d8e2"
        },
        {
            "user_id": "5eb94798fc0bfe6584414ec0",
            "geometry": {
                "type": "Polygon",
                "coordinates": [
                    [
                        [
                            76.9139,
                            15.15642792512414
                        ],
                        [
                            76.91410154453844,
                            15.156397113882027
                        ],
                        [
                            76.91428336033114,
                            15.156307696200166
                        ],
                        [
                            76.9144276498814,
                            15.156168424970792
                        ],
                        [
                            76.9145202891227,
                            15.155992933114431
                        ],
                        [
                            76.91455220998081,
                            15.155798399063235
                        ],
                        [
                            76.91452028798179,
                            15.15560386519095
                        ],
                        [
                            76.91442764803539,
                            15.155428373802964
                        ],
                        [
                            76.91428335848512,
                            15.15528910315254
                        ],
                        [
                            76.91410154339754,
                            15.155199685939055
                        ],
                        [
                            76.9139,
                            15.155168874875848
                        ],
                        [
                            76.91369845660246,
                            15.155199685939055
                        ],
                        [
                            76.91351664151489,
                            15.15528910315254
                        ],
                        [
                            76.91337235196463,
                            15.155428373802964
                        ],
                        [
                            76.91327971201821,
                            15.15560386519095
                        ],
                        [
                            76.91324779001918,
                            15.155798399063235
                        ],
                        [
                            76.91327971087729,
                            15.155992933114431
                        ],
                        [
                            76.91337235011859,
                            15.156168424970792
                        ],
                        [
                            76.91351663966886,
                            15.156307696200166
                        ],
                        [
                            76.91369845546157,
                            15.156397113882027
                        ]
                    ]
                ]
            },
            "is_poi": true,
            "last_visited_on": "2020-05-23T13:05:12.130",
            "timezone_offset": "+0530",
            "confidence": "Medium",
            "dataset": {
                "start_time": "2020-04-14T05:20:39.176885",
                "end_time": "2020-05-26T05:20:39.176885",
                "is_weekend": true
            },
            "location_significance": {
                "is_home": false,
                "is_work": false,
                "number_of_visits": 1
            },
            "location_place": {
                "geometry": {
                    "type": "Point",
                    "coordinates": [
                        76.9139,
                        15.155798399999997
                    ]
                },
                "type": "city",
                "name": "Ballari"
            },
            "created_at": "2020-05-26T05:20:53.388",
            "app_id": "5bf3f5d7dd938814bce3545e_1",
            "id": "5ecca735609ea47b89d3d8e3"
        }
    ]
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
curl --location --request POST 'https://api.geospark.co/v1/api/insights/' \
--header 'Content-Type: application/json' \
--header 'Api-key: eff6e09bd77b43df901d5226f0f1f35b' \
--header 'Content-Type: text/plain' \
--data-raw '{
	"user_id": "5eb94798fc0bfe6584414ec0"
}'
```
{% endtab %}

{% tab title="JavaScript" %}
```
var settings = {
  "url": "https://api.geospark.co/v1/api/insights/",
  "method": "POST",
  "timeout": 0,
  "headers": {
    "Content-Type": ["application/json", "text/plain"],
    "Api-key": "eff6e09bd77b43df901d5226f0f1f35b"
  },
  "data": "{\n\t\"user_id\": \"5eb94798fc0bfe6584414ec0\"\n}",
};

$.ajax(settings).done(function (response) {
  console.log(response);
});
```
{% endtab %}

{% tab title="Java" %}
```
OkHttpClient client = new OkHttpClient().newBuilder()
  .build();
MediaType mediaType = MediaType.parse("application/json,text/plain");
RequestBody body = RequestBody.create(mediaType, "{\n\t\"user_id\": \"5eb94798fc0bfe6584414ec0\"\n}");
Request request = new Request.Builder()
  .url("https://api.geospark.co/v1/api/insights/")
  .method("POST", body)
  .addHeader("Content-Type", "application/json")
  .addHeader("Api-key", "eff6e09bd77b43df901d5226f0f1f35b")
  .addHeader("Content-Type", "text/plain")
  .build();
Response response = client.newCall(request).execute();
```
{% endtab %}

{% tab title="python" %}
```
import requests

url = "https://api.geospark.co/v1/api/insights/"

payload = "{\n\t\"user_id\": \"5eb94798fc0bfe6584414ec0\"\n}"
headers = {
  'Content-Type': 'application/json',
  'Api-key': 'eff6e09bd77b43df901d5226f0f1f35b',
  'Content-Type': 'text/plain'
}

response = requests.request("POST", url, headers=headers, data = payload)

print(response.text.encode('utf8'))

```
{% endtab %}

{% tab title="Swift" %}
```
import Foundation

var semaphore = DispatchSemaphore (value: 0)

let parameters = "{\n\t\"user_id\": \"5eb94798fc0bfe6584414ec0\"\n}"
let postData = parameters.data(using: .utf8)

var request = URLRequest(url: URL(string: "https://api.geospark.co/v1/api/insights/")!,timeoutInterval: Double.infinity)
request.addValue("application/json", forHTTPHeaderField: "Content-Type")
request.addValue("eff6e09bd77b43df901d5226f0f1f35b", forHTTPHeaderField: "Api-key")
request.addValue("text/plain", forHTTPHeaderField: "Content-Type")

request.httpMethod = "POST"
request.httpBody = postData

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

{% tab title="Go" %}
```
package main

import (
  "fmt"
  "strings"
  "net/http"
  "io/ioutil"
)

func main() {

  url := "https://api.geospark.co/v1/api/insights/"
  method := "POST"

  payload := strings.NewReader("{\n	\"user_id\": \"5eb94798fc0bfe6584414ec0\"\n}")

  client := &http.Client {
  }
  req, err := http.NewRequest(method, url, payload)

  if err != nil {
    fmt.Println(err)
  }
  req.Header.Add("Content-Type", "application/json")
  req.Header.Add("Api-key", "eff6e09bd77b43df901d5226f0f1f35b")
  req.Header.Add("Content-Type", "text/plain")

  res, err := client.Do(req)
  defer res.Body.Close()
  body, err := ioutil.ReadAll(res.Body)

  fmt.Println(string(body))
}
```
{% endtab %}
{% endtabs %}

