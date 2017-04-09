---
layout: default
title: Joime Developer Portal | Content
permalink: /api/content/
---

## Content
<hr />
### List Content
<pre>
<b>GET</b> /content
</pre>

#### Parameters

Parameter | Function | Type 
--------- | -------- | ---- 
<b>*</b>latitude    | Filter by location (Example: 40.6892) | Double 
<b>*</b>longitude    | Filter by location (Example: -74.0444) | Double 
page | The page number of records to return (default: 1) | Integer 
per_page | The number of records to return (default: 10) | Integer 
radius | Radius around location default(20) in Miles | Integer 
activity_id | default(0) - get content from specific activity id | Integer 
sort | sort content with one of the fields. default(start_date) | String
order| order sorted resulsts. default(ASC), or DESC | String

### List Content for user
<pre>
<b>GET</b> /content/user
</pre>

#### Headers

Key | Value 
--------- | -------- 
device-id    | UUID of an authorized device 
auth-token   | Valid token for the device

#### Parameters

Parameter | Function | Type
--------- | -------- | ----
page | The page number of records to return (Example: 1) | Integer
per_page | The number of records to return (Example: 10) | Integer

### List Content from space
<pre>
<b>GET</b> /content/space/{space-code}
</pre>

#### Parameters

Parameter | Function | Type
--------- | -------- | ----
page | The page number of records to return (Example: 1) | Integer
per_page | The number of records to return (Example: 10) | Integer


### Create a Content
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


### Content Object
<pre>
    {
      "id": 3,
      "created_at": "2017-04-04 23:31:32",
      "updated_at": "2017-04-04 23:31:32",
      "space_id": 12,
      "user_id": 2,
      "updated_by": 2,
      "content_text": "Lets goo",
      "class_id": 5,
      "content_data": null,
      "shared_from_id": null,
      "address_id": 2,
      "privacy": 0,
      "activity_id": 2,
      "start_date": "2017-04-12 05:00:00",
      "end_date": "2017-04-12 05:00:00",
      "all_day": 0,
      "driving": 1,
      "number_of_seats": 1,
      "price_per_seat": 15,
      "deleted_at": null,
      "address": {
        "id": 2,
        "created_at": "2017-02-24 00:29:42",
        "updated_at": "2017-02-24 00:29:42",
        "latitude": 40.70884,
        "longitude": -74.00517,
        "format_address": "64 Fulton St, New York",
        "location_type": "",
        "image": "https://maps.google.com/maps/api/staticmap?center=64 Fulton St, New York&zoom=16&size=600x400&sensor=false&markers=64 Fulton St, New York"
      },
      "space": {
        "id": 12,
        "created_at": "2014-12-30 21:29:42",
        "updated_at": "2014-12-30 21:29:42",
        "code": "far-rockway",
        "title": "Far rockway",
        "description": "The closest surfing beach to nyc, the crowds are more challenging here than the waves. Average beachbreaks that need a sizable swell to make it in here with big e swells bringing some decent lefts.",
        "active": 1,
        "access": "PU",
        "options": {
          "features": []
        },
        "user_id": 1,
        "lat": "40.58377878530724",
        "lng": "-73.81067253649235",
        "address": "101-89 shore front pkwy, rockaway park, ny 11694",
        "category": ""
      },
      "user": {
        "id": 2,
        "full_name": "Iteny Potamkin",
        "code": "ItenyPotamkin",
        "thumb_url": "assets/avatar/thumbs/148790370458af9bd844351.jpg",
        "photo_url": "assets/avatar/148790370458af9bd844351.jpg"
      },
      "attendants": []
    }
</pre>



