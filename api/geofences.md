---
description: >-
  This set of APIs lets you create, get, update, and delete geofences, specific
  to the project and helps you to keep track of them.
---

# Geofences

{% hint style="info" %}
An optional set of custom key-value pairs for the geofence.By default, GeoFences are not **"event trigger"** enabled. To make a geofence **"event trigger"** enabled, update that particular geofence using **Update API** and pass the below option.
{% endhint %}

{% code title="JSON" %}
```javascript
{"is_enabled": true}
```
{% endcode %}

{% api-method method="post" host="   https://api.geospark.co/v1" path="/api/geofence/" %}
{% api-method-summary %}
Create Geofence API
{% endapi-method-summary %}

{% api-method-description %}
Create Geofence API is responsible for creating geofences for projects.   
  
**Note :** All Latitude and Longitude Coordinates mentioned, use EPSG 4236 WGS 84 \(Web Mercator Projection\) as Coordinate Reference System. GPS from both Android and iOS devices return in the same format. No other CRS is supported.  
Geometry radius is in meters.
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
{% api-method-parameter name="metadata" type="array" required=false %}
An optional set of custom key-value pairs for the geofence.
{% endapi-method-parameter %}

{% api-method-parameter name="coordinates" type="array" required=true %}
Mandatory for creating the geofence.  
  
**Input Data:** Circle \[longitude, latitude\], OR Polygon\[\[longitude, latitude\], \[longitude, latitude\],...\]
{% endapi-method-parameter %}

{% api-method-parameter name="geometry\_type" type="string" required=true %}
Defines the type of geometry.  
  
**Input Data:** circle or polygon
{% endapi-method-parameter %}

{% api-method-parameter name="geometry\_radius" type="integer" required=true %}
Defines the radius of circular geofence in meters. Range 50m to 1000m.  
\(Required only for type circle. Field value ignored if sent when geometry\_type is polygon.\)  
  
**Input Data:** 50m to 1000m max
{% endapi-method-parameter %}

{% api-method-parameter name="color\_code" type="string" required=false %}
Defines the color of Geofence and how it is displayed in the dashboard. Type : Hex Code for CSS colors.   
**Note :** Pass the code without '\#'.  
  
**Input Data:**  ffffff
{% endapi-method-parameter %}

{% api-method-parameter name="tag" type="string" required=false %}
Tag the GeoFences for future reference and filtering.  
  
**Input Data:** hotel
{% endapi-method-parameter %}

{% api-method-parameter name="description" type="string" required=false %}
Optional description for the geofence.  
  
**Input Data:**  This is just a 5 star cool hotel where you can stay.
{% endapi-method-parameter %}

{% api-method-parameter name="is\_enabled" type="boolean" required=false %}
Enable/Disable 'event\_trigger' for Geofences. By default event trigger are disabled.  
  
**Input Data:** true or false
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=201 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

{% code title="JSON" %}
```javascript
{
    "status": true,
    "msg": "Geofence Added successfully.",
    "code": 201,
    "data": {
        "id": "5bd5bc35eec1a504f3d87382",
        "account_id": "5bbdd7a8eec1a511b246490d",
        "project_id": "5bbdd865eec1a511b246490e",
        "geometry_type": "circle",
        "geometry_radius": 50,
        "geometry_center": {
            "type": "Point",
            "coordinates": [
                -72.28122,
                42.926042
            ]
        },
        "is_enabled": false,
        "color_code": "00BFFF",
        "tag": "Hotel",
        "created_at": "2018-10-28T13:40:05.097",
        "updated_at": "2018-10-28T13:40:05.097",
        "metadata": {
                    "name": "Coffee Shop",
                    "external_id": 123
                }

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
curl -X POST \
    https://api.geospark.co/v1/api/geofence/ \
    -H 'Api-Key: 2fd72b3b94b149018957eae89c2d1c86' \
    -H 'Content-Type: application/json' \
    -d '{
    "geometry_type": "circle",
    "coordinates": [-72.28122, 42.926042] ,
    "geometry_radius": 50,
    "color_code": "00BFFF",
    "tag": "Hotel",
    "metadata": {"name": "Coffee Shop","external_id": 123}
}'
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
var settings = {
    "async": true,
    "crossDomain": true,
    "url": "https://api.geospark.co/v1/api/geofence/",
    "method": "POST",
    "headers": {
      "Api-Key": "2fd72b3b94b149018957eae89c2d1c86",
      "Content-Type": "application/json"
    },
    "processData": false,
    "data": "{\n\t\"geometry_type\": \"circle\",\n\t\"coordinates\":
    [-72.28122, 42.926042] ,\n\t\"geometry_radius\": 50\n,\n\t\"color_code\":
    \"00BFFF\",\n\t\"tag\": \"Hotel\"\n}"
}

$.ajax(settings).done(function (response) {
    console.log(response);
});
```
{% endtab %}

