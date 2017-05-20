---
layout: default
title: Joime Developer Portal | Spaces
permalink: /api/photos/
---

## Photos
<hr />
### Get last photo from space
<pre>
<pre><b>GET</b> /space/photo/{spaceCode}</pre>
</pre>

### Create a Photo for space
<pre><b>POST</b> /space/photo/{spaceCode}</pre>

#### Headers

Key | Value 
--------- | -------- 
device-id    | UUID of an authorized device 
auth-token   | Valid token for the device

#### Parameters

Parameter | Function | Type
--------- | -------- | ----
file | File object with jpg or png extentions | File

### Delete a Photo for space
<pre><b>DELETE</b> /space/photo/{photoId}</pre>

#### Headers

Key | Value 
--------- | -------- 
device-id    | UUID of an authorized device 
auth-token   | Valid token for the device

### Photo Object
<pre>
  {
    "id": 3,
    "created_at": "2017-05-15 20:58:33",
    "updated_at": "2017-05-15 20:58:33",
    "name": "breezy-point3.jpg",
    "photo_url": "https://s3.amazonaws.com/20170513-joime-public-bucket/images/breezy-point3.jpg",
    "thumb_url": "https://s3.amazonaws.com/20170513-joime-public-bucket/images/thumbnails/breezy-point3.jpg",
    "space_id": 10,
    "user_id": 1,
    "deleted_at": null
  }
</pre>



