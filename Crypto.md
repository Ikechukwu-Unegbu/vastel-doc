# Crypto Funding Feature - ApI

## Overview
    Crypto is currently for funding on vastel.
    Currently we support only limited number of crypto currencies as follows: USDT, USDC,BTC,ETH,BNB,SOL,DOGE,TRX,XRP 
    Our provider endpoint is case sensitive and values are to be supplied in lower case except where otherwise stated.


## Exchange rates api for each of the allowed coins

    Method: POST
    Endpoint: domain/api/quidax/temporary-swap
## Response    
    {
        "status": "success",
        "data": {
            "usdt": {
                "status": "success",
                "message": "Successful",
                "data": {
                    "from_currency": "USDT",
                    "to_currency": "NGN",
                    "from_amount": "1.0",
                    "to_amount": "1490.86",
                    "quoted_price": "1490.8623",
                    "quoted_currency": "NGN"
                }
            },
            "usdc": {
                "status": "success",
                "message": "Successful",
                "data": {
                    "from_currency": "USDC",
                    "to_currency": "NGN",
                    "from_amount": "1.0",
                    "to_amount": "1475.35",
                    "quoted_price": "1475.3573926556175",
                    "quoted_currency": "NGN"
                }
            },
            "btc": {
                "status": "success",
                "message": "Successful",
                "data": {
                    "from_currency": "BTC",
                    "to_currency": "NGN",
                    "from_amount": "1.0",
                    "to_amount": "163618941.0",
                    "quoted_price": "163618941.92",
                    "quoted_currency": "NGN"
                }
            },
            "eth": {
                "status": "success",
                "message": "Successful",
                "data": {
                    "from_currency": "ETH",
                    "to_currency": "NGN",
                    "from_amount": "1.0",
                    "to_amount": "5855439.0",
                    "quoted_price": "5855439.24",
                    "quoted_currency": "NGN"
                }
            },
            "bnb": {
                "status": "success",
                "message": "Successful",
                "data": {
                    "from_currency": "BNB",
                    "to_currency": "NGN",
                    "from_amount": "1.0",
                    "to_amount": "1458966.17",
                    "quoted_price": "1458966.1734999",
                    "quoted_currency": "NGN"
                }
            },
            "sol": {
                "status": "success",
                "message": "Successful",
                "data": {
                    "from_currency": "SOL",
                    "to_currency": "NGN",
                    "from_amount": "1.0",
                    "to_amount": "294982.87",
                    "quoted_price": "294982.877346498",
                    "quoted_currency": "NGN"
                }
            },
            "doge": null,
            "trx": null,
            "xrp": {
                "status": "success",
                "message": "Successful",
                "data": {
                    "from_currency": "XRP",
                    "to_currency": "NGN",
                    "from_amount": "1.0",
                    "to_amount": "4148.5",
                    "quoted_price": "4148.5066",
                    "quoted_currency": "NGN"
                }
            }
        }
    }


## User account creation
    We can set account for every user on Quidax via backend command or we can create account for users only when they need crypto service. I prefer the later unless there is strong argument for the former.


    So when a user navigate to crypto funding, mobile app can start by checking if the user already has quidax id, if not, call user account creation endpoint

    Method: POST
    Endpoint: domain/api/quidax/users/create

### Failure Response 
    {
        "status": false,
        "errors": [],
        "message": "Failed to create User"
    }


### Success Response
    Be aware of Quidax pa
    {
        "status": true,
        "response": {
            "status": "success",
            "message": "Successful",
            "data": {
                "id": "3477b1d5-4cb3-4b03-96f5-8fb3c6b5e743",
                "sn": "QDXH3MCY3JS",
                "email": "alyson.pagac@example.org",
                "reference": null,
                "first_name": "Mr.",
                "last_name": "Norbert",
                "display_name": null,
                "created_at": "2025-09-15T21:11:40.754Z",
                "updated_at": "2025-09-15T21:11:40.959Z"
            }
        },
        "message": "Request successful"
    }


## Generate a Payment address for the user
    A fresh user on quidax by default has no wallet address. Now the user can generate wallet for the user
    Wallet generation is handled in the background. So when call to wallet generation endpoint is successful,
    you only get success response but not the wallet. You wont recieve any wallet to display.

    GET call
    Endpoint: domain/api/quidax/wallets-generate/usdt?network=bep20
### Failure Response 
    {
        "status": false,
        "errors": [],
        "message": "API request failed"
    }

