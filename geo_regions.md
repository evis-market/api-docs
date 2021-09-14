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
          "name": "Europe",
          "parent_id": null,
          "iso_code": "EU"
        },
        {
          "id": 1,
          "name": "Spain",
          "parent_id": 1,
          "iso_code": "ESP"
        },
      ]
    }

**Empty or not found response**

    HTTP status Code: 200

    {
      "status": "OK",

      "geo_regions": []
    }
