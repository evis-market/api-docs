# geo regions

Evis.Market geo regions API documentation.

Table of Contents
=================
* [Get geo regions list](#get-geo-regions-list)

## Get geo regions list

URL: `/api/v1/geo_regions/`

Method: `GET`

**URL params**

* parent_id - parent geo region id
* name - geo region name filter

**Example query**

    /api/v1/geo_regions/?name=data&parent_id=1


**Successful response**

    HTTP status Code: 200

    {
      "status": "OK",

      "geo_regions": [
        {
          "id": 1,
          "parent_id": null,
          "name": "geo region1 name",
          "logo_url": "https://domain.com/logo1.jpg",
          "slug": "geo region1",
          "sort_id": 1
        },
        {
          "id": 2,
          "parent_id": null,
          "name": "geo region2 name",
          "logo_url": "https://domain.com/logo2.jpg",
          "slug": "geo region2",
          "sort_id": 90
        }
      ]
    }

**Empty or not found response**

    HTTP status Code: 200

    {
      "status": "OK",

      "geo_regions": []
    }
