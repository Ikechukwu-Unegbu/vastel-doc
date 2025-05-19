## Virtual Account Endpoint

### Fetch Banks for BVN KYC Verification
    GET /api/banks?monnify
    HTTP/1.1
    Content-Type: application/json
    Example Response : {
        "status": true,
        "response": [
            {
            "id": 1,
            "name": "Access bank",
            "code": "044",
            "ussd_template": "*901*Amount*AccountNumber#",
            "base_ussd_code": "*901#",
            "transfer_ussd_template": "*901*AccountNumber#"
            }
        ],
        "message": "Bank Codes fetched successfully"
    }

### Fetch Virtual Accounts
    GET /api/virtual-accounts HTTP/1.1
    Content-Type: application/json
    Authorization: Bearer 2|0q2K7QUbnT3TcQUMsyyRh4UASupLJl9XuKjotUqqe5b1832c
    Example Response : {
        "status": true,
        "response": []
        "message": "Virtual Account fetched successfully."
    }


### KYC verification endpoint
    Either a BVN or NIN is required.
    If a BVN is provided, then both the account number and bank code must be supplied.
    If a NIN is provided, the account number and bank code are not required.
    
    POST /api/virtual-accounts/create HTTP/1.1
    Content-Type: application/json
    Authorization: Bearer 2|0q2K7QUbnT3TcQUMsyyRh4UASupLJl9XuKjotUqqe5b1832c
    Body : {
        "bvn || nin": 22222222222,
        "account_number": 2222222222,
        "bank_code": "044"
    }
    Example Response : {
        "status": true,
        "response": []
        "message": "KYC updated & BVN linked to your account successfully."
    }
