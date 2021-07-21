---
description: Learn more about the key concepts of GeoSpark location technology.
---

# Key Concepts

Below are the key concepts of GeoSpark location technology:

## **Location update** 

The fundamental component of GeoSpark location tracking. It is a package of data collected about a users’ location that includes latitude, longitude, altitude, speed, direction, activity and [more](https://geospark.co/knowledgebase/what-data-points-do-you-collect/).

## **Location module** 

A desired data flow of a location update. Depending on what you intend to do with the location update we distinguish 4 different location modules: Tracker, Publisher, Listener, Processor.

## **Location Tracker** 

The location update is collected by the GPS via GeoSpark SDK and stored locally in the mobile device. Use it if you want simple location tracking and store the location data yourself. 

## **Location Publisher** 

The location update is collected by the GPS via GeoSpark SDK, sent from the mobile device to the backend server and stored in the GeoSpark database. Use it if you want to store the data on GeoSpark servers and go beyond simple location tracking by accessing other GeoSpark products.

## **Location Listener** 

The location update returns from the database through the server to a mobile device.

## **Location Processor** 

The location update stored in the database is processed according to the respective API call. 

## **Location tracking mode**  

Customization of location tracking with varying frequencies of updates and levels of battery drainInsights. We differentiate three default modes: Active, Reactive, Passive and one fully customizable. Read more [here](https://geosparkai.atlassian.net/wiki/spaces/MGKS/pages/804388923/Location+Tracking).

