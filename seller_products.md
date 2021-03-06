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
          "id": 1,
          "name": "Product1 name",
          "descr": "Product1 description",
          "price_by_request": false,
          "price_per_month": 9,
          "price_per_one_time": 100,
          "price_per_usage": true,
          "price_per_usage_descr": "$1 per 100 API requests",
          "price_per_year": 70,
          "rating": 0,
          "data_urls": [
            {
              "url": "https://drive.google.com/some_file_location1",
              "data_delivery_type_id": 1,
              "data_format_id": 1,
            },
            {
              "url": "https://drive.google.com/some_file_location2",
              "data_delivery_type_id": 1,
              "data_format_id": 2,
            }
          ]
        },
        {
            ...
        },
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

URL: `/api/v1/seller_products/my/`

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
      "data_samples": [
        "06ed84be-0eac-42a6-9020-213329db3737",
        "4f41af44-6f82-48b1-ba97-c86f5469ce04"
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
            "data_urls": {
                "0": "invalid format",
                "1": "invalid format"
            }
          }
      }
    }



## Update product

URL: `/api/v1/seller_products/my/:seller_product_id`

Method: `PUT`

This endpoint is equal to create product except method `PUT`.


## Delete product

URL: `/api/v1/seller_products/my/:seller_product_id`

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
