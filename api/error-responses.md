# Error Responses

{% hint style="warning" %}
Valid keys will become invalid if it's associated Project or Account is deleted, and error will be thrown when those keys are used again.
{% endhint %}

## Get User API

**Code:** 400

**Description:**  Occurs when an unknown error is caught. Given to ensure graceful fails.

{% code title="JSON" %}
```javascript
  {
    "status": false,
    "msg": "Unknown Error.",
    "code": 400,
    "error": {
        "ErrorCode": "GS400",
        "ErrorMessage": "An error occured"
    }
  }
```
{% endcode %}

**Code:** 401

**Description:**  Occurs when an invalid API key of any form is passed. **Note :** API key of any inactive/deleted project or account is considered as Invalid.

{% code title="JSON" %}
```javascript
  {
    "status": true,
    "msg": "Invalid Api key.",
    "code": 401,
    "error": {
        "ErrorCode": "GS401",
        "ErrorMessage": "Invalid Api key",
        "details": "Invalid Api key."
    }
  }
```
{% endcode %}

**Code:** 401

**Description:**  Occurs when API key is not provided in the request.

{% code title="JSON" %}
```javascript
  {
      "status": true,
      "msg": "No Api key in Header provided",
      "code": 401,
      "error": {
          "ErrorCode": "GS401",
          "ErrorMessage": "Invalid Api key",
          "details": "No Api key in Header provided"
      }
  }
```
{% endcode %}

## Get Location API

**Code:** 400

**Description:**  Occurs when an unknown error is caught. Given to ensure graceful fails.

{% code title="JSON" %}
```javascript
  {
    "status": false,
    "msg": "Unknown Error.",
    "code": 400,
    "error": {
        "ErrorCode": "GS400",
        "ErrorMessage": "An error occured"
    }
  }
```
{% endcode %}

**Code:** 400

**Description:**  Occurs when the user\_id provided is invalid.

{% code title="JSON" %}
```javascript
  {
    "status": false,
    "msg": "Error Occured.",
    "code": 400,
    "error": {
        "ErrorCode": "GS402",
        "ErrorMessage": "Invalid request",
        "details": {
            "user_id": {
                "user_id": "This field is invalid"
            }
        }
    }
  }
```
{% endcode %}

**Code:** 400

**Description:**  Occurs when user\_id is not passed in the request header.

{% code title="JSON" %}
```javascript
  {
    "status": false,
    "msg": "Error Occured.",
    "code": 400,
    "error": {
        "ErrorCode": "GS402",
        "ErrorMessage": "Invalid request",
        "details": {
            "user_id": [
                "This field is required."
            ]
        }
    }
  }
```
{% endcode %}

**Code:** 401

**Description:**  Occurs when API key is not provided in the request header.

{% code title="JSON" %}
```javascript
  {
    "status": true,
    "msg": "No Api key in Header provided",
    "code": 401,
    "error": {
        "ErrorCode": "GS401",
        "ErrorMessage": "Invalid Api key",
        "details": "No Api key in Header provided"
    }
  }
```
{% endcode %}

**Code:** 401

**Description:**  Occurs when an invalid API key of any form is passed.

{% code title="JSON" %}
```javascript
  {
    "status": true,
    "msg": "Invalid Api key.",
    "code": 401,
    "error": {
        "ErrorCode": "GS401",
        "ErrorMessage": "Invalid Api key",
        "details": "Invalid Api key."
    }
  }
```
{% endcode %}

## Create Geofence API

**Code:** 400

**Description:**  Occurs when an unknown error is caught. Given to ensure graceful fails.

{% code title="JSON" %}
```javascript
  {
    "status": false,
    "msg": "Unknown Error.",
    "code": 400,
    "error": {
        "ErrorCode": "GS400",
        "ErrorMessage": "An error occured"
    }
  }
```
{% endcode %}

**Code:** 400

**Description:**  Occurs when unsupported/invalid Geometry type is passed, or when given coordinates are invalid.  **NOTE:** Invalid coordinates include wrong formatting and wrong data type. It is advised not to pass Latitude/Longitude data when they are out of their respective ranges. Unknown error occurs in that case.

