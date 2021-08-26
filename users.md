# Users

Evis.Market users API documentation.


## Signup by email or phone

URL: `/api/v1/users/signup`

Method: `POST`

**Request**

    {
      "first_name": "Evgeny",
      "last_name": "Mamonov",
      "phone": "15552223456",
      "email": "test@test.com",
      "password": "some_very_strong_password",
    }

**Required fields**
* phone or email (one of)
* password

**Successful response**

    HTTP status Code: 200

    {
      "status": "OK",
      "user_id": 1
    }

**Failed response**

    HTTP status Code: 405

    {
      "status": "ERR",

      "error": {
          "code": 405,

          "invalid_fields": {
            "email": "invalid format",
            "password": "too short, 8 symbols minimum",
          },

          "msg" : "bad request"
      }
    }


## Send confirmation email

Generates new secret_code and sends email with link to confirm email.

URL: `/api/v1/users/send_email_confirmation`

Method: `POST`

**Request**

    {
      "email": "test@test.com",
    }

**Successful response**

    HTTP status Code: 200

    {
      "status": "OK",
    }

**Failed response**

    HTTP status Code: 404

    {
      "status": "ERR",

      "error": {
          "code": 404,
          "msg" : "email not found"
      }
    }


## Confirm email

URL: `/api/v1/users/confirm_email`

Method: `POST`

**Request**

    {
      "email": "test@test.com",
      "secret_code": "asd134df"
    }

**Successful response**

    HTTP status Code: 200

    {
      "status": "OK",
    }

**Failed response**

    HTTP status Code: 405

    {
      "status": "ERR",

      "error": {
          "code": 405,
          "msg" : "invalid secret code"
      }
    }


## Reset password by email

Generates new secret_code and sends email with link to set new password.

URL: `/api/v1/users/send_reset_password_email`

Method: `POST`

**Request**

    {
      "email": "test@test.com",
    }

**Successful response**

    HTTP status Code: 200

    {
      "status": "OK",
    }

**Failed response**

    HTTP status Code: 404

    {
      "status": "ERR",

      "error": {
          "code": 404,
          "msg" : "email not found"
      }
    }


## Set password by secret code

Sends email with link to set new password.

URL: `/api/v1/users/set_password_by_secret_code`

Method: `POST`

**Request**

    {
      "password": "new_strong_password",
      "secret_code": "asd134df"
    }

**Successful response**

    HTTP status Code: 200

    {
      "status": "OK",
    }

**Failed response**

    HTTP status Code: 405

    {
      "status": "ERR",

      "error": {
          "code": 405,
          "msg" : "invalid secret code"
      }
    }

