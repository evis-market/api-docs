# Products catalog

Evis.Market products catalog API documentation.

Table of Contents
=================
* [List not empty categories](#list-not-empty-categories)
* [List category products](#list-category-products)
* [Get filter options](#get-filter-options)
* [Get product detailed information](#get-product-detailed-information)
* [Get related products](#get-related-products)
* [Get all options in one query](#get-all-options-in-one-query)


## List not empty categories

URL: `/api/v1/products_catalog/categories/`

Method: `GET`

**Successful response**

    HTTP status Code: 200

    {
      "status": "OK",

      "categories": [
        {
          "name": "Category1 name",
          ...
        },
        {
          "name": "Category2 name",
          ...
        }
      ]
    }


## List category products

URL: `/api/v1/products_catalog/products/`

Method: `GET`

**Query parameters**

all filter options:

* category_ids - products category ID, example: 1,2,3

**Successful response**

    HTTP status Code: 200

    {
      "status": "OK",
      "products": [
        ...
      ]
    }


## Get filter options

URL: `/api/v1/products_catalog/filter_options/`

Method: `GET`

**URL parameters**

* category_id - products category ID, example: 1

**Successful response**

    HTTP status Code: 200

    {
      "status": "OK",
      "filter_options": [
        ...
      ]
    }



## Get product detailed information
Получить детальную информация о товаре + полные данные продавца + версия

## Get related products

URL: `/api/v1/products_catalog/related_products/:seller_product_id`

Method: `GET`

**Successful response**

    HTTP status Code: 200

    {
      "status": "OK",

      "related_products": [
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

      "related_products": []
    }


## Get all options in one query

URL: `/api/v1/products_catalog/all_products_options`

Method: `GET`

**Successful response**

    HTTP status Code: 200

    {
      "status": "OK",

      "categories": [],
      "langs": [],
      "geo_regions": [],
      "data_types": [],
      "data_delivery_types": []
    }
