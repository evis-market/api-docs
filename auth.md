# Authentication

Evis.Market authentication API documentation.

Table of Contents
=================

* [Authentication by login: email/phone/erc-20 wallet](#authentication-by-login-emailphoneerc-20-wallet)
* [Refresh tokens](#refresh-tokens)

## Authentication by login: email/phone/erc-20 wallet

Returns JWT access and refresh tokens.

URL: `/api/v1/auth/jwt/grant`

Method: `POST`

**Request**

    {
      "grant_type": "password",
      "login": "email_or_phone_or_erc-20_wallet",
      "password": "user_password"
    }

Login can be email, phone

    curl ...


**Successful response**

    HTTP status Code: 200

    {
      "status": "OK",
      "access_token": "....jwt_token_data...",
      "refresh_token": "....jwt_token_data...",
      "token_type": "Bearer"
    }

**Failed response**

    HTTP status Code: 400

    {
      "status": "ERR",

      "error": {
          "code": 400,
          "msg": "invalid credentials"
      }
    }


## Refresh tokens

Returns JWT access and refresh tokens.

URL: `/api/v1/auth/jwt/grant`

Method: `POST`

**Request**

    {
      "grant_type": "refresh_token",
      "refresh_token": "....jwt_token_data..."
    }

**Successful response**

    HTTP status Code: 200

    {
      "status": "OK",
      "access_token": "....jwt_token_data...",
      "refresh_token": "....jwt_token_data...",
      "token_type": "Bearer"
    }

**Failed response**

    HTTP status Code: 400

    {
      "status": "ERR",

      "error": {
          "code": 400,
          "msg": "invalid token"
      }
    }
