
## Money Transfer (Bank) Endpoint

## Fetch Bank List
     GET /api/bank-list HTTP/1.1
    Content-Type: application/json
    Example Response : {
        "status": true,
        "response": [
             {
                "id": 384,
                "name": "opay",
                "code": "000000",
                "image": "image.png"
            }
        ],
        "message": "Banks fetched successfully"
    }
    
## Query Account Number
    POST /api/bank/query-account-number HTTP/1.1
    Content-Type: application/json
    Authorization: Bearer 2|0q2K7QUbnT3TcQUMsyyRh4UASupLJl9XuKjotUqqe5b1832c
    Body : {
        "account_number": 2222222222,
        "bank_code": "000000"
    }
    Example Response : {
        "status": true,
        "response": {
            "Status": "Success",
            "accountName": "Vastel V"
        },
        "message": "Account verified successfully."
    }
    
## Process Payment
    POST /api/bank/process-transaction HTTP/1.1
    Content-Type: application/json
    Authorization: Bearer 2|0q2K7QUbnT3TcQUMsyyRh4UASupLJl9XuKjotUqqe5b1832c
     Body : {
        "account_number": 2222222222,
        "bank_code": "000000",
        "account_name": "Vastel V",
        "amount": 100,
        "remark": ""

    }
    Example Response : {
        "status": true,
        "response": {
           "trx_ref": "VST|9|20250403155531|GN9RO3",
            "amount": "1000",
            "account_number": "2222222222",
        },
        "message": "Bank transfer successfully initiated."
    }
