# Authentication

Evis.Market authentication API documentation.


## Authentication by email or phone

Returns JWT access and refresh tokens.

URL: `/api/v1/auth/jwt/grant`

Method: `POST`

**Request**

    {
      "grant_type": "password",
      "login": "email_or_phone",
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
          "msg" : "login or password is invalid"
      }
    }


## Refresh tokens

Returns JWT access and refresh tokens.

URL: `/api/v1/auth/jwt/grant`

Method: `POST`

**Request**

    {
      "grant_type": "refresh_token",
      "refresh_token": "....jwt_token_data...",
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

    HTTP status Code: 404

    {
      "status": "ERR",

      "error": {
          "code": 404,
          "msg" : "refresh token not found"
      }
    }
