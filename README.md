# api-docs

API documentation for [web-interface-backend](https://github.com/evis-market/web-interface-backend)

Table of Contents
=================

* [Introduction](#introduction)
* [HTTP response codes](#http-response-codes)
* [Success response example](#success-response-example)
* [Error response example](#error-response-example)
* [Authentication](auth.md)


### HTTP response codes
```
200: Success
400: Bad request
401: Unauthorized
403: Forbidden
404: Cannot be found
405: Method not allowed
50X: Server Error
```

## Authentication by login
----
Returns JWT access and refresh tokens.

URL: `/api/v1/auth/jwt/grant`

Method: `POST`

### Data Params
```json
{
  "grant_type": "password",
  "login": "email_or_phone_or_erc20_wallet",
  "password": "user_password"
}
```
*Login can be email, phone or ERC-20 wallet.*

    curl ...

### Successful response

HTTP Code: 200

```json
{
  "status": "OK",
  "access_token": "....jwt_token_data...",
  "refresh_token": "....jwt_token_data...",
  "token_type": "Bearer"
}
```

### Failed Response
HTTP Code: 400

```json
{
  "err_code": 400,
  "err_msg" : "login or password is invalid"
}
```