{% tab title="Python" %}
```python
import requests

url = "https://api.geospark.co/v1/api/geofence/"

payload = {"geometry_type": "circle","coordinates": [ -72.28122, 42.926042 ] ,"geometry_radius": 50, "color_code": "00BFFF","tag": "Hotel"}

headers = {'Api-Key': "2fd72b3b94b149018957eae89c2d1c86"}

response = requests.request("POST", url, json=payload, headers=headers)

print(response.text)
```
{% endtab %}

{% tab title="Java" %}
```java
OkHttpClient client = new OkHttpClient();

MediaType mediaType = MediaType.parse("application/json");
RequestBody body = RequestBody.create(mediaType, "{\n\t\"geometry_type\": \"circle\",\n\t\"coordinates\": [-72.28122, 42.926042] ,\n\t\"geometry_radius\": 50\n,\n\t\"color_code\": \"00BFFF\",\n\t\"tag\":
 \"Hotel\"\n}"}");
Request request = new Request.Builder()
    .url("https://api.geospark.co/v1/api/geofence/")
    .post(body)
    .addHeader("Api-Key", "2fd72b3b94b149018957eae89c2d1c86")
    .addHeader("Content-Type", "application/json")
    .build();

Response response = client.newCall(request).execute();
```
{% endtab %}

