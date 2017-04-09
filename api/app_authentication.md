---
layout: default
title: Joime Developer Portal | App Authentication
permalink: /api/app_authentication/
---

## App Authentication
<hr />

### Login
<pre><b>POST</b> /applogin</pre>

#### Parameters

Parameter | Function | Type
--------- | -------- | ----
*email | Users email | String
*password | Users passord | String
*device | JSON Object with the following fields | JSON
*device.uuid | Unique identifier for a device | String
device.name | Name of the device | String
device.system_name | Device Type | String
device.system_version | Version of the OS | Double
device.model | Model of the device | String
device.localized_model | Localized model of the device | String
device.user_interface_idiom | iPhone or iPad | String
device.identifier_for_vendor | Apple internal ID for the device | String
device.apns_token | Token to recieve push notifications | String

### Register
<pre><b>POST</b> /appregister</pre>

#### Parameters

Parameter | Function | Type
--------- | -------- | ----
*first_name Users first name | String
*last_name | Users last name | String
*email | Users email | String
*password | Users passord | String
*password_confirmation | Password one more timr | String
*device | JSON Object with the following fields | JSON
*device.uuid | Unique identifier for a device | String
device.name | Name of the device | String
device.system_name | Device Type | String
device.system_version | Version of the OS | Double
device.model | Model of the device | String
device.localized_model | Localized model of the device | String
device.user_interface_idiom | iPhone or iPad | String
device.identifier_for_vendor | Apple internal ID for the device | String
device.apns_token | Token to recieve push notifications | String

### Successful response
<pre>
    {
  "success": true,
  "data": {
    "id": 1,
    "created_at": "2015-09-16 12:27:42",
    "updated_at": "2017-04-08 12:38:07",
    "first_name": "Andrey",
    "last_name": "Svetliy",
    "full_name": "Andrey Svetliy",
    "code": "",
    "email": "example@svetliy.com",
    "email_verified": 1,
    "email_verification_code": "ab109b862060b9ad490907d778771d66dffa6dfe227700fbed84bcdb386bfa19",
    "state": 2,
    "admin": 1,
    "status": null,
    "organization": "Organization or Dept.",
    "position": "My Position",
    "skills": null,
    "showemail": 1,
    "interests": null,
    "workingon": null,
    "phone": "6467172111",
    "phone_verified": 1,
    "phone_verification_code": null,
    "skype": null,
    "facebook": "face_user",
    "twitter": null,
    "googleplus": null,
    "github": null,
    "linkedin": null,
    "last_login": "2017-04-08 12:38:07",
    "last_activity": "2017-02-21 14:47:28",
    "favorites": null,
    "activation_code": "43ec517d68b6edd3015b3edc9a11367b827db8eea0db60964700634d22d4d0cb",
    "activation_expire": "2017-04-04 21:49:48",
    "activation_date": null,
    "create_spaces": 1,
    "notif_content": 1,
    "notif_like": 1,
    "notif_content_starred": 1,
    "notif_comment": 0,
    "notif_task": 0,
    "notif_mention": 1,
    "notif_invite": 1,
    "notif_request_seat": 1,
    "notif_request_pickup": 1,
    "email_content": 1,
    "email_like": 1,
    "email_content_starred": 0,
    "email_task": 0,
    "email_mention": 1,
    "email_invite": 1,
    "email_private_msg": 1,
    "email_request_seat": 0,
    "email_request_pickup": 0,
    "notif_post": 0,
    "email_post": 0,
    "invited_by": 0,
    "facebook_user_id": 10204507623862112,
    "access_token": null,
    "facebook_verified": 1,
    "total_facebook_friends": 0,
    "facebook_link": "https://www.facebook.com/app_scoped_user_id/10204507623862994/",
    "photo_url": "assets/avatar/1.jpg",
    "thumb_url": "assets/avatar/1.jpg",
    "device": {
      "id": 5,
      "created_at": "2017-04-05 14:08:37",
      "updated_at": "2017-04-08 12:38:07",
      "user_id": 1,
      "uuid": "1FBD29A0-1233-4E1D-9CB3-F97A81D34B1E",
      "name": "Andrey’s MacBook Pro",
      "system_name": "iOS",
      "system_version": "10.3",
      "model": "iPhone",
      "localized_model": "iPhone",
      "user_interface_idiom": "",
      "identifier_for_vendor": "B7A2CE10-7768-4102-9A7E-D36294AA5791",
      "type": "",
      "active": 1,
      "auth_token": "b655823d-3811-43d6-9bd3-7200900c11db"
    }
  }
}
</pre>

### Logout
<pre><b>POST</b> /applogout</pre>

#### Headers

Key | Value 
--------- | -------- 
*device-id    | UUID of an authorized device 
*auth-token   | Valid token for the device

<pre>
{
  "success": true
}
</pre>



