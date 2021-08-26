# Authentication

Evis.Market user registration API documentation.


## Registration by email or phone

URL: `/api/v1/users/signup`

Method: `POST`

**Request**

    {
      "first_name": "Evgeny",
      "last_name": "Mamonov",
      "phone": "79885762574",
      "email:" "evgeny@mamonov.org",
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