{% tab title="Swift" %}
```swift
import Foundation

let headers = [
    "Api-Key": "2fd72b3b94b149018957eae89c2d1c86",
    "Content-Type": "application/json"
]
let parameters = [
    "geometry_type": "circle",
    "coordinates": [-72.28122, 42.926042],
    "geometry_radius": 50,
    "color_code": "00BFFF",
    "tag": "Hotel"
] as [String : Any]

let postData = JSONSerialization.data(withJSONObject: parameters, options: [])

let request = NSMutableURLRequest(url: NSURL(string: "https://api.geospark.co/v1/api/geofence/")! as URL,
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

   url := "https://api.geospark.co/v1/api/geofence/"

   payload := strings.NewReader("{\n\t\"geometry_type\": \"circle\",\n\t\"coordinates\": [-72.28122, 42.926042] ,\n\t\"geometry_radius\": 50\n, \n\t\"color_code\": \"00BFFF\",\n\t\"tag\":\"Hotel\"\n}")

   req, _ := http.NewRequest("POST", url, payload)

   req.Header.Add("Api-Key", "2fd72b3b94b149018957eae89c2d1c86")
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

{% api-method method="put" host="   https://api.geospark.co/v1" path="/api/geofence/" %}
{% api-method-summary %}
Update Geofence API
{% endapi-method-summary %}

{% api-method-description %}
Update details for existing geofence of any specific project using Update Geofence API.
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
{% api-method-parameter name="metadata" type="array" required=false %}
An optional set of custom key-value pairs for the geofence.
{% endapi-method-parameter %}

{% api-method-parameter name="geofence\_id" type="string" required=true %}
Identifies the Geofence.  
  
**Input Data:** 5bd2aee1eec1a50d8faf1293
{% endapi-method-parameter %}

{% api-method-parameter name="color\_code" type="string" required=false %}
Defines the color of Geofence and how it is displayed in the dashboard. Type : Hex Code for CSS colors.   
**Note :** Pass the code without '\#'.  
  
**Input Data:** ffffff
{% endapi-method-parameter %}

{% api-method-parameter name="tag" type="string" required=false %}
This is to tag your geofence for your structural property.  
  
**Input Data:** hotel
{% endapi-method-parameter %}

{% api-method-parameter name="description" type="string" required=false %}
Optional description for the geofence.  
  
**Input Data:**  This is just a 5 star cool hotel where you can stay.
{% endapi-method-parameter %}

{% api-method-parameter name="is\_enabled" type="boolean" required=false %}
Enable/Disable 'event\_trigger' for Geofences. By Default event trigger are disabled.  
  
**Input Data:** true or false
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
      "msg": "Geofence updated successfully.",
      "code": 200,
      "data": {
          "id": "5bd2aee1eec1a50d8faf1293",
          "geometry": {
              "type": "Polygon",
              "coordinates": [
                  [
                      [
                          -72.28122,
                          42.926042
                      ],
                      [
                          -72.2823209,
                          42.9250442
                      ],
                      [
                          -72.2804648,
                          42.9243686
                      ],
                      [
                          -72.2795207,
                          42.9254685
                      ],
                      [
                          -72.2800592,
                          42.9261249
                      ],
                      [
                          -72.28122,
                          42.926042
                      ]
                  ]
              ]
          },
          "account_id": "5bbdd7a8eec1a511b246490d",
          "project_id": "5bbdd865eec1a511b246490e",
          "geometry_type": "polygon",
          "geometry_center": {
              "type": "Point",
              "coordinates": [
                  -72.28080043090077,
                  42.92531143047176
              ]
          },
          "is_enabled": true,
          "description": "Private Resort area",
          "color_code": "ffff",
          "tag": "Hotel",
          "metadata": {
                    "name": "Coffee Shop",
                    "external_id": 123
                },
          "created_at": "2018-10-26T06:06:25.122",
          "updated_at": "2018-10-28T14:00:41.198"
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
  curl -X PUT \
    https://api.geospark.co/v1/api/geofence/ \
    -H 'Api-Key: 2fd72b3b94b149018957eae89c2d1c86' \
    -H 'Content-Type: application/json' \
    -d '{
    "geofence_id": "5bd2aee1eec1a50d8faf1293",
    "is_enabled": true,
    "description": "Private Resort area",
    "tag": "Hotel",
    "color_code": "ffff",
    "metadata": {"name": "Coffee Shop","external_id": 123}
  }'
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
  var settings = {
    "async": true,
    "crossDomain": true,
    "url": "https://api.geospark.co/v1/api/geofence/",
    "method": "PUT",
    "headers": {
      "Api-Key": "2fd72b3b94b149018957eae89c2d1c86",
      "Content-Type": "application/json"
    },
    "processData": false,
    "data": "{\n\t\"geofence_id\": \"5bd2aee1eec1a50d8faf1293\",\n\t\"is_enabled\": true,\n\t\"description\": \"Private Resort area\",\n\t\"tag\": \"Hotel\",\n\t\"color_code\": \"ffff\"\n}"
  }

  $.ajax(settings).done(function (response) {
    console.log(response);
  });
```
{% endtab %}

{% tab title="Python" %}
```python
  import requests

  url = "https://api.geospark.co/v1/api/geofence/"

  payload =  {"geofence_id": "5bd2aee1eec1a50d8faf1293","is_enabled":
  True,"description": "Private Resort area","tag": "Hotel","color_code":
  "ffff"}
  headers = {'Api-Key': "2fd72b3b94b149018957eae89c2d1c86"}

  response = requests.request("PUT", url, data=payload, headers=headers)

  print(response.text)
```
{% endtab %}

