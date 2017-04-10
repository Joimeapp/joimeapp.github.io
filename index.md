---
layout: default
---

# [](#header-1)Joime
> Share rides to the activities you love.

Live application can be found via following url: https://joime.net

## Introduction

Joime API documentation provides information to web and app developers who wish to use Joime's Application Programming Interfaces (APIs).
The Joime API includes modules for managing trips and associated metadata.
In addition, this reference describes a number of related objects. The Joime API is a RESTful API service.

Our API is designed around standard REST CRUD (Create-Read-Update-Delete) semantics:

**POST** - Create a resource within a given collection

**GET** - Get a resource or collection of resources

**PUT** - Update a resource

**DELETE** - Delete a resource

Our default is to support JSON formatting, however if you prefer XML use the Content-Type header with value text/xml.
<hr>

## Authentication

### Device Access Tokens

Device tokens provide per user authentication for API requests. Device tokens are time based tokens that are created after login or registration. 

Pass following keys with values in the header for API request.
<pre>
device-id
auth-token
</pre>

<hr>

## Errors

Joime uses conventional HTTP response codes to indicate success or failure of an API request. In general, codes in the 2xx range indicate success, codes in the 4xx range indicate an error that resulted from the provided information (e.g. a required r was missing, a charge failed, etc.), and codes in the 5xx range indicate an error with Joime's servers.

### 200 (OK)
The request was processed successfully.

### 401 (Unauthorized)
The request could not be processed because no API key was provided, or the API key provided is invalid.

### 404 (Not Found)
The request could not be processed because the resource you are operating on could not be found.

### 422 (Unprocessable Entity)
The request could not be processed due to a validation rule.

### 500 (Server Error)
The request could not be processed due to a error on Joime's servers.

### Attributes:
**message** - A human-readable message giving more details about the error.

<hr>

## Pagination

Pagination is required for all 'list' requests. The default setting for any list request is to return 10 records.

### Parameters

page (optional) The page number of records to return (zero indexed).

per_page (optional) The number of records to return (Default: 10, Maximum: 100).

### Attributes

Paging data is returned in the 'pagination' element on list requests. The following data is made available.

**total** - Total number of items

**per_page** - The maximum number of records returned.

**current_page** - The current page requested

**last_page** - Last page that can be requested

**next_page_url** - The page after the page requested.

**prev_page_url** - The page before the page requested.

**from** - Index of the first returned record.

**to** - Index of the last returned record.

Example:

<pre>{
    "success": true,
    "data": { ... },
    "pagination": {
      "total": 19,
      "per_page": 10,
      "current_page": 1,
      "last_page": 2,
      "next_page_url": "http://localhost:8888/api/v2/content?page=2",
      "prev_page_url": null,
      "from": 1,
      "to": 10
    }
}
</pre>
<hr>
