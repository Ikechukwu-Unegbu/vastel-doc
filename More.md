## Upload profile pics
    Method: POST
    Endpoint: domain.com/api/upload-avatar

## Update profile pics
    Method: POST
    Endpoint: domain.com/api/update-avatar

    Both endpoints have following body structure

    {
        "image":"image"
    }
    Upload as form data

#### Response
    Responses includes typical laravel validation messages.
    If everything goes well, then you can expect
    {
        "file": https://fileurl
    }


## Upgrade to Reseller
    Method: GET
    Endpoint: domain.com/api/upgrade-user

### Response
    {
        "status": true,
        "response": [],
        "message": "upgrade request successful"
    }
