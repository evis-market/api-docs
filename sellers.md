# Sellers

Evis.Market sellers API documentation.

Table of Contents
=================
* [Get self settings](#get-self-settings)
* [Update self settings](#update-self-settings)

## Get self settings

URL: `/api/v1/sellers/settings/my`

Method: `GET`

**Successful response**

    HTTP status Code: 200

    {
      "status": "OK",

      "seller": {
        "user_id": 1,
        "name": "Seller name",
        "descr": "Seller description",
        "logo_url": "https://domain.com/logo.jpg",
        "wallet_for_payments_erc20": "0x....",
        "rating": 4.97,

        "sites": [
          { "url": "https://domain1.com/" },
          { "url": "https://domain2.com/" }
        ],

        "phones": [
          { "phone": "1231231231", "comment": "phone1 comment" },
          { "phone": "1231231232", "comment": "phone2 comment" }
        ],

        "emails": [
          { "email": "email1@test.com", "comment": "email1 comment" },
          { "email": "email2@test.com", "comment": "email2 comment" }
        ],
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


## Update self settings

URL: `/api/v1/sellers/settings/my`

Method: `PUT`

**Request**

    {
      "name": "Seller name",
      "descr": "Seller description",
      "wallet_for_payments_erc20": "0x....",

      "sites": [
          { "url": "https://domain1.com/" },
          { "url": "https://domain2.com/" }
        ],

        "phones": [
          { "phone": "1231231231", "comment": "phone1 comment" },
          { "phone": "1231231232", "comment": "phone2 comment" }
        ],

        "emails": [
          { "email": "email1@test.com", "comment": "email1 comment" },
          { "email": "email2@test.com", "comment": "email2 comment" }
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
            "name": "to long, 256 symbols maximum",
            "email": "email2#test.com is invalid"
          }
      }
    }