{% code title="JSON" %}
```javascript
  // when there is required geometry type mismatch 
  {
      "status": false,
      "msg": "Error Occured.",
      "code": 400,
      "error": {
          "ErrorCode": "GS402",
          "ErrorMessage": "Invalid request",
          "details": {
              "geometry_type": [
                  "\"circles\" is not a valid choice."
              ]
          }
      }
  }

  // invalid coordiantes
  {
      "status": false,
      "msg": "Error Occured.",
      "code": 400,
      "error": {
          "ErrorCode": "GS402",
          "ErrorMessage": "Invalid request",
          "details": {
              "coordinates": [
                  "Invalid coordinates for given geometry type"
              ]
          }
      }
  }
```
{% endcode %}

**Code:** 400

**Description:**  Occurs when mandatory fields, geometry\_type and coordinate parameters are not passed.

{% code title="JSON" %}
```javascript
  {
    "status": false,
    "msg": "Error Occured.",
    "code": 400,
    "error": {
        "ErrorCode": "GS402",
        "ErrorMessage": "Invalid request",
        "details": {
            "geometry_type": [
                "This field is required."
            ],
            "coordinates": [
                "This field is required."
            ]
        }
    }
  }
```
{% endcode %}

**Code:** 401

**Description:**  Occurs when API key is not provided in the request header.

{% code title="JSON" %}
```javascript
  {
    "status": true,
    "msg": "No Api key in Header provided",
    "code": 401,
    "error": {
        "ErrorCode": "GS401",
        "ErrorMessage": "Invalid Api key",
        "details": "No Api key in Header provided"
    }
  }
```
{% endcode %}

**Code:** 401

**Description:**  Occurs when an invalid API key of any form is passed.

{% code title="JSON" %}
```javascript
  {
    "status": true,
    "msg": "Invalid Api key.",
    "code": 401,
    "error": {
        "ErrorCode": "GS401",
        "ErrorMessage": "Invalid Api key",
        "details": "Invalid Api key."
    }
  }
```
{% endcode %}

## Update Geofence API 

**Code:** 400

**Description:**  Occurs when an unknown error is caught. Given to ensure graceful fails.

{% code title="JSON" %}
```javascript
  {
    "status": false,
    "msg": "Unknown Error.",
    "code": 400,
    "error": {
        "ErrorCode": "GS400",
        "ErrorMessage": "An error occured"
    }
  }
```
{% endcode %}

**Code:** 400

**Description:**  Occurs when geofence\_id is not passed in the request header.

{% code title="JSON" %}
```javascript
  {
      "status": false,
      "msg": "Error Occured.",
      "code": 400,
      "error": {
          "ErrorCode": "GS402",
          "ErrorMessage": "Invalid request",
          "details": {
              "geofence_id": [
                  "This field is required."
              ]
          }
      }
  }
```
{% endcode %}

**Code:** 401

**Description:**  Occurs when API key is not provided in the request header.

{% code title="JSON" %}
```javascript
  {
    "status": true,
    "msg": "No Api key in Header provided",
    "code": 401,
    "error": {
        "ErrorCode": "GS401",
        "ErrorMessage": "Invalid Api key",
        "details": "No Api key in Header provided"
    }
  }
```
{% endcode %}

**Code:** 401

**Description:**  Occurs when an invalid API key of any form is passed.

{% code title="JSON" %}
```javascript
  {
    "status": true,
    "msg": "Invalid Api key.",
    "code": 401,
    "error": {
        "ErrorCode": "GS401",
        "ErrorMessage": "Invalid Api key",
        "details": "Invalid Api key."
    }
  }
```
{% endcode %}

## Get Geofence API 

**Code:** 400

**Description:**  Occurs when an unknown error is caught. Given to ensure graceful fails.Possibly bad formatting in the request.

{% code title="JSON" %}
```javascript
  {
    "status": false,
    "msg": "Unknown Error.",
    "code": 400,
    "error": {
        "ErrorCode": "GS400",
        "ErrorMessage": "An error occured"
    }
  }
```
{% endcode %}

**Code:** 401

**Description:**  Occurs when API key is not provided in the request header.

{% code title="JSON" %}
```javascript
  {
    "status": true,
    "msg": "No Api key in Header provided",
    "code": 401,
    "error": {
        "ErrorCode": "GS401",
        "ErrorMessage": "Invalid Api key",
        "details": "No Api key in Header provided"
    }
  }
```
{% endcode %}

