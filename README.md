# api-docs

Evis.Market API documentation for [web-interface-backend](https://github.com/evis-market/web-interface-backend)

Table of Contents
=================

* [Introduction](#introduction)
* [HTTP response codes](#http-response-codes)
* [Error codes](#error-codes)
* [Successful response example](#successful-response-example)
* [Error response example](#error-response-example)
* [Error response example with invalid fields](#error-response-example-with-invalid-fields)
* [Authentication](auth.md)
* [Users](users.md) Signup, password recovery, email confirmation etc.
* [Sellers](sellers.md)
* [Categories](categories.md)
* [Geo regions](geo_regions.md)
* [Languages](langs.md)

## Introduction

Production BASE URL: `https://evis.market`

Test BASE URL: `https://test.evis.market`


## HTTP response codes

    200: Success
    400: Bad request
    401: Unauthorized
    403: Forbidden
    404: Cannot be found
    405: Method not allowed
    50X: Server Error


## Error codes

    400: Bar request
    401: Unauthorized
    403: Forbidden
    404: Cannot be found


## Successful response example

    HTTP status Code: 200

    {
      "status": "OK"
    }


## Error response example

    HTTP status Code: 400

    {
      "status": "ERR",

      "error": {
          "code": 400,
          "msg" : "login or password is invalid"
      }
    }


## Error response example with invalid fields
    HTTP status Code: 400

    {
      "status": "ERR",

      "error": {
          "code": 400,
          "msg" : "bad request",
          "invalid_fields": {
            "name": "to long, 256 symbols maximum",
            "email": "is invalid"
          }
      }
    }
