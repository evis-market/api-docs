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

      "shopping_list": [
        {
          "created_at": "2021-10-16 13:17:17",
          "uuid": "123e4567-e89b-12d3-a456-426614174000",
          "amount": 12345.6789,

          "seller: {
            "id": 12345,
            "name": "Name",
            "logo_url": "https://evis.market/img/sellers/logo/12345.jpg",
            "rating: 4.93
          },

          "products": [
            {
              "id": 1234,
              "name": "Product name",
              "descr": "Product description",
              "price_per_one_time": 1200,
              "price_per_month": 0,
              "price_per_year": 0,
              "price_by_request": false,
              "price_per_usage": true,
              "price_per_usage_descr": "some text described pricing",
              "rating": 4.99,
              "total_reviews_cnt": 267,
              "version": 1
            }
          ]
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
          "created_at": "2021-10-16 13:17:17",
          "uuid": "123e4567-e89b-12d3-a456-426614174000",
          "amount": 12345.6789,

          "buyer: {
            "id": 12345,
            "first_name": "Name",
            "last_name": "LastName",
            "wallet_erc20": "0x65b7E47E7FBDA46531B40B3DDfdE3460556BBE39"
          },

          "products": [
            {
              "id": 1234,
              "name": "Product name",
              "descr": "Product description",
              "price_per_one_time": 1200,
              "price_per_month": 0,
              "price_per_year": 0,
              "price_by_request": false,
              "price_per_usage": true,
              "price_per_usage_descr": "some text described pricing",
              "rating": 4.99,
              "total_reviews_cnt": 267,
              "version": 1
            }
          ]
        }
      ]
    }
