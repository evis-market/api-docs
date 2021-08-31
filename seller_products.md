# Seller products management

Evis.Market seller products management API documentation.

This service available for authenticated seller only.

Table of Contents
=================
* [List products](#list-products)
* [Get product](#get-product)
* [Create product](#create-product)
* [Update product](#update-product)
* [Delete product](#delete-product)

## List products

URL: `/api/v1/seller_products/my/`

Method: `GET`

**Successful response**

    HTTP status Code: 200

    {
      "status": "OK",

      "products": [
        {
          "name": "Product1 name",
          "descr": "Product1 description",
          ...
        },
        {
          "name": "Product2 name",
          "descr": "Product2 description",
          ...
        }
      ]
    }

**Successful empty response**

    HTTP status Code: 200

    {
      "status": "OK",

      "products": []
    }


**Failed response**

    HTTP status Code: 403

    {
      "status": "ERR",

      "error": {
          "code": 403,
          "msg" : "forbidden"
      }
    }


## Get product

URL: `/api/v1/seller_products/my/:seller_product_id`

Method: `GET`

**URL parameters**

* seller_product_id - seller product ID, example: 1

**Successful response**

    HTTP status Code: 200

    {
      "status": "OK",

      "product": {
        "name": "Product1 name",
        "descr": "Product1 description",
        ...
      }
    }

**Failed response**

    HTTP status Code: 401

    {
      "status": "ERR",

      "error": {
          "code": 401,
          "msg" : "unauthorized"
      }
    }


## Create product

URL: `/api/v1/sellers/settings/my/`

Method: `POST`

**Request**

    {
      "name": "Product name",
      "descr": "Product description",
      "price_one_time": 99.99,
      "price_per_month": 199,
      "price_per_year": 999,
      "price_by_request": false,
      "price_per_usage": true,
      "price_per_usage_descr": "$10 per 1000 API requests",

      "data_categories_ids": [1, 2, 3],
      "data_langs_ids": [1, 2, 3],
      "data_geo_regions_ids": [1, 2, 3],
      "data_types_ids": [1],
      "data_formats_ids": [1, 2],
      "data_delivery_types_ids": [1, 2],
      "data_urls": [
        { "data_delivery_type_id": 1, "data_format_id": 1, "url": "http://domain.com/data1.xlsx" },
        { "data_delivery_type_id": 1, "data_format_id": 2, "url": "http://domain.com/data1.xml" }
      ],
      "data_sample_urls": [
        "http://domain.com/data_sample1.xls",
        "http://domain.com/data_sample2.xls"
      ]
    }

**Successful response**

    HTTP status Code: 200

    {
      "status": "OK"
    }

**Failed response**

    HTTP status Code: 400

    {
      "status": "ERR",

      "error": {
          "code": 400,
          "msg" : "bad request",

          "invalid_fields": {
            "name": "required field",
            "descr": "to long, 300 symbols maximum",
            "data_urls": [
                { "data_delivery_type_id": 1, "data_format_id": 1, "error": "invalid format" }
            ]
          }
      }
    }



## Update product

URL: `/api/v1/sellers/settings/my/:seller_product_id`

Method: `PUT`

This endpoint is equal to create product except method `PUT`.


## Delete product

URL: `/api/v1/sellers/settings/my/:seller_product_id`

Method: `DELETE`

**Successful response**

    HTTP status Code: 200

    {
      "status": "OK"
    }


**Failed response**

    HTTP status Code: 403

    {
      "status": "ERR",

      "error": {
          "code": 403,
          "msg" : "Forbidden"
      }
    }
