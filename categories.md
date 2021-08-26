# Categories

Evis.Market categories API documentation.

Table of Contents
=================
* [Get categories list](#get-categories-list)

## Get categories list

URL: `/api/v1/categories/`

Method: `GET`

**URL params**

* parent_id - parent category id
* name - category name filter

**Example query**

    /api/v1/categories/?name=data&parent_id=1


**Successful response**

    HTTP status Code: 200

    {
      "status": "OK",

      "categories": [
        {
          "id": 1,
          "parent_id": null,
          "name": "Category1 name",
          "descr": "Category1 description",
          "logo_url": "https://domain.com/logo1.jpg",
          "slug": "category1"
        },
        {
          "id": 2,
          "parent_id": null,
          "name": "Category2 name",
          "descr": "Category2 description",
          "logo_url": "https://domain.com/logo2.jpg",
          "slug": "category2"
        }
      ]
    }

**Empty or not found response**

    HTTP status Code: 200

    {
      "status": "OK",

      "categories": []
    }
