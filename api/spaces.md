---
layout: default
title: Joime Developer Portal | Spaces
permalink: /api/spaces/
---

## Space
<hr />
### Get spaces near location
<pre>
<b>GET</b> /space
</pre>

Get spaces which are located within the radius from the provided coordinates. Use case for the app: show all spaces near me.

#### Headers

Key | Value 
--------- | -------- 
device-id    | UUID of an authorized device.(optinal)
auth-token   | Valid token for the device.(optinal)

#### Parameters

Parameter | Function | Type 
--------- | -------- | ---- 
<b>*</b>latitude    | Filter by location (Example: 40.6892) | Double 
<b>*</b>longitude    | Filter by location (Example: -74.0444) | Double 
page | The page number of records to return (default: 1) | Integer 
per_page | The number of records to return (default: 10) | Integer 
radius | Radius around location default(20) in Miles | Integer 
activities | Fet spaces with specific activities. Default is to show all resutls. Example: [1,2] | Array[Int]]   
exclude_user_id | Hide videos that user is part of. | Integer
sort | sort content with one of the fields. default(title) | String
order| order sorted resulsts. default(ASC), or DESC | String

### Get Spaces for user
<pre>
<b>GET</b> /space/user/{user_id}
</pre>

Get spaces that user is part of. Use case for the app: show my spaces screen

#### Headers

Key | Value 
--------- | -------- 
device-id    | UUID of an authorized device 
auth-token   | Valid token for the device

#### Parameters

Parameter | Function | Type
--------- | -------- | ----


### Get Space
<pre>
<b>GET</b> /space/{space-code}
</pre>

#### Parameters

Parameter | Function | Type
--------- | -------- | ----
page | The page number of records to return (Example: 1) | Integer
per_page | The number of records to return (Example: 10) | Integer


### Create a Space
<pre><b>POST</b> /content</pre>

#### Parameters

Parameter | Function | Type
--------- | -------- | ----
class_id | 5 - I'm Going or 9 - Pick up | Int
content_text | Message that user typed | String
space_code | The description of the video | String
event | JSON Object with the following fields | JSON
event.allday | If event is all day or not | Boolean
event.driving | Is driving or picking up | Boolean
event.start_date | Start date of the trip | Date
event.end_date | End date of the trip | Date
event.number_of_seats | Number of total seats | Integer
event.price_per_seat | Price for each seat | Integer
event.space | If of a space for a trip | Integer
event.activity_id | Id of activity for a trip | Integer
event.waiting | Should always be false | Boolean
event.zoom | Zoon of an image that is shown on the web, default 14 | Integer
event.addressObject | JSON Object with the following fields | JSON
event.addressObject.latitude | Latitude of an address | Double
event.addressObject.longitude | Longitude of an address | Double
event.addressObject.formatAddress | Full formatted address | String
event.addressObject.locationType | Data that is coming from google | String
event.addressObject.image | Url to an image that is shown on a web | String


### Space Object
<pre>
    {
            "id": 20,
            "created_at": "2015-09-28 12:28:04",
            "updated_at": "2015-09-28 18:58:49",
            "code": "brooklyn-boulders",
            "title": "Brooklyn boulders",
            "description": "\"a good space with many routes and challenges for a wide variety of skill levels.\"",
            "active": 1,
            "access": "PU",
            "options": {
                "features": []
            },
            "user_id": 4,
            "lat": "40.679653",
            "lng": "-73.98438",
            "address": "575 Degraw St, Brooklyn, NY 11217",
            "category": "",
            "activities": [
                {
                    "id": 10,
                    "created_at": "-0001-11-30 00:00:00",
                    "updated_at": "-0001-11-30 00:00:00",
                    "code": "rock-climbing",
                    "title": "Rock Climbing",
                    "icon": "assets/icons/rock-climbing_icon.png",
                    "description": "Rock Climbing",
                    "active": 1,
                    "pivot": {
                        "space_id": 20,
                        "activity_id": 10
                    }
                }
         
</pre>



