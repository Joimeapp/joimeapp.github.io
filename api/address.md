---
layout: default
title: Joime Developer Portal | Spaces
permalink: /api/address/
---

### Get Adddresses for user
<pre>
<b>GET</b> /address/user/{user_id}
</pre>

Get address that user is part of. 

#### Headers

Key | Value 
--------- | -------- 
device-id    | UUID of an authorized device 
auth-token   | Valid token for the device

#### Parameters

Parameter | Function | Type
--------- | -------- | ----



### Create an Address
<pre><b>POST</b> /address</pre>

#### Parameters

Parameter | Function | Type
--------- | -------- | ----
class_id | 5 - I'm Going or 9 - Pick up | Int


### Address Object
<pre>
     {
        "latitude": "40.695062530010432",
        "longitude": "-73.991653893030872",
        "format_address": "206-212 Montague St, New York",
        "image": "https://maps.google.com/maps/api/staticmap?center=206-212 Montague St, New York&zoom=14&size=600x400&sensor=false&markers=206-212 Montague St, New York",
        "updated_at": "2017-08-04 15:28:35",
        "created_at": "2017-08-04 15:28:35",
        "id": 28
    }
</pre>



