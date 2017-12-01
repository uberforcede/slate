---
title: API Reference

language_tabs: 
  - shell
  - javascript

toc_footers:
  - <a href='#'>Sign Up to the Innovative Insurance program</a>
  
includes:
  - errors

search: true
---

# Introduction

Welcome 2 to the NextGen API of wefox, here you will find all the documentation to connect your product to the marvelous experience of wefox.

# Authentication

> To authorize, use this code:


```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "Authorization: <<Token>>"
```

```javascript
const wefox = require('wefox');

let api = wefox.authorize('<<TOKEN>>');
```

> Make sure to replace `<<TOKEN>>` with your API key.

NextGen API use Oauth2.0 as Authentication method. Before continue make sure to have the necessary credentials in order to continue.

Parameter | Mandatory | Description
--------- | ------- | -----------
client_id | true | Unic client id provided by wefox

`Authorization: <<TOKEN>>`

<aside class="notice">
You must replace <code><<TOKEN>></code> with your personal API key.
</aside>

# Real time Offer API

## Get Offers

```shell
curl "http://example.com/api/offer"
  -H "Authorization: <<TOKEN>>"
```

```javascript
const wefox = require('wefox');

let api = wefox.authorize('<<TOKEN>>');
let offers = api.offers.get();
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name": "Max",
    "product": "Liability",
    "fee": "43.75",
    "payment_terms":"Yearly"
  },
  {
    "id": 2,
    "name": "Max",
    "product": "Health",
    "fee": "50",
    "payment_terms":"Monthly"
  }
]
```

This endpoint retrieves all offers.

### HTTP Request

`GET http://example.com/api/offers`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
status | open | Filter all the offers by the offer status.
available | true | If set to false, the result will include offers that have already closed.



## Get a Specific Offer

```shell
curl "http://example.com/api/offer/2"
  -H "Authorization: <<TOKEN>>"
```

```javascript
const wefox = require('wefox');

let api = wefox.authorize('<<TOKEN>>');
let max = api.offers.get(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "name": "Max",
  "product": "Health",
  "fee": "50",
  "payment_terms":"Monthly"
}
```

This endpoint retrieves a specific offer.


### HTTP Request

`GET http://example.com/api/offers/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the offer to retrieve

## Delete a Specific Offer



```shell
curl "http://example.com/api/offer/2"
  -X DELETE
  -H "Authorization: <<TOKEN>>"
```

```javascript
const wefox = require('wefox');

let api = wefox.authorize('<<TOKEN>>');
let max = api.offers.delete(2);
```


This endpoint deletes a specific offer.

### HTTP Request

`DELETE http://example.com/api/offer/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the offer to delete

# Real time Digitalization API

## Update Contract

# Real time Claims API

## Get Claims List

## Update Claim

# Real time Payments API

## Issue customer payment

# Real time Master Data API

## Contract change

## Customer change