# Seller products management

Evis.Market seller products management API documentation.

This service available for authenticated seller only.

Table of Contents
=================
* [Get File](#get-file)
* [Upload File](#upload-file)

## Get File

URL: `/api/v1/upload/:uuid`

Method: `GET`

**Successful response**

    HTTP status Code: 200

    {
        "uploaded_file": {
            "file_url": "/media/uploaded_files_tmp/247ad31c927149ca940a13017f755fd9.pdf",
            "created_by": 1,
            "created_at": "2021-10-26T21:20:55.891438Z",
            "updated_at": "2021-10-26T21:20:55.891534Z",
            "file_name_original": "2_5330012327951470428.pdf"
        },
        "status": "OK"
    }

**Failed response**

    HTTP status Code: 404

    {
        "status": "ERR",
        "error": {
            "code": 404,
            "msg": "File does not exist or you do not have access permissions to it"
        }
    }


## Upload File

URL: `/api/v1/upload/`

Content-type: `multipart/form-data`

Method: `POST`

**Request**

    {
        "file": "upload_file_here"
    }

**Successful response**

    HTTP status Code: 200

    {
        "uuid": "1170a5f8-b9d3-4742-adda-eba3f4e08be6",
        "status": "OK"
    }

**Failed response**

    HTTP status Code: 400
    
    {
        "status": "ERR",
        "error": {
            "code": 400,
            "msg": "bad request",
            "invalid_fields": {
                "file": "No file was submitted."
            }
        }
    }

    HTTP status Code: 400
    {
        "status": "ERR",
        "error": {
            "code": 400,
            "msg": "bad request",
            "invalid_fields": {
                "file": "The submitted data was not a file. Check the encoding type on the form."
            }
        }
    }