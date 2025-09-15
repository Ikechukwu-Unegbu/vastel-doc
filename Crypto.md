# Crypto Funding Feature - ApI

## Overview
    Crypto is currently for funding on vastel.
    Currently we support only limited number of crypto currencies as follows: USDT, USDC,BTC,ETH,BNB,SOL,DOGE,TRX,XRP 
    Our provider endpoint is case sensitive and values are to be supplied in lower case except where otherwise stated.



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
                {
                    "id": "b2859a30-3821-4c3e-8d83-0cf75c0e3984",
                    "name": "Litecoin",
                    "currency": "ltc",
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
                    "created_at": "2025-09-15T21:17:09.000Z",
                    "updated_at": "2025-09-15T21:17:09.000Z",
                    "blockchain_enabled": true,
                    "default_network": "ltc",
                    "networks": [
                        {
                            "id": "ltc",
                            "name": "Litecoin Blockchain",
                            "deposits_enabled": true,
                            "withdraws_enabled": true
                        }
                    ],
                    "deposit_address": null,
                    "destination_tag": null
                },
                {
                    "id": "cc51e6e9-dc18-49f4-9c83-3ac40e1edff1",
                    "name": "Ethereum",
                    "currency": "eth",
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
                    "default_network": "erc20",
                    "networks": [
                        {
                            "id": "erc20",
                            "name": "Ethereum Network",
                            "deposits_enabled": true,
                            "withdraws_enabled": true
                        },
                        {
                            "id": "bep20",
                            "name": "Binance Smart Chain",
                            "deposits_enabled": true,
                            "withdraws_enabled": false
                        },
                        {
                            "id": "base",
                            "name": "Base Network",
                            "deposits_enabled": true,
                            "withdraws_enabled": false
                        }
                    ],
                    "deposit_address": null,
                    "destination_tag": null
                },
                {
                    "id": "67cf9607-06fe-4bdd-a2e0-bff244bc101e",
                    "name": "XRP",
                    "currency": "xrp",
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
                    "created_at": "2025-09-15T21:17:09.000Z",
                    "updated_at": "2025-09-15T21:17:09.000Z",
                    "blockchain_enabled": true,
                    "default_network": "ripple",
                    "networks": [
                        {
                            "id": "ripple",
                            "name": "Ripple Payment Network",
                            "deposits_enabled": true,
                            "withdraws_enabled": true
                        }
                    ],
                    "deposit_address": null,
                    "destination_tag": null
                },
                {
                    "id": "f8550d86-4c72-4d43-81b3-bf255f4358fb",
                    "name": "Bitcoin Cash",
                    "currency": "bch",
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
                    "created_at": "2025-09-15T21:17:09.000Z",
                    "updated_at": "2025-09-15T21:17:09.000Z",
                    "blockchain_enabled": true,
                    "default_network": "bch",
                    "networks": [
                        {
                            "id": "bch",
                            "name": "BCH Blockchain",
                            "deposits_enabled": true,
                            "withdraws_enabled": true
                        }
                    ],
                    "deposit_address": null,
                    "destination_tag": null
                },
                {
                    "id": "58dc5228-65e2-45b3-8cdd-f2c3b9b274f2",
                    "name": "USDT Tether",
                    "currency": "usdt",
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
                    "default_network": "bep20",
                    "networks": [
                        {
                            "id": "bep20",
                            "name": "Binance Smart Chain",
                            "deposits_enabled": true,
                            "withdraws_enabled": true
                        },
                        {
                            "id": "erc20",
                            "name": "Ethereum Network",
                            "deposits_enabled": true,
                            "withdraws_enabled": true
                        },
                        {
                            "id": "trc20",
                            "name": "Tron Network",
                            "deposits_enabled": true,
                            "withdraws_enabled": true
                        },
                        {
                            "id": "polygon",
                            "name": "Polygon Network",
                            "deposits_enabled": true,
                            "withdraws_enabled": true
                        },
                        {
                            "id": "solana",
                            "name": "Solana Network",
                            "deposits_enabled": true,
                            "withdraws_enabled": true
                        },
                        {
                            "id": "celo",
                            "name": "Celo Network",
                            "deposits_enabled": true,
                            "withdraws_enabled": true
                        },
                        {
                            "id": "optimism",
                            "name": "Optimism Network",
                            "deposits_enabled": true,
                            "withdraws_enabled": true
                        },
                        {
                            "id": "ton",
                            "name": "Ton Network",
                            "deposits_enabled": true,
                            "withdraws_enabled": true
                        },
                        {
                            "id": "arbitrum",
                            "name": "Arbitrum Network",
                            "deposits_enabled": true,
                            "withdraws_enabled": false
                        }
                    ],
                    "deposit_address": "0x4D1BFbaAC42C03a5A2826eb49F2Bc0577f51c3E5",
                    "destination_tag": null
                },
                {
                    "id": "801ff4da-1a64-4547-901a-2df4f43adbe7",
                    "name": "Dash",
                    "currency": "dash",
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
                    "created_at": "2025-09-15T21:17:09.000Z",
                    "updated_at": "2025-09-15T21:17:09.000Z",
                    "blockchain_enabled": true,
                    "default_network": "dash",
                    "networks": [
                        {
                            "id": "dash",
                            "name": "Dash Blockchain",
                            "deposits_enabled": true,
                            "withdraws_enabled": true
                        }
                    ],
                    "deposit_address": null,
                    "destination_tag": null
                },
                {
                    "id": "19333f1c-f6ce-437e-9ebd-9790e8e172b9",
                    "name": "Tron",
                    "currency": "trx",
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
                    "created_at": "2025-09-15T21:17:09.000Z",
                    "updated_at": "2025-09-15T21:17:09.000Z",
                    "blockchain_enabled": true,
                    "default_network": "trc20",
                    "networks": [
                        {
                            "id": "trc20",
                            "name": "Tron Network",
                            "deposits_enabled": true,
                            "withdraws_enabled": true
                        }
                    ],
                    "deposit_address": null,
                    "destination_tag": null
                },
                {
                    "id": "4ac37e65-9926-4f47-9690-3ed44d99e139",
                    "name": "Dogecoin",
                    "currency": "doge",
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
                    "created_at": "2025-09-15T21:17:09.000Z",
                    "updated_at": "2025-09-15T21:17:09.000Z",
                    "blockchain_enabled": true,
                    "default_network": "doge",
                    "networks": [
                        {
                            "id": "doge",
                            "name": "Doge Blockchain",
                            "deposits_enabled": true,
                            "withdraws_enabled": true
                        }
                    ],
                    "deposit_address": null,
                    "destination_tag": null
                },
                {
                    "id": "4acf71e5-6017-4af0-8bdf-dea2e25bfc57",
                    "name": "Binance (BEP20)",
                    "currency": "bnb",
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
                    "created_at": "2025-09-15T21:17:08.000Z",
                    "updated_at": "2025-09-15T21:17:08.000Z",
                    "blockchain_enabled": true,
                    "default_network": "bep20",
                    "networks": [
                        {
                            "id": "bep20",
                            "name": "Binance Smart Chain",
                            "deposits_enabled": true,
                            "withdraws_enabled": true
                        }
                    ],
                    "deposit_address": null,
                    "destination_tag": null
                },
                {
                    "id": "5c9a8da4-642d-4d81-9aa5-e81d8930da9f",
                    "name": "Quidax Token",
                    "currency": "qdx",
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
                    "default_network": "bep20",
                    "networks": [
                        {
                            "id": "bep20",
                            "name": "Binance Smart Chain",
                            "deposits_enabled": true,
                            "withdraws_enabled": true
                        }
                    ],
                    "deposit_address": null,
                    "destination_tag": null
                },
                {
                    "id": "a55c1d1f-361f-4841-9514-783a054ef4fa",
                    "name": "POL (ex-MATIC)",
                    "currency": "pol",
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
                    "created_at": "2025-09-15T21:17:09.000Z",
                    "updated_at": "2025-09-15T21:17:09.000Z",
                    "blockchain_enabled": true,
                    "default_network": "polygon",
                    "networks": [
                        {
                            "id": "polygon",
                            "name": "Polygon Network",
                            "deposits_enabled": true,
                            "withdraws_enabled": true
                        },
                        {
                            "id": "erc20",
                            "name": "Ethereum Network",
                            "deposits_enabled": true,
                            "withdraws_enabled": true
                        }
                    ],
                    "deposit_address": null,
                    "destination_tag": null
                },
                {
                    "id": "ab84fbc1-ceec-48c9-a5d6-80a844e3a3f7",
                    "name": "Aave",
                    "currency": "aave",
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
                    "created_at": "2025-09-15T21:17:09.000Z",
                    "updated_at": "2025-09-15T21:17:09.000Z",
                    "blockchain_enabled": true,
                    "default_network": "bep20",
                    "networks": [
                        {
                            "id": "bep20",
                            "name": "Binance Smart Chain",
                            "deposits_enabled": true,
                            "withdraws_enabled": true
                        }
                    ],
                    "deposit_address": null,
                    "destination_tag": null
                },
                {
                    "id": "6ba7b8f3-4b0f-40ee-a82f-691707c61872",
                    "name": "Shiba Inu",
                    "currency": "shib",
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
                    "created_at": "2025-09-15T21:17:09.000Z",
                    "updated_at": "2025-09-15T21:17:09.000Z",
                    "blockchain_enabled": true,
                    "default_network": "bep20",
                    "networks": [
                        {
                            "id": "erc20",
                            "name": "Ethereum Network",
                            "deposits_enabled": true,
                            "withdraws_enabled": false
                        },
                        {
                            "id": "bep20",
                            "name": "Binance Smart Chain",
                            "deposits_enabled": true,
                            "withdraws_enabled": true
                        }
                    ],
                    "deposit_address": null,
                    "destination_tag": null
                },
                {
                    "id": "a10f4e7c-85a7-47dc-b271-d90f390a6c62",
                    "name": "Polkadot",
                    "currency": "dot",
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
                    "created_at": "2025-09-15T21:17:09.000Z",
                    "updated_at": "2025-09-15T21:17:09.000Z",
                    "blockchain_enabled": true,
                    "default_network": "bep20",
                    "networks": [
                        {
                            "id": "bep20",
                            "name": "Binance Smart Chain",
                            "deposits_enabled": true,
                            "withdraws_enabled": true
                        }
                    ],
                    "deposit_address": null,
                    "destination_tag": null
                },
                {
                    "id": "53130c2a-eaab-4913-8635-4714764bf295",
                    "name": "Chainlink",
                    "currency": "link",
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
                    "created_at": "2025-09-15T21:17:09.000Z",
                    "updated_at": "2025-09-15T21:17:09.000Z",
                    "blockchain_enabled": true,
                    "default_network": "bep20",
                    "networks": [
                        {
                            "id": "bep20",
                            "name": "Binance Smart Chain",
                            "deposits_enabled": true,
                            "withdraws_enabled": true
                        }
                    ],
                    "deposit_address": null,
                    "destination_tag": null
                },
                {
                    "id": "9b45c2c7-2403-48a3-b5f4-8ca8dcb9381f",
                    "name": "Pancakeswap",
                    "currency": "cake",
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
                    "created_at": "2025-09-15T21:17:09.000Z",
                    "updated_at": "2025-09-15T21:17:09.000Z",
                    "blockchain_enabled": true,
                    "default_network": "bep20",
                    "networks": [
                        {
                            "id": "bep20",
                            "name": "Binance Smart Chain",
                            "deposits_enabled": true,
                            "withdraws_enabled": true
                        }
                    ],
                    "deposit_address": null,
                    "destination_tag": null
                },
                {
                    "id": "9d2d6135-39ff-457f-8aec-52281ac43afb",
                    "name": "Stellar",
                    "currency": "xlm",
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
                    "created_at": "2025-09-15T21:17:09.000Z",
                    "updated_at": "2025-09-15T21:17:09.000Z",
                    "blockchain_enabled": true,
                    "default_network": "stellar",
                    "networks": [
                        {
                            "id": "stellar",
                            "name": "Stellar Blockchain",
                            "deposits_enabled": true,
                            "withdraws_enabled": true
                        }
                    ],
                    "deposit_address": null,
                    "destination_tag": null
                },
                {
                    "id": "32ae8969-d71c-47be-822f-f1ef15e89123",
                    "name": "Axie Infinity",
                    "currency": "axs",
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
                    "created_at": "2025-09-15T21:17:09.000Z",
                    "updated_at": "2025-09-15T21:17:09.000Z",
                    "blockchain_enabled": true,
                    "default_network": "bep20",
                    "networks": [
                        {
                            "id": "bep20",
                            "name": "Binance Smart Chain",
                            "deposits_enabled": true,
                            "withdraws_enabled": true
                        }
                    ],
                    "deposit_address": null,
                    "destination_tag": null
                },
                {
                    "id": "ca102c45-f068-48ca-8755-66eb43c271c8",
                    "name": "Filecoin",
                    "currency": "fil",
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
                    "created_at": "2025-09-15T21:17:09.000Z",
                    "updated_at": "2025-09-15T21:17:09.000Z",
                    "blockchain_enabled": true,
                    "default_network": "bep20",
                    "networks": [
                        {
                            "id": "bep20",
                            "name": "Binance Smart Chain",
                            "deposits_enabled": true,
                            "withdraws_enabled": true
                        }
                    ],
                    "deposit_address": null,
                    "destination_tag": null
                },
                {
                    "id": "bd138e3c-caf1-4a8b-94d0-06033406cb6c",
                    "name": "Cardano",
                    "currency": "ada",
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
                    "created_at": "2025-09-15T21:17:09.000Z",
                    "updated_at": "2025-09-15T21:17:09.000Z",
                    "blockchain_enabled": true,
                    "default_network": "cardano",
                    "networks": [
                        {
                            "id": "cardano",
                            "name": "Cardano",
                            "deposits_enabled": true,
                            "withdraws_enabled": true
                        }
                    ],
                    "deposit_address": null,
                    "destination_tag": null
                },
                {
                    "id": "eca5d6ee-2719-468e-abac-4ddb1ef49e77",
                    "name": "Harmony",
                    "currency": "one",
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
                    "created_at": "2025-09-15T21:17:09.000Z",
                    "updated_at": "2025-09-15T21:17:09.000Z",
                    "blockchain_enabled": true,
                    "default_network": "bep20",
                    "networks": [
                        {
                            "id": "bep20",
                            "name": "Binance Smart Chain",
                            "deposits_enabled": true,
                            "withdraws_enabled": true
                        }
                    ],
                    "deposit_address": null,
                    "destination_tag": null
                },
                {
                    "id": "9546103d-5a61-4245-9e0f-2cbbecf42a11",
                    "name": "BabyDoge Coin",
                    "currency": "babydoge",
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
                    "created_at": "2025-09-15T21:17:09.000Z",
                    "updated_at": "2025-09-15T21:17:09.000Z",
                    "blockchain_enabled": true,
                    "default_network": "bep20",
                    "networks": [
                        {
                            "id": "bep20",
                            "name": "Binance Smart Chain",
                            "deposits_enabled": true,
                            "withdraws_enabled": true
                        }
                    ],
                    "deposit_address": null,
                    "destination_tag": null
                },
                {
                    "id": "d343d07f-dfd1-46ef-9b89-7dac39df1c7a",
                    "name": "Tezos Coin",
                    "currency": "xtz",
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
                    "created_at": "2025-09-15T21:17:09.000Z",
                    "updated_at": "2025-09-15T21:17:09.000Z",
                    "blockchain_enabled": true,
                    "default_network": "bep20",
                    "networks": [
                        {
                            "id": "bep20",
                            "name": "Binance Smart Chain",
                            "deposits_enabled": true,
                            "withdraws_enabled": true
                        }
                    ],
                    "deposit_address": null,
                    "destination_tag": null
                },
                {
                    "id": "566ab87b-b1a9-4e09-a6c0-6914686f7d0e",
                    "name": "Smooth Love Potion",
                    "currency": "slp",
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
                    "created_at": "2025-09-15T21:17:10.000Z",
                    "updated_at": "2025-09-15T21:17:10.000Z",
                    "blockchain_enabled": false,
                    "default_network": null,
                    "networks": [],
                    "deposit_address": null,
                    "destination_tag": null
                },
                {
                    "id": "011a773c-0dde-4b9d-a4ee-9f45c6bc8870",
                    "name": "SushiSwap",
                    "currency": "sushi",
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
                    "created_at": "2025-09-15T21:17:12.000Z",
                    "updated_at": "2025-09-15T21:17:12.000Z",
                    "blockchain_enabled": false,
                    "default_network": null,
                    "networks": [],
                    "deposit_address": null,
                    "destination_tag": null
                },
                {
                    "id": "9cf8a6e3-7647-41b3-87dc-34ce402628fe",
                    "name": "Zilliqa",
                    "currency": "zil",
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
                    "created_at": "2025-09-15T21:17:12.000Z",
                    "updated_at": "2025-09-15T21:17:12.000Z",
                    "blockchain_enabled": false,
                    "default_network": null,
                    "networks": [],
                    "deposit_address": null,
                    "destination_tag": null
                },
                {
                    "id": "97c88450-6aca-4884-8e1b-3ce1080bba41",
                    "name": "Floki Inu",
                    "currency": "floki",
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
                    "created_at": "2025-09-15T21:17:10.000Z",
                    "updated_at": "2025-09-15T21:17:10.000Z",
                    "blockchain_enabled": true,
                    "default_network": "bep20",
                    "networks": [
                        {
                            "id": "bep20",
                            "name": "Binance Smart Chain",
                            "deposits_enabled": true,
                            "withdraws_enabled": true
                        }
                    ],
                    "deposit_address": null,
                    "destination_tag": null
                },
                {
                    "id": "f8fed23e-6851-444e-b8f3-c466dd396d2e",
                    "name": "Solana",
                    "currency": "sol",
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
                    "created_at": "2025-09-15T21:17:10.000Z",
                    "updated_at": "2025-09-15T21:17:10.000Z",
                    "blockchain_enabled": true,
                    "default_network": "bep20",
                    "networks": [
                        {
                            "id": "solana",
                            "name": "Solana Network",
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
                {
                    "id": "171d73cb-c097-4715-9510-ecca7af7461c",
                    "name": "Decentraland",
                    "currency": "mana",
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
                    "created_at": "2025-09-15T21:17:10.000Z",
                    "updated_at": "2025-09-15T21:17:10.000Z",
                    "blockchain_enabled": false,
                    "default_network": null,
                    "networks": [],
                    "deposit_address": null,
                    "destination_tag": null
                },
                {
                    "id": "585fb3a6-3108-417c-af99-bda6ff74df83",
                    "name": "Sonic (prev. FTM)",
                    "currency": "s",
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
                    "created_at": "2025-09-15T21:17:10.000Z",
                    "updated_at": "2025-09-15T21:17:10.000Z",
                    "blockchain_enabled": false,
                    "default_network": null,
                    "networks": [],
                    "deposit_address": null,
                    "destination_tag": null
                },
                {
                    "id": "164dbe2d-4fa2-4e67-9b83-d65b0e392455",
                    "name": "The Sandbox",
                    "currency": "sand",
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
                    "created_at": "2025-09-15T21:17:10.000Z",
                    "updated_at": "2025-09-15T21:17:10.000Z",
                    "blockchain_enabled": false,
                    "default_network": null,
                    "networks": [],
                    "deposit_address": null,
                    "destination_tag": null
                },
                {
                    "id": "28630d7f-fe91-49b7-b65a-a0f42a147a6e",
                    "name": "Apecoin",
                    "currency": "ape",
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
                    "created_at": "2025-09-15T21:17:10.000Z",
                    "updated_at": "2025-09-15T21:17:10.000Z",
                    "blockchain_enabled": true,
                    "default_network": "bep20",
                    "networks": [
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
                {
                    "id": "74c26f33-5219-45a6-b5f3-bb0b7f3ddf73",
                    "name": "Enjin",
                    "currency": "enj",
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
                    "created_at": "2025-09-15T21:17:10.000Z",
                    "updated_at": "2025-09-15T21:17:10.000Z",
                    "blockchain_enabled": false,
                    "default_network": null,
                    "networks": [],
                    "deposit_address": null,
                    "destination_tag": null
                },
                {
                    "id": "da6fb573-01c0-4e06-80da-d6c76443e4ef",
                    "name": "Loopring",
                    "currency": "lrc",
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
                    "created_at": "2025-09-15T21:17:10.000Z",
                    "updated_at": "2025-09-15T21:17:10.000Z",
                    "blockchain_enabled": false,
                    "default_network": null,
                    "networks": [],
                    "deposit_address": null,
                    "destination_tag": null
                },
            
                {
                    "id": "eaab82c4-b68d-4fd5-887e-6ec6104a035d",
                    "name": "Nosana",
                    "currency": "nos",
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
                    "created_at": "2025-09-15T21:17:10.000Z",
                    "updated_at": "2025-09-15T21:17:10.000Z",
                    "blockchain_enabled": false,
                    "default_network": null,
                    "networks": [],
                    "deposit_address": null,
                    "destination_tag": null
                },
                {
                    "id": "1e30fcee-1a71-498d-96ca-3208d851dc93",
                    "name": "Jupiter",
                    "currency": "jup",
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
                    "created_at": "2025-09-15T21:17:10.000Z",
                    "updated_at": "2025-09-15T21:17:10.000Z",
                    "blockchain_enabled": false,
                    "default_network": null,
                    "networks": [],
                    "deposit_address": null,
                    "destination_tag": null
                },
                {
                    "id": "0d6a87a9-044e-43cb-b6d9-3cbc3be37961",
                    "name": "Blur",
                    "currency": "blur",
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
                    "created_at": "2025-09-15T21:17:10.000Z",
                    "updated_at": "2025-09-15T21:17:10.000Z",
                    "blockchain_enabled": false,
                    "default_network": null,
                    "networks": [],
                    "deposit_address": null,
                    "destination_tag": null
                },
                {
                    "id": "90e6279d-6836-4e58-aba1-3d4d8cd65c36",
                    "name": "Katana Inu",
                    "currency": "kata",
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
                    "created_at": "2025-09-15T21:17:11.000Z",
                    "updated_at": "2025-09-15T21:17:11.000Z",
                    "blockchain_enabled": true,
                    "default_network": "bep20",
                    "networks": [
                        {
                            "id": "bep20",
                            "name": "Binance Smart Chain",
                            "deposits_enabled": true,
                            "withdraws_enabled": true
                        }
                    ],
                    "deposit_address": null,
                    "destination_tag": null
                },
                {
                    "id": "3e00f302-9cf2-450f-92f8-90289d477962",
                    "name": "Coq Inu",
                    "currency": "coq",
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
                    "created_at": "2025-09-15T21:17:11.000Z",
                    "updated_at": "2025-09-15T21:17:11.000Z",
                    "blockchain_enabled": true,
                    "default_network": "solana",
                    "networks": [
                        {
                            "id": "avax",
                            "name": "Avalanche Network",
                            "deposits_enabled": true,
                            "withdraws_enabled": true
                        },
                        {
                            "id": "solana",
                            "name": "Solana Network",
                            "deposits_enabled": false,
                            "withdraws_enabled": false
                        }
                    ],
                    "deposit_address": null,
                    "destination_tag": null
                },
                {
                    "id": "30895cbf-be3f-424b-ab90-fa86473f28aa",
                    "name": "Wassie",
                    "currency": "wassie",
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
                    "created_at": "2025-09-15T21:17:11.000Z",
                    "updated_at": "2025-09-15T21:17:11.000Z",
                    "blockchain_enabled": true,
                    "default_network": "erc20",
                    "networks": [
                        {
                            "id": "erc20",
                            "name": "Ethereum Network",
                            "deposits_enabled": true,
                            "withdraws_enabled": true
                        }
                    ],
                    "deposit_address": null,
                    "destination_tag": null
                },
                {
                    "id": "f32a3045-4974-45dd-9b7e-0fd621e7b286",
                    "name": "Fetch.ai",
                    "currency": "fet",
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
                    "created_at": "2025-09-15T21:17:11.000Z",
                    "updated_at": "2025-09-15T21:17:11.000Z",
                    "blockchain_enabled": false,
                    "default_network": null,
                    "networks": [],
                    "deposit_address": null,
                    "destination_tag": null
                },
                {
                    "id": "362179c9-5b02-460c-a0b0-7f0a6b104b9a",
                    "name": "NEAR Protocol",
                    "currency": "near",
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
                    "created_at": "2025-09-15T21:17:11.000Z",
                    "updated_at": "2025-09-15T21:17:11.000Z",
                    "blockchain_enabled": false,
                    "default_network": null,
                    "networks": [],
                    "deposit_address": null,
                    "destination_tag": null
                },
                {
                    "id": "f8fd35b7-69f7-44ed-b1a1-2d12ecffed70",
                    "name": "Sleepless AI",
                    "currency": "ai",
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
                    "created_at": "2025-09-15T21:17:11.000Z",
                    "updated_at": "2025-09-15T21:17:11.000Z",
                    "blockchain_enabled": false,
                    "default_network": null,
                    "networks": [],
                    "deposit_address": null,
                    "destination_tag": null
                },
                {
                    "id": "e77c24c0-b91a-4633-89de-e0d463b381b8",
                    "name": "Bob",
                    "currency": "bob",
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
                    "created_at": "2025-09-15T21:17:11.000Z",
                    "updated_at": "2025-09-15T21:17:11.000Z",
                    "blockchain_enabled": false,
                    "default_network": null,
                    "networks": [],
                    "deposit_address": null,
                    "destination_tag": null
                },
                {
                    "id": "679db610-67b6-4b17-853b-4110c7b3bd9a",
                    "name": "SLERF",
                    "currency": "slerf",
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
                    "created_at": "2025-09-15T21:17:11.000Z",
                    "updated_at": "2025-09-15T21:17:11.000Z",
                    "blockchain_enabled": false,
                    "default_network": null,
                    "networks": [],
                    "deposit_address": null,
                    "destination_tag": null
                },
                {
                    "id": "5aa3071e-c4b8-4fd6-acd1-40e690068833",
                    "name": "Book Of Meme",
                    "currency": "bome",
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
                    "created_at": "2025-09-15T21:17:11.000Z",
                    "updated_at": "2025-09-15T21:17:11.000Z",
                    "blockchain_enabled": false,
                    "default_network": null,
                    "networks": [],
                    "deposit_address": null,
                    "destination_tag": null
                },
                {
                    "id": "23fc120c-be62-40d4-8c11-683b82e625c8",
                    "name": "Stacks",
                    "currency": "stx",
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
                    "created_at": "2025-09-15T21:17:11.000Z",
                    "updated_at": "2025-09-15T21:17:11.000Z",
                    "blockchain_enabled": false,
                    "default_network": null,
                    "networks": [],
                    "deposit_address": null,
                    "destination_tag": null
                },
                {
                    "id": "e4d7ce43-785d-47b3-a29c-1f525d119107",
                    "name": "Toncoin",
                    "currency": "ton",
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
                    "created_at": "2025-09-15T21:17:11.000Z",
                    "updated_at": "2025-09-15T21:17:11.000Z",
                    "blockchain_enabled": true,
                    "default_network": "ton",
                    "networks": [
                        {
                            "id": "ton",
                            "name": "Ton Network",
                            "deposits_enabled": true,
                            "withdraws_enabled": true
                        }
                    ],
                    "deposit_address": null,
                    "destination_tag": null
                },
                {
                    "id": "3a1c5d29-1871-42fb-8cb5-2297f22bc768",
                    "name": "Render",
                    "currency": "rndr",
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
                    "created_at": "2025-09-15T21:17:11.000Z",
                    "updated_at": "2025-09-15T21:17:11.000Z",
                    "blockchain_enabled": false,
                    "default_network": null,
                    "networks": [],
                    "deposit_address": null,
                    "destination_tag": null
                },
                {
                    "id": "0d108b8f-a38d-4182-8173-3a2c1a45b474",
                    "name": "MOG",
                    "currency": "mog",
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
                    "created_at": "2025-09-15T21:17:11.000Z",
                    "updated_at": "2025-09-15T21:17:11.000Z",
                    "blockchain_enabled": false,
                    "default_network": null,
                    "networks": [],
                    "deposit_address": null,
                    "destination_tag": null
                },
                {
                    "id": "3c6abe8f-56fe-43ea-94ca-162c480f550d",
                    "name": "Injective",
                    "currency": "inj",
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
                    "created_at": "2025-09-15T21:17:11.000Z",
                    "updated_at": "2025-09-15T21:17:11.000Z",
                    "blockchain_enabled": false,
                    "default_network": null,
                    "networks": [],
                    "deposit_address": null,
                    "destination_tag": null
                },
                {
                    "id": "932ea8b2-70d8-4b6f-961b-c09631958d7e",
                    "name": "Mantle",
                    "currency": "mnt",
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
                    "created_at": "2025-09-15T21:17:11.000Z",
                    "updated_at": "2025-09-15T21:17:11.000Z",
                    "blockchain_enabled": false,
                    "default_network": null,
                    "networks": [],
                    "deposit_address": null,
                    "destination_tag": null
                },
                {
                    "id": "2ba87a5f-8459-408c-a3b7-817886633b46",
                    "name": "Beam",
                    "currency": "beam",
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
                    "created_at": "2025-09-15T21:17:11.000Z",
                    "updated_at": "2025-09-15T21:17:11.000Z",
                    "blockchain_enabled": false,
                    "default_network": null,
                    "networks": [],
                    "deposit_address": null,
                    "destination_tag": null
                },
                {
                    "id": "3d905e4a-d919-4b65-bc2c-7f2fafbaf36a",
                    "name": "Starknet",
                    "currency": "strk",
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
                    "created_at": "2025-09-15T21:17:11.000Z",
                    "updated_at": "2025-09-15T21:17:11.000Z",
                    "blockchain_enabled": false,
                    "default_network": null,
                    "networks": [],
                    "deposit_address": null,
                    "destination_tag": null
                },
                {
                    "id": "91bea2f6-82f4-4e68-b77a-81d5db446ca6",
                    "name": "AVAX HAS NO CHILL",
                    "currency": "nochill",
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
                    "created_at": "2025-09-15T21:17:11.000Z",
                    "updated_at": "2025-09-15T21:17:11.000Z",
                    "blockchain_enabled": false,
                    "default_network": null,
                    "networks": [],
                    "deposit_address": null,
                    "destination_tag": null
                },
                {
                    "id": "076fd246-eeb6-41eb-a804-12fe3322ee80",
                    "name": "Cat in a Dogs World",
                    "currency": "mew",
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
                    "created_at": "2025-09-15T21:17:11.000Z",
                    "updated_at": "2025-09-15T21:17:11.000Z",
                    "blockchain_enabled": false,
                    "default_network": null,
                    "networks": [],
                    "deposit_address": null,
                    "destination_tag": null
                },
                {
                    "id": "a861e8ed-618d-4f34-a917-d38b14edb4b2",
                    "name": "Gnosis",
                    "currency": "gno",
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
                    "created_at": "2025-09-15T21:17:11.000Z",
                    "updated_at": "2025-09-15T21:17:11.000Z",
                    "blockchain_enabled": false,
                    "default_network": null,
                    "networks": [],
                    "deposit_address": null,
                    "destination_tag": null
                },
                {
                    "id": "64d4b6dd-41b6-4664-8d7b-bb81ff1579d8",
                    "name": "Waves",
                    "currency": "waves",
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
                    "created_at": "2025-09-15T21:17:11.000Z",
                    "updated_at": "2025-09-15T21:17:11.000Z",
                    "blockchain_enabled": false,
                    "default_network": null,
                    "networks": [],
                    "deposit_address": null,
                    "destination_tag": null
                },
                {
                    "id": "a9b86e52-f7c0-4627-b505-f9ff5c9f41c4",
                    "name": "XYO",
                    "currency": "xyo",
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
                    "created_at": "2025-09-15T21:17:11.000Z",
                    "updated_at": "2025-09-15T21:17:11.000Z",
                    "blockchain_enabled": false,
                    "default_network": null,
                    "networks": [],
                    "deposit_address": null,
                    "destination_tag": null
                },
                {
                    "id": "1533e307-dc76-4e49-bac3-4255a7c80bdb",
                    "name": "Official Trump",
                    "currency": "trump",
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
                    "created_at": "2025-09-15T21:17:11.000Z",
                    "updated_at": "2025-09-15T21:17:11.000Z",
                    "blockchain_enabled": false,
                    "default_network": null,
                    "networks": [],
                    "deposit_address": null,
                    "destination_tag": null
                },
                {
                    "id": "71b45728-2389-4c20-af94-c46742a3ef1e",
                    "name": "Compliant Nigerian Naira",
                    "currency": "cngn",
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
                    "created_at": "2025-09-15T21:17:12.000Z",
                    "updated_at": "2025-09-15T21:17:12.000Z",
                    "blockchain_enabled": true,
                    "default_network": "bep20",
                    "networks": [
                        {
                            "id": "bep20",
                            "name": "Binance Smart Chain",
                            "deposits_enabled": true,
                            "withdraws_enabled": true
                        }
                    ],
                    "deposit_address": null,
                    "destination_tag": null
                },
                {
                    "id": "1fdbfa71-4625-4f35-ae37-959e74d044fa",
                    "name": "Fartcoin",
                    "currency": "fartcoin",
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
                    "created_at": "2025-09-15T21:17:12.000Z",
                    "updated_at": "2025-09-15T21:17:12.000Z",
                    "blockchain_enabled": false,
                    "default_network": null,
                    "networks": [],
                    "deposit_address": null,
                    "destination_tag": null
                },
                {
                    "id": "5e13e691-1323-420b-ae9b-5e342f48e11d",
                    "name": "Peanut the Squirrel",
                    "currency": "pnut",
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
                    "created_at": "2025-09-15T21:17:12.000Z",
                    "updated_at": "2025-09-15T21:17:12.000Z",
                    "blockchain_enabled": false,
                    "default_network": null,
                    "networks": [],
                    "deposit_address": null,
                    "destination_tag": null
                },
                {
                    "id": "ea3526c4-bbbb-4840-8dcd-0e51b1e7512c",
                    "name": "HyperLiquid",
                    "currency": "hype",
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
                    "created_at": "2025-09-15T21:17:08.000Z",
                    "updated_at": "2025-09-15T21:17:08.000Z",
                    "blockchain_enabled": true,
                    "default_network": "erc20",
                    "networks": [
                        {
                            "id": "erc20",
                            "name": "Ethereum Network",
                            "deposits_enabled": true,
                            "withdraws_enabled": true
                        }
                    ],
                    "deposit_address": null,
                    "destination_tag": null
                }
            ]
        },
        "message": "Request successful"
    }