**Code:** 401

**Description:**  Occurs when an invalid API key of any form is passed.

{% code title="JSON" %}
```javascript
  {
    "status": true,
    "msg": "Invalid Api key.",
    "code": 401,
    "error": {
        "ErrorCode": "GS401",
        "ErrorMessage": "Invalid Api key",
        "details": "Invalid Api key."
    }
  }
```
{% endcode %}

## Delete Geofence API 

**Code:** 400

**Description:**  Occurs when an unknown error is caught. Given to ensure graceful fails.Possibly bad formatting in the request.

{% code title="JSON" %}
```javascript
  {
    "status": false,
    "msg": "Unknown Error.",
    "code": 400,
    "error": {
        "ErrorCode": "GS400",
        "ErrorMessage": "An error occured"
    }
  }
```
{% endcode %}

**Code:** 400

**Description:**  Occurs when the given geofence doesn't exist.

{% code title="JSON" %}
```javascript
  {
      "status": false,
      "msg": "Error Occured.",
      "code": 400,
      "error": {
          "ErrorCode": "GS400",
          "ErrorMessage": "An error occured",
          "details": "Geofence does not exist."
      }
  }
```
{% endcode %}

**Code:** 400

**Description:**  Occurs when geofence\_id is not provided.

{% code title="JSON" %}
```javascript
  {
      "status": false,
      "msg": "Error Occured.",
      "code": 400,
      "error": {
          "ErrorCode": "GS402",
          "ErrorMessage": "Invalid request",
          "details": {
              "geofence_id": [
                  "This field is required."
              ]
          }
      }
  }
```
{% endcode %}

**Code:** 401

**Description:**  Occurs when API key is not provided in the request header.

{% code title="JSON" %}
```javascript
  {
    "status": true,
    "msg": "No Api key in Header provided",
    "code": 401,
    "error": {
        "ErrorCode": "GS401",
        "ErrorMessage": "Invalid Api key",
        "details": "No Api key in Header provided"
    }
  }
```
{% endcode %}

**Code:** 401

**Description:**  Occurs when an invalid API key of any form is passed.

{% code title="JSON" %}
```javascript
  {
    "status": true,
    "msg": "Invalid Api key.",
    "code": 401,
    "error": {
        "ErrorCode": "GS401",
        "ErrorMessage": "Invalid Api key",
        "details": "Invalid Api key."
    }
  }
```
{% endcode %}

## Get Events API

**Code:** 400

**Description:**  Occurs when either given geofence\_id or location\_id is invalid or doesn't exist or the given geofence\_id is not event\_enabled.

{% code title="JSON" %}
```javascript
  {
      "status": false,
      "msg": "Error Occured.",
      "code": 400,
      "error": {
          "ErrorCode": "GS402",
          "ErrorMessage": "Invalid request",
          "details": {
              "geofence_id": {
                  "geofence_id": "This field is invalid"
              },
              "location_id": {
                  "location_id": "This field is invalid"
              }
          }
      }
  }
```
{% endcode %}

**Code:** 400

**Description:**  Occurs when an unknown error is caught. Given to ensure graceful fails.Possibly bad formatting in the header.

{% code title="JSON" %}
```javascript
  {
      "status": false,
      "msg": "Unknown Error.",
      "code": 400,
      "error": {
          "ErrorCode": "GS400",
          "ErrorMessage": "An error occured"
      }
  }
```
{% endcode %}

**Code:** 401

**Description:**  Occurs when API key is not provided in the request header.

{% code title="JSON" %}
```javascript
  {
    "status": true,
    "msg": "No Api key in Header provided",
    "code": 401,
    "error": {
        "ErrorCode": "GS401",
        "ErrorMessage": "Invalid Api key",
        "details": "No Api key in Header provided"
    }
  }
```
{% endcode %}

**Code:** 401

**Description:**  Occurs when an invalid API key of any form is passed.

{% code title="JSON" %}
```javascript
  {
    "status": true,
    "msg": "Invalid Api key.",
    "code": 401,
    "error": {
        "ErrorCode": "GS401",
        "ErrorMessage": "Invalid Api key",
        "details": "Invalid Api key."
    }
  }
```
{% endcode %}

