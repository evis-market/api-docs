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
        "logo_url": "/media/seller_logo/6a401d84-5595-473c-9268-b6b9f013839d.png",
        "wallet_for_payments_erc20": "0x....",
        "rating": 4.97,

        "contacts": [
          { "type_id": 1, "value": "https://domain1.com/", "comment": "main site" },
          { "type_id": 1, "value": "https://domain2.com/", "comment": "" },
          { "type_id": 2, "value": "1231231231", "comment": "phone1 comment" },
          { "type_id": 2, "value": "1231231232", "comment": "phone2 comment" }
          { "type_id": 3: "value": "email1@test.com", "comment": "email1 comment" },
          { "type_id": 3: "value": "email2@test.com", "comment": "" }
        ]
      }
    }

Type ID's:
* `1` - URL
* `2` - phone
* `3` - email

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
      "logo_url": "6a401d84-5595-473c-9268-b6b9f013839d",

      "contacts": [
        { "type_id": 1, "value": "https://domain1.com/", "comment": "main site" },
        { "type_id": 1, "value": "https://domain2.com/", "comment": "" },
        { "type_id": 2, "value": "1231231231", "comment": "phone1 comment" },
        { "type_id": 2, "value": "1231231232", "comment": "phone2 comment" }
        { "type_id": 3: "value": "email1@test.com", "comment": "email1 comment" },
        { "type_id": 3: "value": "email2@test.com", "comment": "" }
      ]
    }

Type ID's:
* `1` - URL
* `2` - phone
* `3` - email

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
            "email": "invalid format",
            "contacts": {
              "0": "invalid format",
              "1": "invalid format"
            }
          }
      }
    }
