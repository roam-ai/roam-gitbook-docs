---
description: >-
  A Python backend library for GeoSpark Location Subscription. It is used to
  subscribe to a group of user's locations at the project level or to subscribe
  to the location of a single user.
---

# Python Library

## Installation

You can install our python SDK from the PIP package manager.

```python
pip install roam-python
```

## Example Usage

You can think of this library as a wrapper around our REST API which needs your API key for authorization and it works as per project level.

It is fairly simple to use:

* Create an instance of a client with your API key.
* Define your custom callback function which will be executed on every location received from the server.
* Subscribe with the help of the client for receiving the location updates.

Example usage code:

```python
from roam import Client​

#Do something when you receive locations
def custom_callback_function(payload):    
  print(payload)    
  log(payload)
  
​#To listen locations at project level with the callback function
client = Client(API_KEY=<API-KEY>, CALLBACK=<custom_callback_function>)

​#Subcribe to locations
client.sub()
```

## Subscribe Locations <a id="Subscribe-Locations"></a>

### Single User's Locations <a id="Single-User&apos;s-Locations"></a>

You can also use the Library to subscribe to a single user's location and listen to it. You have to pass the User ID which our Mobile SDKs return during creating a user.

```python
client = Client(API_KEY=<API-KEY>, USER_ID=<USER-ID>, CALLBACK=<custom_callback_function>)
```

**Example Usage**

```python
from roam import Client​

#Do something when you receive locations
def custom_callback_function(payload):    
  print(payload)    
  log(payload)
  
​#To listen locations at user level with the callback function
client = Client(API_KEY=<API-KEY>, USER_ID=<USER-ID>, CALLBACK=<custom_callback_function>)

​#Subcribe to locations
client.sub()
```

### List of User’s Locations <a id="List-of-User&#x2019;s-Locations"></a>

You can use the Library to subscribe to a list of users and listen to their location updates.

Create a list with the User IDs you want to listen to and use the list when creating the client instance.

```python
USER_LIST = ["user_id1", "user_id2", ...]
client = Client(API_KEY=<API-KEY>, USER_ID=<USER_LIST>, CALLBACK=<custom_callback_function>)
```

**Example Usage**

```python
from roam import Client​

#Do something when you receive locations
def custom_callback_function(payload):    
  print(payload)    
  log(payload)​

#Create a user list with the list of user_id's
USER_LIST = ["user_id1", "user_id2", ..]​

#To listen locations for list of user with the callback function
client = Client(API_KEY=<API-KEY>, USER_ID=<USER-LIST>, CALLBACK=<custom_callback_function>)​

#Subcribe to locations
client.sub()
```

### Group of User’s Location <a id="Group-of-User&#x2019;s-Location"></a>

You can also use the SDK to subscribe to a user group and listen to their location updates.

You can get the group\_id from our developer API for user grouping. You can use the group\_id when creating the Client instance to listen to locations at the user group level.

```python
client = Client(API_KEY=<API-KEY>, GROUP_ID=<GROUP_ID>, CALLBACK=<custom_callback_function>)
```

**Example Usage**

```python
from roam import Client​

#Do something when you receive locations
def custom_callback_function(payload):    
  print(payload)    
  log(payload)
  
​#To listen locations for list of user with the callback function
client = Client(API_KEY=<API-KEY>, GROUP_ID=<GROUP_ID>, CALLBACK=<custom_callback_function>)​

#Subcribe to locations
client.sub()
```

## Unsubscribe

If you wish to unsubscribe from location updates at any point, use the below code to disconnect from the client instance.

```python
client.disconnect()
```

## Handling Callbacks 

By default the Library prints out the locations. If the locations are required for any other output, then use a callback function.

```python
def custom_callback_function(payload):    
  # print(payload)    
  # save_to_file(payload)    
  # log(payload)
  
​client = Client(API_KEY=<API-KEY>, CALLBACK=<custom_callback_function>)
```