{% tab title="Java" %}
```java
  OkHttpClient client = new OkHttpClient();

  MediaType mediaType = MediaType.parse("application/json");
  RequestBody body = RequestBody.create(mediaType, "{\n\t\"geofence_id\": \"5bd2aee1eec1a50d8faf1293\",\n\t\"is_enabled\": true,\n\t\"description\": \"Private Resort area\",\n\t\"tag\": \"Hotel\",\n\t\"color_code\": \"ffff\"\n}");
  Request request = new Request.Builder()
    .url("https://api.geospark.co/v1/api/geofence/")
    .put(body)
    .addHeader("Api-Key", "2fd72b3b94b149018957eae89c2d1c86")
    .addHeader("Content-Type", "application/json")
    .build();

  Response response = client.newCall(request).execute();
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

    url := "https://api.geospark.co/v1/api/geofence/"

    payload := strings.NewReader("{\n\t\"geofence_id\": \"5bd2aee1eec1a50d8faf1293\",\n\t\"is_enabled\": true,\n\t\"description\": \""Private Resort area\",\n\t\"tag\": \"Hotel\",\n\t\"color_code\": \"ffff\"\n}")

    req, _ := http.NewRequest("PUT", url, payload)

    req.Header.Add("Api-Key", "2fd72b3b94b149018957eae89c2d1c86")
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

{% api-method method="get" host="  https://api.geospark.co/v1" path="/api/geofence/" %}
{% api-method-summary %}
Get Geofence API
{% endapi-method-summary %}

{% api-method-description %}
This API gives you the filtered list of geofences.
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
This field can be user for defining the start date form which the list of geofences to be shown.  
 **Input Date**: 2018-10-19
{% endapi-method-parameter %}

{% api-method-parameter name="end\_date" type="string" required=false %}
This field can be used to define a range of time till when the last document needs to be provided. 'end\_date' should always be greater than 'start\_date'. If end\_date is provided then start\_date should also be provided.If only start\_date is passed, the geofence list for same day will be returned.   
**Input Date**: 2018-10-20
{% endapi-method-parameter %}

{% api-method-parameter name="page\_number" type="integer" required=false %}
Returns the data in the page provided. A page will have a maximum of 10 entries. If the response returns an empty list in data field, it is safe to assume the pages are exhausted.
{% endapi-method-parameter %}

{% api-method-parameter name="color\_code" type="string" required=false %}
Defines the color of Geofence and how it is displayed in the dashboard.   
Type : Hex Code for CSS colors.   
**Note :** Pass the code without '\#'.  
  
**Input Data:** ffffff
{% endapi-method-parameter %}

{% api-method-parameter name="tag" type="string" required=false %}
Tag the GeoFences for future reference and filtering.  
  
**Input Data:** hotel
{% endapi-method-parameter %}

{% api-method-parameter name="geometry\_type" type="string" required=false %}
Type of the Geofence. Can be either a Circle or Polygon.  
  
**Input Data:**  circle or polygon
{% endapi-method-parameter %}

{% api-method-parameter name="geofence\_id" type="string" required=false %}
To get the data only for a single geofence, pass it's geofence\_id.  
  
**Input Data:**  5bd2aee1eec1a50d8faf1293
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
        "account_id": "5bbdd7a8eec1a511b246490d",
        "project_id": "5bbdd865eec1a511b246490e",
        "geofences": [
            {
              "id": "5bc89a4feec1a50e738db301",
              "geometry": {
                  "type": "Polygon",
                  "coordinates": [
                      [
                          [
                          -0.107524,
                          51.505716
                          ],
                          [
                          -0.100071,
                          51.492607
                          ],
                          [
                          -0.149201,
                          51.490107
                          ],
                          [
                          -0.107524,
                          51.505716
                          ]
                      ]
                  ]
            },
            "geometry_type": "polygon",
            "geometry_center": {
                "type": "Point",
                "coordinates": [
                    -0.11893199999993373,
                    51.49614333333265
                ]
            },
            "is_enabled": true,
            "description": "Hotel Area",
            "tag": "Hotel",
            "metadata": {
                    "name": "Coffee Shop",
                    "external_id": 123
                },
            "created_at": "2018-10-18T14:35:59.810",
            "updated_at": "2018-10-18T14:35:59.810"
          },
          {
            "id": "5bc89a75eec1a50e738db302",
            "geometry": {
            "type": "Polygon",
            "coordinates": [
                [
                    [
                    -0.107524,
                    51.505716
                    ],
                    [
                    -0.100071,
                    51.492607
                    ],
                    [
                    -0.149201,
                    51.490107
                    ],
                    [
                    -0.107524,
                    51.505716
                    ]
                ]
            ]
        },
        "geometry_type": "polygon",
        "geometry_center": {
            "type": "Point",
            "coordinates": [
                -0.11893199999993373,
                51.49614333333265
            ]
       },
          "is_enabled": true,
          "tag": "Office",
          "metadata": {
                    "name": "Office Sarjapur",
                    "external_id": 128
                }
          "created_at": "2018-10-18T14:36:37.747",
          "updated_at": "2018-10-18T14:36:37.747"
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
    'https://api.geospark.co/v1/api/geofence/?geometry_type=polygon&color_code=ffff&tag=border%20code&page_number=1' \
    -H 'Api-Key: 2fd72b3b94b149018957eae89c2d1c86'
```
{% endtab %}

