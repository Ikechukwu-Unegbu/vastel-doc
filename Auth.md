
# VasTel API Documentation for Mobile APP

### Account Creation API 
    Method: POST
    Endpoint: domain/api/register
    Body:
        {
            "name":"Ikechukwu Vin API",
            "username":"Ikeapi2",
            "phone":"08064133376",
            "email":"apiike2@gmail.com", 
            "password":"password", 
            "password_confirmation":"password"
        }

#### Success Response 
    Response:  
        {
            "message": "Account Created.",
            "status": "success",
            "user": {
                "name": "Ikechukwu Vin API",
                "username": "Ikeapi2",
                "email": "apiike2@gmail.com",
                "role": "user",
                "updated_at": "2024-04-13T18:48:54.000000Z",
                "created_at": "2024-04-13T18:48:54.000000Z",
                "id": 5
            }
        }
 NB: This now returns the new user's virtual accounts

#### Failure Response
    {
        "message": "The username field is required. (and 1 more error)",
        "errors": {
            "username": [
                "The username field is required."
            ],
            "email": [
                "The email field is required."
            ]
        }
    }


## Login Endpoint
    Method: POST
    Endpoint: domain.com/api/login
    Body:
    {
        "email":"apiike2@gmail.com",
        "password":"password"
    }

#### Success Response
    Response:  
        {
            "\r\n                token": "1|qlNlkUGLaUcKGARvrNcOJb8HNcKvInY6ynNQbsIJb634a4f6",
            "status": "success",
            "user": {
                "id": 5,
                "name": "Ikechukwu Vin API",
                "username": "Ikeapi2",
                "email": "apiike2@gmail.com",
                "role": "user",
                "email_verified_at": null,
                "image": null,
                "address": null,
                "mobile": null,
                "referer_username": null,
                "gender": null,
                "account_balance": "0.00",
                "wallet_balance": "0.00",
                "bonus_balance": "0.00",
                "created_at": "2024-04-13T18:48:54.000000Z",
                "updated_at": "2024-04-13T18:48:54.000000Z",
                "phone": null
            }
        }

#### Failure Response 
        Response: {
            "message": "The password field is required.",
            "errors": {
                "password": [
                    "The password field is required."
                ]
            }
    }

## Logout Endpoint
    Method: POST
    Endpoint: domain.com/api/logout
    This is authenticated endpoint


## Forgot Password
    This endpoint is email sending and takes time - so implement loading spinner. 

    Method: POST
    Endpoint: domain.com/api/forgot-password
    Body:
    {
        "email":"iunegbu94@yahoo.com"
    }

#### Success Response
    {
        "status":"success"
        "message": "We have emailed your password reset link."
    }
#### Failure Response 
    {
        "status":"failed", 
        "error": {
            "email": [
                "The email field must be a valid email address."
            ]
        }
    }

## Change Password
    Method: Post
    Endpoint: domain.com/api/change-password/
    
    Body: 
    {
        "current_password":"password", 
        "new_password":"updated_password", 
        "confirm_password":"updated_password3"
    }

#### Failure Response 
    {
        "message": "The confirm password field must match new password.",
        "errors": {
            "confirm_password": [
                "The confirm password field must match new password."
            ]
        }
    }

#### Success Response
    {
        "message": "Password updated successfully",
        "status": "success"
    }

## View Profile Settings 
    Method: GET
    Endpoint: domain.com/api/user/{username/email}

#### Response 
    {
        "id": 5,
        "name": "Ikechukwu Vin API",
        "username": "Ikeapi2",
        "email": "apiike2@gmail.com",
        "role": "user",
        "email_verified_at": null,
        "image": null,
        "address": null,
        "mobile": null,
        "referer_username": null,
        "gender": null,
        "account_balance": "0.00",
        "wallet_balance": "0.00",
        "bonus_balance": "0.00",
        "created_at": "2024-04-13T18:48:54.000000Z",
        "updated_at": "2024-04-14T16:31:52.000000Z",
        "phone": null
    }


## Update Profile
    Method: post
    URL: /api/user
### Request Body
    {
        "name":"updated ikechukwu",
        "phone":"080747777777",
        "username":"updated_vincent"
    }

    Please concatnate first and second name into one.

### Failure response
    You can expect typical laravel validation error
    


# OTP 
    Email should be submitted as hidden field.

## Resend OTP
    Method: POST
    Endpoint: domain.com/api/resend-otp
    This is un-authenticated endpoint

### Body

    {
        "email":"postranet@gmail.com"
    }

### Success Response
    {
        "status": "success",
        "0": "New OTP sent"
    }

## Verify OTP
    Method: POST
    Endpoint: domain.com/api/verify-otp
    This is un-authenticated endpoint

### Body
    {
        "otp":"GHO2", 
        "email":"postranet@gmail.com"
    }

### Failure Response - ERROR Code 403
    {
        "status": "failed",
        "message": "Invalid otp"
    }

    or you can see
    {
        "message": "The otp field is required.",
        "errors": {
            "otp": [
                "The otp field is required."
            ]
        }
    }

### Failure Response - Code 200

    {
        "status": "success",
        "message": "Valid otp"
    }



## User PIN Endpoint

    -- Creating New PIN

    POST /api/pin/create HTTP/1.1
    Content-Type: application/json
    Authorization: Bearer 2|0q2K7QUbnT3TcQUMsyyRh4UASupLJl9XuKjotUqqe5b1832c
    Body : {
        "pin": 1234,
        "pin_confirmation": 1234
    }

    Validation Response : {
        "errors": {
            "pin": [
                "The pin field is required.",
                "The pin field must be 4 digits."
            ],
            "pin_confirmation": [
                "The pin confirmation field is required.",
                "The pin confirmation field must match pin."
            ]
        }
    }

    Example Response : {
        "status": true,
        "error": null,
        "message": "PIN created successfully."
    }

    -- Updating Pin

    POST /api/pin/update HTTP/1.1
    Content-Type: application/json
    Authorization: Bearer 2|0q2K7QUbnT3TcQUMsyyRh4UASupLJl9XuKjotUqqe5b1832c
    Body : {
        "current_pin": 1234,
        "pin": 1234,
        "pin_confirmation": 1234
    }

    Validation Response : {
        "message": "The current pin field is required. (and 2 more errors)",
        "errors": {
            "current_pin": [
                "The current pin field is required.",
                "The current pin field must be 4 digits.",
                "The current PIN is incorrect."
            ],
            "pin": [
                "The pin field is required.",
                "The pin field must be 4 digits."
            ],
            "pin_confirmation": [
                "The pin confirmation field is required.",
                "The pin confirmation field must match pin."
            ]
        }
    }

    Example Response : {
        "status": true,
        "error": null,
        "message": "PIN updated successfully."
    }


    -- Validating Pin on every transaction
    POST /api/pin/validate HTTP/1.1
    Content-Type: application/json
    Authorization: Bearer 2|0q2K7QUbnT3TcQUMsyyRh4UASupLJl9XuKjotUqqe5b1832c
    Body : {
        "pin": 1234
    }

    Validation Response : {
        "message": "The pin field is required",
        "errors": {
            "pin": [
                "The pin field is required.",
                "The pin field must be 4 digits.",
                "The PIN provided is incorrect. Provide a valid PIN."
            ]
        }
    }

    Example Response : {
        "status": true,
        "message": "PIN validated successfully."
    }
