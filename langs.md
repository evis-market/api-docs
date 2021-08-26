# Languages

Evis.Market languages API documentation.

Table of Contents
=================
* [Get languages list](#get-languages-list)

## Get languages list

URL: `/api/v1/langs/`

Method: `GET`

**Successful response**

    HTTP status Code: 200

    {
      "status": "OK",

      "langs": [
        {
          "id": 1,
          "name_native": "English",
          "name_en": "English",
          "slug": "en"
        },
        {
          "id": 2,
          "name_native": "Русский",
          "name_en": "Russian",
          "slug": "ru"
        }
      ]
    }