{% tab title="JavaScript" %}
```javascript
 var settings = {
    "async": true,
    "crossDomain": true,
    "url": "https://api.geospark.co/v1/api/geofence/?geometry_type=polygon&color_code=ffff&tag=border%20code&page_number=1",
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

  url = "https://api.geospark.co/v1/api/geofence/"

  querystring = {"geometry_type":"polygon","color_code":"ffff","tag":"border%20code","page_number":"1"}

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
    .url("https://api.geospark.co/v1/api/geofence/?geometry_type=polygon&color_code=ffff&tag=border%20code&page_number=1")
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

  let request = NSMutableURLRequest(url: NSURL(string: "https://api.geospark.co/v1/api/geofence/?geometry_type=polygon&color_code=ffff&tag=border%20code&page_number=1")! as URL,
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

    url := "https://api.geospark.co/v1/api/geofence/?geometry_type=polygon&color_code=ffff&tag=border%20code&page_number=1"

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

{% api-method method="delete" host=" https://api.geospark.co/v1" path="/api/geofence/" %}
{% api-method-summary %}
Delete Geofence API
{% endapi-method-summary %}

{% api-method-description %}
Delete Geofence API allows you to delete already existing geofences for a project.
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

{% api-method-body-parameters %}
{% api-method-parameter name="geofence\_id" type="string" required=true %}
Deletes the geofence given here.  
  
**Input Data:**  5bb3177a02a89b3c7a6a8d4f
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
      "msg": "Geofence deleted successfully.",
      "code": 200,
      "data": {}
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
  curl -X DELETE \
    https://api.geospark.co/v1/api/geofence/ \
    -H 'Api-Key: 2fd72b3b94b149018957eae89c2d1c86' \
    -H 'Content-Type: application/json'
    -d '{
    "geofence_id": "5bd2aee1eec1a50d8faf1293"
  }'
```
{% endtab %}

{% tab title="" %}
```javascript
  var settings = {
    "async": true,
    "crossDomain": true,
    "url": "https://api.geospark.co/v1/api/geofence/",
    "method": "DELETE",
    "headers": {
      "Api-Key": "2fd72b3b94b149018957eae89c2d1c86",
      "Content-Type": "application/json"
    },
    "processData": false,
    "data": "{\n\t\"geofence_id\": \"5bd2aee1eec1a50d8faf1293\"\n}"
  }

  $.ajax(settings).done(function (response) {
    console.log(response);
  });
```
{% endtab %}

{% tab title="Python" %}
```python
  import requests

  url = "https://api.geospark.co/v1/api/geofence/"

  payload = "{\n\t\"geofence_id\": \"5bd2aee1eec1a50d8faf1293\"\n}"
  headers = {
      'Api-Key': "2fd72b3b94b149018957eae89c2d1c86",
      'Content-Type': "application/json"
      }

  response = requests.request("DELETE", url, data=payload, headers=headers)

  print(response.text)
```
{% endtab %}

{% tab title="Java" %}
```java
  OkHttpClient client = new OkHttpClient();

  MediaType mediaType = MediaType.parse("application/json");
  RequestBody body = RequestBody.create(mediaType, "{\n\t\"geofence_id\": \"5bd2aee1eec1a50d8faf1293\"\n}");
  Request request = new Request.Builder()
    .url("https://api.geospark.co/v1/api/geofence/")
    .delete(body)
    .addHeader("Api-Key", "2fd72b3b94b149018957eae89c2d1c86")
    .addHeader("Content-Type", "application/json")
    .build();

  Response response = client.newCall(request).execute();
```
{% endtab %}

{% tab title="Swift" %}
```swift
  import Foundation

  let headers = [
    "Api-Key": "2fd72b3b94b149018957eae89c2d1c86",
    "Content-Type": "application/json"
  ]
  let parameters = ["geofence_id": "5bd2aee1eec1a50d8faf1293"] as [String : Any]

  let postData = JSONSerialization.data(withJSONObject: parameters, options: [])

  let request = NSMutableURLRequest(url: NSURL(string: "https://api.geospark.co/v1/api/geofence/")! as URL,
                                          cachePolicy: .useProtocolCachePolicy,
                                      timeoutInterval: 10.0)
  request.httpMethod = "DELETE"
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

    url := "https://api.geospark.co/v1/api/geofence/"

    payload := strings.NewReader("{\n\t\"geofence_id\": \"5bd2aee1eec1a50d8faf1293\"\n}")

    req, _ := http.NewRequest("DELETE", url, payload)

    req.Header.Add("Api-Key", "2fd72b3b94b149018957eae89c2d1c86")
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

