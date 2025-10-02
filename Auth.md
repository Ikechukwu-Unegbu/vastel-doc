
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
            "password_confirmation":"password",
             "os_player_id": "0000-player-id-0000"
        }

#### Success Response 
    Response:  
       {
            "message": "Account Created.",
            "status": "success",
            "user": {
                "id": 58,
                "name": null,
                "username": "ituadeskkkdsss",
                "email": "notexist@gmail.com",
                "role": "user",
                "user_level": "ordinary",
                "email_verified_at": null,
                "image": null,
                "address": null,
                "mobile": null,
                "referer_username": null,
                "gender": null,
                "account_balance": "0.00",
                "single_transfer_limit": null,
                "daily_transfer_limit": null,
                "wallet_balance": "0.00",
                "bonus_balance": "0.00",
                "bvn": null,
                "nin": null,
                "created_at": "2025-10-02T00:32:05.000000Z",
                "updated_at": "2025-10-02T00:32:05.000000Z",
                "phone": null,
                "deactivation": 0,
                "blocked_by_admin": 0,
                "admin_block_reason": null,
                "deleted_at": null,
                "soft_deleted_by": null,
                "blocked_by": null,
                "os_player_id": null,
                "device_type": null,
                "is_admin": 0,
                "kyc_name": null,
                "is_flagged": 0,
                "post_no_debit": 0,
                "is_blacklisted": 0,
                "is_kyc_check": 0,
                "flagged_by_admin_id": null,
                "flagged_at": null,
                "post_no_debit_by_admin_id": null,
                "post_no_debit_at": null,
                "blacklisted_by_admin_id": null,
                "blacklisted_at": null,
                "referral_link": null,
                "date_of_birth": null,
                "house_number": null,
                "street_address": null,
                "local_government": null,
                "area_code": null,
                "city": null,
                "state": null,
                "next_of_kin_relationship": null,
                "next_of_kin_first_name": null,
                "next_of_kin_last_name": null,
                "next_of_kin_email": null,
                "next_of_kin_phone": null,
                "next_of_kin_gender": null,
                "utility_bill_type": null,
                "utility_bill_path": null,
                "government_id_type": null,
                "government_id_path": null,
                "tier_1_completed": 0,
                "tier_1_completed_at": null,
                "tier_2_completed": 0,
                "tier_2_completed_at": null,
                "tier_3_completed": 0,
                "tier_3_completed_at": null,
                "kyc_completed": 0,
                "kyc_completed_at": null,
                "quidax_id": null,
                "quidax_sn": null,
                "quidax_display_name": null,
                "quidax_reference": null,
                "quidax_created_at": null,
                "quidax_updated_at": null,
                "crypto_wallets": [
                    {
                        "id": 89,
                        "balance": "0.00",
                        "currency": "ngn",
                        "wallet_type": "crypto_base",
                        "user_id": 58,
                        "created_at": "2025-10-02T00:32:05.000000Z",
                        "updated_at": "2025-10-02T00:32:05.000000Z"
                    }
                ]
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
        "password":"password",
         "os_player_id": "0000-player-id-0000"
    }

#### Success Response
    Response:  
        {
            "token": "270|e1WAXlpDpFhbnIOUVSZl4gAv6HLQCbdL9j0EdMjMf90b93a8",
            "status": "success",
            "user": {
                "id": 6,
                "name": "Ikechukwu Vincent",
                "username": "Unegbu",
                "email": "ikunegbu@ebsafr.com",
                "role": "superadmin",
                "user_level": "ordinary",
                "email_verified_at": null,
                "image": null,
                "address": null,
                "mobile": null,
                "referer_username": null,
                "gender": null,
                "account_balance": "493.00",
                "single_transfer_limit": null,
                "daily_transfer_limit": null,
                "wallet_balance": "0.00",
                "bonus_balance": "0.00",
                "bvn": "22222470261",
                "nin": null,
                "created_at": "2024-05-07T21:30:09.000000Z",
                "updated_at": "2025-09-04T10:19:12.000000Z",
                "phone": null,
                "deactivation": 0,
                "blocked_by_admin": 0,
                "admin_block_reason": null,
                "deleted_at": null,
                "soft_deleted_by": null,
                "blocked_by": null,
                "os_player_id": null,
                "device_type": null,
                "is_admin": 0,
                "kyc_name": null,
                "is_flagged": 0,
                "post_no_debit": 0,
                "is_blacklisted": 0,
                "is_kyc_check": 0,
                "flagged_by_admin_id": null,
                "flagged_at": null,
                "post_no_debit_by_admin_id": null,
                "post_no_debit_at": null,
                "blacklisted_by_admin_id": null,
                "blacklisted_at": null,
                "referral_link": null,
                "date_of_birth": null,
                "house_number": null,
                "street_address": null,
                "local_government": null,
                "area_code": null,
                "city": null,
                "state": null,
                "next_of_kin_relationship": null,
                "next_of_kin_first_name": null,
                "next_of_kin_last_name": null,
                "next_of_kin_email": null,
                "next_of_kin_phone": null,
                "next_of_kin_gender": null,
                "utility_bill_type": null,
                "utility_bill_path": null,
                "government_id_type": null,
                "government_id_path": null,
                "tier_1_completed": 0,
                "tier_1_completed_at": null,
                "tier_2_completed": 0,
                "tier_2_completed_at": null,
                "tier_3_completed": 0,
                "tier_3_completed_at": null,
                "kyc_completed": 0,
                "kyc_completed_at": null,
                "quidax_id": "f723ef71-d748-4a54-bcf5-b1a6f0de2453",
                "quidax_sn": "QDXO2VRBQWM",
                "quidax_display_name": null,
                "quidax_reference": null,
                "quidax_created_at": "2025-09-04T10:19:12.065Z",
                "quidax_updated_at": "2025-09-04T10:19:12.371Z",
                "virtual_accounts": [
                    {
                        "id": 14,
                        "payment_id": 3,
                        "user_id": 6,
                        "reference": "QTb6OwPflf8liRB",
                        "bank_code": "50515",
                        "bank_name": "Moniepoint Microfinance Bank",
                        "account_name": "IKE",
                        "account_number": "6991796659",
                        "account_type": null,
                        "bvn": null,
                        "nin": null,
                        "reservation_reference": "10GARYY1RXBMJ3503695",
                        "reserved_account_type": "GENERAL",
                        "restrict_payment_source": "0",
                        "collection_channel": "RESERVED_ACCOUNT",
                        "status": "ACTIVE",
                        "created_on": "2025-02-27 14:38:17.044",
                        "created_at": "2025-02-27T13:38:17.000000Z",
                        "updated_at": "2025-02-27T13:38:17.000000Z",
                        "deleted_at": null
                    },
                    {
                        "id": 15,
                        "payment_id": 5,
                        "user_id": 6,
                        "reference": "wnntou4H8Svvix7NIqOiKEEwu",
                        "bank_code": "100033",
                        "bank_name": "PalmPay",
                        "account_name": "Ikechukwu Vincent(VASTEL)",
                        "account_number": "6657667943",
                        "account_type": "personal",
                        "bvn": null,
                        "nin": null,
                        "reservation_reference": "L250127152998844389761",
                        "reserved_account_type": null,
                        "restrict_payment_source": null,
                        "collection_channel": null,
                        "status": "ACTIVE",
                        "created_on": null,
                        "created_at": "2025-02-27T13:38:17.000000Z",
                        "updated_at": "2025-02-27T13:38:17.000000Z",
                        "deleted_at": null
                    }
                ],
                "crypto_wallets": [
                    {
                        "id": 73,
                        "balance": "14683.14",
                        "currency": "usdt",
                        "wallet_type": "crypto_base",
                        "user_id": 6,
                        "created_at": "2025-09-18T22:18:14.000000Z",
                        "updated_at": "2025-10-01T19:02:29.000000Z"
                    }
                ]
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
        "status": true,
        "response": {
            "id": 6,
            "name": "Ikechukwu Vincent",
            "username": "Unegbu",
            "email": "ikunegbu@ebsafr.com",
            "role": "superadmin",
            "user_level": "ordinary",
            "email_verified_at": null,
            "image": null,
            "address": null,
            "mobile": null,
            "referer_username": null,
            "gender": null,
            "account_balance": "493.00",
            "single_transfer_limit": null,
            "daily_transfer_limit": null,
            "wallet_balance": "0.00",
            "bonus_balance": "0.00",
            "bvn": "22222470261",
            "nin": null,
            "created_at": "2024-05-07T21:30:09.000000Z",
            "updated_at": "2025-09-04T10:19:12.000000Z",
            "phone": null,
            "deactivation": 0,
            "blocked_by_admin": 0,
            "admin_block_reason": null,
            "deleted_at": null,
            "soft_deleted_by": null,
            "blocked_by": null,
            "os_player_id": null,
            "device_type": null,
            "is_admin": 0,
            "kyc_name": null,
            "is_flagged": 0,
            "post_no_debit": 0,
            "is_blacklisted": 0,
            "is_kyc_check": 0,
            "flagged_by_admin_id": null,
            "flagged_at": null,
            "post_no_debit_by_admin_id": null,
            "post_no_debit_at": null,
            "blacklisted_by_admin_id": null,
            "blacklisted_at": null,
            "referral_link": null,
            "date_of_birth": null,
            "house_number": null,
            "street_address": null,
            "local_government": null,
            "area_code": null,
            "city": null,
            "state": null,
            "next_of_kin_relationship": null,
            "next_of_kin_first_name": null,
            "next_of_kin_last_name": null,
            "next_of_kin_email": null,
            "next_of_kin_phone": null,
            "next_of_kin_gender": null,
            "utility_bill_type": null,
            "utility_bill_path": null,
            "government_id_type": null,
            "government_id_path": null,
            "tier_1_completed": 0,
            "tier_1_completed_at": null,
            "tier_2_completed": 0,
            "tier_2_completed_at": null,
            "tier_3_completed": 0,
            "tier_3_completed_at": null,
            "kyc_completed": 0,
            "kyc_completed_at": null,
            "quidax_id": "f723ef71-d748-4a54-bcf5-b1a6f0de2453",
            "quidax_sn": "QDXO2VRBQWM",
            "quidax_display_name": null,
            "quidax_reference": null,
            "quidax_created_at": "2025-09-04T10:19:12.065Z",
            "quidax_updated_at": "2025-09-04T10:19:12.371Z",
            "virtual_accounts": [
                {
                    "id": 14,
                    "payment_id": 3,
                    "user_id": 6,
                    "reference": "QTb6OwPflf8liRB",
                    "bank_code": "50515",
                    "bank_name": "Moniepoint Microfinance Bank",
                    "account_name": "IKE",
                    "account_number": "6991796659",
                    "account_type": null,
                    "bvn": null,
                    "nin": null,
                    "reservation_reference": "10GARYY1RXBMJ3503695",
                    "reserved_account_type": "GENERAL",
                    "restrict_payment_source": "0",
                    "collection_channel": "RESERVED_ACCOUNT",
                    "status": "ACTIVE",
                    "created_on": "2025-02-27 14:38:17.044",
                    "created_at": "2025-02-27T13:38:17.000000Z",
                    "updated_at": "2025-02-27T13:38:17.000000Z",
                    "deleted_at": null
                },
                {
                    "id": 15,
                    "payment_id": 5,
                    "user_id": 6,
                    "reference": "wnntou4H8Svvix7NIqOiKEEwu",
                    "bank_code": "100033",
                    "bank_name": "PalmPay",
                    "account_name": "Ikechukwu Vincent(VASTEL)",
                    "account_number": "6657667943",
                    "account_type": "personal",
                    "bvn": null,
                    "nin": null,
                    "reservation_reference": "L250127152998844389761",
                    "reserved_account_type": null,
                    "restrict_payment_source": null,
                    "collection_channel": null,
                    "status": "ACTIVE",
                    "created_on": null,
                    "created_at": "2025-02-27T13:38:17.000000Z",
                    "updated_at": "2025-02-27T13:38:17.000000Z",
                    "deleted_at": null
                }
            ],
            "crypto_wallets": [
                {
                    "id": 73,
                    "balance": "14683.14",
                    "currency": "usdt",
                    "wallet_type": "crypto_base",
                    "user_id": 6,
                    "created_at": "2025-09-18T22:18:14.000000Z",
                    "updated_at": "2025-10-01T19:02:29.000000Z"
                }
            ]
        },
        "message": "User exists"
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