### Success Response 

    {
        "status": true,
        "response": {
            "status": "success",
            "message": "Successful",
            "data": {
                "id": "8c6fe6d1-ce51-4c48-9796-9d14adefef3a",
                "reference": null,
                "currency": "usdt",
                "address": null,
                "network": "bep20",
                "user": {
                    "id": "3477b1d5-4cb3-4b03-96f5-8fb3c6b5e743",
                    "sn": "QDXH3MCY3JS",
                    "email": "alyson.pagac@example.org",
                    "reference": null,
                    "first_name": "Mr.",
                    "last_name": "Norbert",
                    "display_name": null,
                    "created_at": "2025-09-15T21:11:40.000Z",
                    "updated_at": "2025-09-15T21:11:40.000Z"
                },
                "destination_tag": null,
                "total_payments": null,
                "created_at": "2025-09-15T21:16:01.874Z",
                "updated_at": "2025-09-15T21:16:01.874Z"
            }
        },
        "message": "Request successful"
    }



## Fetch All Wallets of Given User
    Bear in mind that this is direct quidax response. Filter it for the wallets we issue.


### Success Response 
    GET call
    Endpoint: domain/api/quidax/wallets

    {
        "status": true,
        "response": {
            "status": "success",
            "message": "Successful",
            "data": [
                {
                    "id": "f8f05b43-7b5c-4837-8f2e-2df3596c64f1",
                    "name": "US Dollar",
                    "currency": "usd",
                    "balance": "0.0",
                    "locked": "0.0",
                    "staked": "0.0",
                    "user": {
                        "id": "3477b1d5-4cb3-4b03-96f5-8fb3c6b5e743",
                        "sn": "QDXH3MCY3JS",
                        "email": "alyson.pagac@example.org",
                        "reference": null,
                        "first_name": "Mr.",
                        "last_name": "Norbert",
                        "display_name": null,
                        "created_at": "2025-09-15T21:11:40.000Z",
                        "updated_at": "2025-09-15T21:11:40.000Z"
                    },
                    "converted_balance": "0.0",
                    "reference_currency": "ngn",
                    "is_crypto": false,
                    "created_at": "2025-09-15T21:11:40.000Z",
                    "updated_at": "2025-09-15T21:11:40.000Z",
                    "blockchain_enabled": false,
                    "default_network": null,
                    "networks": [],
                    "deposit_address": null,
                    "destination_tag": null
                },
                {
                    "id": "92c2f088-e9a0-444e-85be-0780e2ade707",
                    "name": "Naira",
                    "currency": "ngn",
                    "balance": "0.0",
                    "locked": "0.0",
                    "staked": "0.0",
                    "user": {
                        "id": "3477b1d5-4cb3-4b03-96f5-8fb3c6b5e743",
                        "sn": "QDXH3MCY3JS",
                        "email": "alyson.pagac@example.org",
                        "reference": null,
                        "first_name": "Mr.",
                        "last_name": "Norbert",
                        "display_name": null,
                        "created_at": "2025-09-15T21:11:40.000Z",
                        "updated_at": "2025-09-15T21:11:40.000Z"
                    },
                    "converted_balance": "0.0",
                    "reference_currency": "ngn",
                    "is_crypto": false,
                    "created_at": "2025-09-15T21:11:40.000Z",
                    "updated_at": "2025-09-15T21:11:40.000Z",
                    "blockchain_enabled": false,
                    "default_network": null,
                    "networks": [],
                    "deposit_address": null,
                    "destination_tag": null
                },
                {
                    "id": "143d8a25-197a-44d4-ae5d-c30bf6951e87",
                    "name": "Bitcoin",
                    "currency": "btc",
                    "balance": "0.0",
                    "locked": "0.0",
                    "staked": "0.0",
                    "user": {
                        "id": "3477b1d5-4cb3-4b03-96f5-8fb3c6b5e743",
                        "sn": "QDXH3MCY3JS",
                        "email": "alyson.pagac@example.org",
                        "reference": null,
                        "first_name": "Mr.",
                        "last_name": "Norbert",
                        "display_name": null,
                        "created_at": "2025-09-15T21:11:40.000Z",
                        "updated_at": "2025-09-15T21:11:40.000Z"
                    },
                    "converted_balance": "0.0",
                    "reference_currency": "ngn",
                    "is_crypto": true,
                    "created_at": "2025-09-15T21:11:40.000Z",
                    "updated_at": "2025-09-15T21:11:40.000Z",
                    "blockchain_enabled": true,
                    "default_network": "btc",
                    "networks": [
                        {
                            "id": "btc",
                            "name": "Bitcoin",
                            "deposits_enabled": true,
                            "withdraws_enabled": true
                        },
                        {
                            "id": "bep20",
                            "name": "Binance Smart Chain",
                            "deposits_enabled": true,
                            "withdraws_enabled": false
                        }
                    ],
                    "deposit_address": null,
                    "destination_tag": null
                },
            ]
        },
        "message": "Request successful"
    }
