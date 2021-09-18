# Sales

Evis.Market sales API documentation.

Table of Contents
=================
* [Buyer shopping list](#buyer-shopping-list)
* [Seller sales list](#seller-sales-list)


## Buyer shopping list

URL: `/api/v1/sales/buyer_shopping_list`

Method: `GET`

**Successful response**

    HTTP status Code: 200

    {
      "status": "OK",

      "sales": [
        {
          ...
        },
        {
          ...
        }
      ]
    }

## Seller sales list

URL: `/api/v1/sales/seller_sales_list`

Method: `GET`

**Successful response**

    HTTP status Code: 200

    {
      "status": "OK",

      "sales": [
        {
          ...
        },
        {
          ...
        }
      ]
    }