## Get Trips List API 

**Code:** 400

**Description:**  Occurs when mandatory field app\_id is not provided.

{% code title="JSON" %}
```javascript
  {
    "status": false,
    "msg": "Error Occured.",
    "code": 400,
    "error": {
        "ErrorCode": "GS402",
        "ErrorMessage": "Invalid request",
        "details": {
            "app_id": [
                "This field is required."
            ]
        }
    }
  }
```
{% endcode %}

**Code:** 400

**Description:**  Occurs when mandatory field user\_id is not provided.

{% code title="JSON" %}
```javascript
  {
    "status": false,
    "msg": "Error Occured.",
    "code": 400,
    "error": {
        "ErrorCode": "GS402",
        "ErrorMessage": "Invalid request",
        "details": {
            "user_id": [
                "This field is required."
            ]
        }
    }
  }
```
{% endcode %}

**Code:** 400

 **Description:**  Occurs when an unknown error is caught. Given to ensure graceful fails. Possibly bad formatting in the request.

{% code title="JSON" %}
```javascript
  {
    "status": false,
    "msg": "Unknown Error.",
    "code": 400,
    "error": {
        "ErrorCode": "GS400",
        "ErrorMessage": "An error occured"
    }
  }
```
{% endcode %}

**Code:** 401

**Description:**  Occurs when API key is not provided in the request header.

{% code title="JSON" %}
```javascript
  {
    "status": true,
    "msg": "No Api key in Header provided",
    "code": 401,
    "error": {
        "ErrorCode": "GS401",
        "ErrorMessage": "Invalid Api key",
        "details": "No Api key in Header provided"
    }
  }
```
{% endcode %}

**Code:** 401

**Description:**  Occurs when an invalid API key of any form is passed.

{% code title="JSON" %}
```javascript
  {
    "status": true,
    "msg": "Invalid Api key.",
    "code": 401,
    "error": {
        "ErrorCode": "GS401",
        "ErrorMessage": "Invalid Api key",
        "details": "Invalid Api key."
    }
  }
```
{% endcode %}

## Get Trip Summary API

**Code:** 400

**Description:**  Occurs when mandatory field trip\_id is not provided.

{% code title="JSON" %}
```javascript
{
    "status": false,
    "msg": "Please provide a valid trip id.",
    "code": 400,
    "error": {
        "ErrorCode": "GS400",
        "ErrorMessage": "An error occured",
        "details": "Please provide a valid trip id."
    }
}
```
{% endcode %}

**Code:** 400

**Description:**  Occurs when invalid trip\_id is provided.

{% code title="JSON" %}
```javascript
{
    "status": false,
    "msg": "trip_id is invalid.",
    "code": 400,
    "error": {
        "ErrorCode": "GS402",
        "ErrorMessage": "Invalid request",
        "details": {
            "trip_id": {
                "trip_id": "This field is invalid."
            }
        }
    }
}
```
{% endcode %}

**Code:** 400

**Description:**  Occurs when an unknown error is caught. Given to ensure graceful fails. Possibly bad formatting in the request.

{% code title="JSON" %}
```javascript
  {
    "status": false,
    "msg": "Unknown Error.",
    "code": 400,
    "error": {
        "ErrorCode": "GS400",
        "ErrorMessage": "An error occured"
    }
  }
```
{% endcode %}

**Code:** 401

**Description:**  Occurs when API key is not provided in the request header.

{% code title="JSON" %}
```javascript
  {
    "status": true,
    "msg": "No Api key in Header provided",
    "code": 401,
    "error": {
        "ErrorCode": "GS401",
        "ErrorMessage": "Invalid Api key",
        "details": "No Api key in Header provided"
    }
  }
```
{% endcode %}

**Code:** 401

**Description:**  Occurs when an invalid API key of any form is passed.

{% code title="JSON" %}
```javascript
  {
    "status": true,
    "msg": "Invalid Api key.",
    "code": 401,
    "error": {
        "ErrorCode": "GS401",
        "ErrorMessage": "Invalid Api key",
        "details": "Invalid Api key."
    }
  }
```
{% endcode %}

