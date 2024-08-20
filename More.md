## Upload profile pics
    Method: POST
    Endpoint: domain.com/api/upload-avatar

## Update profile pics
    Method: POST
    Endpoint: domain.com/api/upload-avatar

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


## Fetch all of a user transactions
    Method: GET
    Endpoint: domain.com/api/transactions?page=pagenumber

### Response 
    [
        [
            {
            "transaction_id": "202408072201-electricity-1zcsmuc0rl013877900-1723064491p6mc",
            "status": 1,
            "amount": "370.26",
            "created_at": "2024-08-07T21:01:31.000000Z",
            "model_source": "ElectricityTransaction"
            },
            {
            "transaction_id": "202408072201-electricity-nuqojiqrc5023466300-1723064491yebe",
            "status": 0,
            "amount": "924.62",
            "created_at": "2024-08-07T21:01:31.000000Z",
            "model_source": "ElectricityTransaction"
            },
            {
            "transaction_id": "202408072201-electricity-csvgkfgn2g028999200-1723064491hsih",
            "status": 0,
            "amount": "888.79",
            "created_at": "2024-08-07T21:01:31.000000Z",
            "model_source": "ElectricityTransaction"
            },
            {
            "transaction_id": "202408072201-electricity-bur2b5fa0f034539000-1723064491gpp6",
            "status": 0,
            "amount": "362.71",
            "created_at": "2024-08-07T21:01:31.000000Z",
            "model_source": "ElectricityTransaction"
            },
            {
            "transaction_id": "202408072201-electricity-zcljab6ig4040075100-1723064491yjmo",
            "status": 1,
            "amount": "596.03",
            "created_at": "2024-08-07T21:01:31.000000Z",
            "model_source": "ElectricityTransaction"
            },
            {
            "transaction_id": "202408072201-electricity-xaorcve8ov051138200-1723064491e7nl",
            "status": 0,
            "amount": "869.96",
            "created_at": "2024-08-07T21:01:31.000000Z",
            "model_source": "ElectricityTransaction"
            },
            {
            "transaction_id": "202408072201-electricity-82wh1hc0ju056676200-1723064491rwjh",
            "status": 1,
            "amount": "644.57",
            "created_at": "2024-08-07T21:01:31.000000Z",
            "model_source": "ElectricityTransaction"
            },
            {
            "transaction_id": "202408072201-electricity-ee05rafszm062206600-1723064491nmft",
            "status": 1,
            "amount": "629.65",
            "created_at": "2024-08-07T21:01:31.000000Z",
            "model_source": "ElectricityTransaction"
            },
            {
            "transaction_id": "202408072201-electricity-cyi8bbfmvv067748700-17230644917vtz",
            "status": 0,
            "amount": "937.77",
            "created_at": "2024-08-07T21:01:31.000000Z",
            "model_source": "ElectricityTransaction"
            },
            {
            "transaction_id": "202408072201-electricity-2nyjy2toan073295200-1723064491p2pf",
            "status": 1,
            "amount": "947.29",
            "created_at": "2024-08-07T21:01:31.000000Z",
            "model_source": "ElectricityTransaction"
            }
        ],
        [],
        [],
        [
            {
            "transaction_id": "20240807001323500-1723064491-result-checker-m0r0crpt5s2vyx",
            "status": 1,
            "amount": "257.43",
            "created_at": "2024-08-07T21:01:31.000000Z",
            "model_source": "ResultCheckerTransaction"
            },
            {
            "transaction_id": "20240807006860900-1723064491-result-checker-yydetzsmzchi4u",
            "status": 1,
            "amount": "671.25",
            "created_at": "2024-08-07T21:01:31.000000Z",
            "model_source": "ResultCheckerTransaction"
            },
            {
            "transaction_id": "20240807035021400-1723064490-result-checker-v6usutmvwpl7jw",
            "status": 1,
            "amount": "124.33",
            "created_at": "2024-08-07T21:01:30.000000Z",
            "model_source": "ResultCheckerTransaction"
            },
            {
            "transaction_id": "20240807047064000-1723064490-result-checker-mzp1gx9l3bvowr",
            "status": 0,
            "amount": "790.86",
            "created_at": "2024-08-07T21:01:30.000000Z",
            "model_source": "ResultCheckerTransaction"
            },
            {
            "transaction_id": "20240807095804900-1723064490-result-checker-qakldo3vcnuod5",
            "status": 1,
            "amount": "504.67",
            "created_at": "2024-08-07T21:01:30.000000Z",
            "model_source": "ResultCheckerTransaction"
            },
            {
            "transaction_id": "20240807029482900-1723064490-result-checker-6z9hgntjynwenl",
            "status": 0,
            "amount": "286.85",
            "created_at": "2024-08-07T21:01:30.000000Z",
            "model_source": "ResultCheckerTransaction"
            },
            {
            "transaction_id": "20240807078101700-1723064490-result-checker-h7migv0wtzhuoy",
            "status": 1,
            "amount": "470.18",
            "created_at": "2024-08-07T21:01:30.000000Z",
            "model_source": "ResultCheckerTransaction"
            },
            {
            "transaction_id": "20240807053808300-1723064490-result-checker-bdadqgloj9kyf7",
            "status": 1,
            "amount": "926.85",
            "created_at": "2024-08-07T21:01:30.000000Z",
            "model_source": "ResultCheckerTransaction"
            },
            {
            "transaction_id": "20240807041535200-1723064490-result-checker-7gu497833r51jh",
            "status": 1,
            "amount": "435.17",
            "created_at": "2024-08-07T21:01:30.000000Z",
            "model_source": "ResultCheckerTransaction"
            },
            {
            "transaction_id": "20240807055955000-1723064489-result-checker-syqkg9o66pfwku",
            "status": 1,
            "amount": "386.95",
            "created_at": "2024-08-07T21:01:29.000000Z",
            "model_source": "ResultCheckerTransaction"
            }
        ],
        [
            {
            "transaction_id": "202408072201-cable-41jvqxvvar020899400-1723064492qzfh",
            "status": 1,
            "amount": "306.18",
            "created_at": "2024-08-07T21:01:32.000000Z",
            "model_source": "CableTransaction"
            },
            {
            "transaction_id": "202408072201-cable-lniuqnvymv026432200-1723064492tu8l",
            "status": 0,
            "amount": "760.96",
            "created_at": "2024-08-07T21:01:32.000000Z",
            "model_source": "CableTransaction"
            },
            {
            "transaction_id": "202408072201-cable-uewjasqytp031971000-1723064492q36t",
            "status": 1,
            "amount": "477.01",
            "created_at": "2024-08-07T21:01:32.000000Z",
            "model_source": "CableTransaction"
            },
            {
            "transaction_id": "202408072201-cable-fj7mc78ntp037508600-17230644922xio",
            "status": 1,
            "amount": "247.91",
            "created_at": "2024-08-07T21:01:32.000000Z",
            "model_source": "CableTransaction"
            },
            {
            "transaction_id": "202408072201-cable-jmmhhtqmyo043042100-1723064492pfxn",
            "status": 1,
            "amount": "673.96",
            "created_at": "2024-08-07T21:01:32.000000Z",
            "model_source": "CableTransaction"
            },
            {
            "transaction_id": "202408072201-cable-2l3vzhqjki048582100-1723064492kuds",
            "status": 1,
            "amount": "309.38",
            "created_at": "2024-08-07T21:01:32.000000Z",
            "model_source": "CableTransaction"
            },
            {
            "transaction_id": "202408072201-cable-82xjlre5ll054120000-1723064492s6uf",
            "status": 0,
            "amount": "196.69",
            "created_at": "2024-08-07T21:01:32.000000Z",
            "model_source": "CableTransaction"
            },
            {
            "transaction_id": "202408072201-cable-eaos7zlu5w059666700-1723064492ooyf",
            "status": 1,
            "amount": "699.22",
            "created_at": "2024-08-07T21:01:32.000000Z",
            "model_source": "CableTransaction"
            },
            {
            "transaction_id": "202408072201-cable-nng7lmlwh7079914500-1723064491aqqn",
            "status": 0,
            "amount": "147.96",
            "created_at": "2024-08-07T21:01:31.000000Z",
            "model_source": "CableTransaction"
            },
            {
            "transaction_id": "202408072201-cable-bvk3xcczgp099863700-1723064491t3nd",
            "status": 0,
            "amount": "517.48",
            "created_at": "2024-08-07T21:01:31.000000Z",
            "model_source": "CableTransaction"
            }
        ]
    ]



## Single transaction detail
    URL: localhost:8000/api/transactions/{id}?type=none
    Method: GET
    Valid types: electricity, result_checker, data, cable, airtime


### Error Response
    {
        "status": true,
        "response": {
            "status": false,
            "errors": [
                "invalid transaction type"
            ],
            "message": "invalid transaction type"
        },
        "message": "Transaction fetched"
    }

### Success Response
    {
        "status": true,
        "response": {
            "transaction_id": "202408072201-electricity-bur2b5fa0f034539000-1723064491gpp6",
            "user_id": 2,
            "vendor_id": 2,
            "disco_id": "04810042-0caf-3124-b9e9-6c77315c8ed6",
            "disco_name": "Connelly Inc",
            "meter_number": "MTR6514913",
            "meter_type_id": 1,
            "meter_type_name": "reiciendis",
            "amount": "362.71",
            "customer_mobile_number": "+19067420910",
            "customer_name": "Dixie Marks",
            "customer_address": "44590 Murray Shoals\nNorth Zoila, WA 13445-6666",
            "balance_before": "679.45",
            "balance_after": "15.42",
            "token": "eafb7b0f-14c5-3a2d-a744-0043d67a7603",
            "api_data_id": "d238c9db-cd81-3856-a6fb-b86c52734c91",
            "api_response": "{\"data\": {\"amount\": 505.67, \"disco_name\": \"Parisian, Breitenberg and Hickle\", \"meter_number\": \"MTR4143268\", \"transaction_id\": \"4a965869-66ae-3296-994a-e0417c9dc376\"}, \"status\": \"success\", \"message\": \"Necessitatibus omnis quam vel.\"}",
            "status": 0,
            "created_at": "2024-08-07T21:01:31.000000Z",
            "updated_at": "2024-08-07T21:01:31.000000Z"
        },
        "message": "Transaction fetched"
    }

## Fetch Telcos and Vastel Logos and Banner
    Method: GET
    URL: api/logos?logo={{'mtn_logo', 'airtel_logo', 'glo_logo', '9mobile_logo', 'app_logo', 'app_banner'}}

### Error response
    {
        "status":"false",
        "message": "Invalid column specified.",
        "errors": {
            "logo": [
                "Invalid column specified."
            ]
        }
    }



## Notifications Endpoint

    Method: GET
    URL: api/notifications
    Type could be ('info', 'warning', 'success', 'error')
### Response 
    {
        "status": "success",
        "message": "notification fetched",
        "data": {
            "current_page": 1,
            "data": [
                {
                    "id": 1,
                    "uuid": "c6c856d8-7a23-4498-9f96-35dd54ae9401",
                    "title": "First Test Title",
                    "message": "First test announcement",
                    "type": "info",
                    "start_at": null,
                    "end_at": null,
                    "is_active": 1,
                    "created_at": "2024-08-17T09:21:13.000000Z",
                    "updated_at": "2024-08-17T09:21:13.000000Z"
                },
                {
                    "id": 2,
                    "uuid": "e1f56a93-516c-4f24-bf8b-c106f01607c0",
                    "title": "Second Announcement",
                    "message": "Second Announcement",
                    "type": "info",
                    "start_at": null,
                    "end_at": null,
                    "is_active": 1,
                    "created_at": "2024-08-17T09:22:59.000000Z",
                    "updated_at": "2024-08-17T09:22:59.000000Z"
                },
                {
                    "id": 3,
                    "uuid": "69af1cea-ccca-4dc1-a518-3ae31506846c",
                    "title": "Provident earum quas sed esse eveniet vitae.",
                    "message": "Neque et necessitatibus molestias aliquid nostrum. Ipsam et voluptates ut quidem. Sit fuga dolores numquam et qui ut officiis est. Quia et autem consectetur repellendus libero ut occaecati.",
                    "type": "warning",
                    "start_at": "2024-08-26 10:50:52",
                    "end_at": "2024-09-05 10:50:52",
                    "is_active": 1,
                    "created_at": "2024-08-17T09:50:52.000000Z",
                    "updated_at": "2024-08-17T09:50:52.000000Z"
                },
                {
                    "id": 4,
                    "uuid": "2fcfb881-dfb6-48ec-b5bc-2a2dccf52414",
                    "title": "Architecto dolores qui expedita et perspiciatis non libero.",
                    "message": "Non est possimus impedit pariatur molestiae cumque. Aut nihil tempora incidunt qui illo natus voluptate animi. Sit sit quidem laudantium quibusdam eligendi est et nesciunt. Ullam quam et ut laboriosam consequatur nobis.",
                    "type": "info",
                    "start_at": "2024-08-17 10:50:52",
                    "end_at": "2024-09-02 10:50:52",
                    "is_active": 1,
                    "created_at": "2024-08-17T09:50:52.000000Z",
                    "updated_at": "2024-08-17T09:50:52.000000Z"
                },
                {
                    "id": 5,
                    "uuid": "b39a2893-3776-4e47-97c5-1d62ffe95c5f",
                    "title": "Beatae quia quasi quis illo.",
                    "message": "Maxime id quo ipsa rerum. Reiciendis deleniti quis non cum. Deserunt qui aut tempore quia. Voluptatem et aut et sed quasi quasi.",
                    "type": "error",
                    "start_at": "2024-08-19 10:50:52",
                    "end_at": "2024-08-29 10:50:52",
                    "is_active": 1,
                    "created_at": "2024-08-17T09:50:52.000000Z",
                    "updated_at": "2024-08-17T09:50:52.000000Z"
                },
                {
                    "id": 6,
                    "uuid": "ca908a73-057c-463d-8be3-b00a5753efa0",
                    "title": "Ut eveniet animi voluptas consectetur id explicabo.",
                    "message": "Maxime necessitatibus accusamus consequatur rerum aut voluptatem sed ullam. Est at sed veritatis dolor voluptatem ea. Iste soluta commodi minus et. Inventore ducimus dolores nihil quis.",
                    "type": "success",
                    "start_at": "2024-08-25 10:50:52",
                    "end_at": "2024-09-03 10:50:52",
                    "is_active": 1,
                    "created_at": "2024-08-17T09:50:52.000000Z",
                    "updated_at": "2024-08-17T09:50:52.000000Z"
                },
                {
                    "id": 7,
                    "uuid": "dd0fe78a-4c31-4337-9513-129a2276d86a",
                    "title": "Aliquam sint delectus reprehenderit voluptatum omnis.",
                    "message": "Ratione necessitatibus voluptatibus illum est ut. Ullam voluptatem cumque quam aut amet. Earum maxime adipisci est ad.",
                    "type": "warning",
                    "start_at": "2024-08-20 10:50:52",
                    "end_at": "2024-08-31 10:50:52",
                    "is_active": 1,
                    "created_at": "2024-08-17T09:50:52.000000Z",
                    "updated_at": "2024-08-17T09:50:52.000000Z"
                },
                {
                    "id": 8,
                    "uuid": "63576538-f563-4cc3-9936-7bf8fb69addc",
                    "title": "Aut sed quod at autem ex est nobis.",
                    "message": "Voluptas dicta sint voluptatum commodi corrupti rem. Sit sit quasi dolores possimus dignissimos ipsum omnis. Blanditiis nulla fugit neque iusto dolor debitis quos assumenda.",
                    "type": "info",
                    "start_at": "2024-08-19 10:50:52",
                    "end_at": "2024-09-06 10:50:52",
                    "is_active": 1,
                    "created_at": "2024-08-17T09:50:52.000000Z",
                    "updated_at": "2024-08-17T09:50:52.000000Z"
                },
                {
                    "id": 9,
                    "uuid": "126a75b7-ec25-4a04-91e6-d52b136c61e0",
                    "title": "Id in porro et commodi blanditiis.",
                    "message": "Sit eius ipsa rerum ut neque. Perferendis distinctio reprehenderit quasi earum delectus doloribus. Officia sunt est voluptatum vitae cupiditate.",
                    "type": "info",
                    "start_at": "2024-08-27 10:50:52",
                    "end_at": "2024-08-30 10:50:52",
                    "is_active": 1,
                    "created_at": "2024-08-17T09:50:52.000000Z",
                    "updated_at": "2024-08-17T09:50:52.000000Z"
                },
                {
                    "id": 12,
                    "uuid": "3bdae33d-1f4e-448e-b97c-925345c59d6e",
                    "title": "Et est dicta consequatur voluptates.",
                    "message": "Recusandae at autem enim rem illum odio corporis. Eum qui sed deleniti quia. Sed labore ipsam consequatur.",
                    "type": "error",
                    "start_at": "2024-08-27 10:50:52",
                    "end_at": "2024-08-30 10:50:52",
                    "is_active": 1,
                    "created_at": "2024-08-17T09:50:52.000000Z",
                    "updated_at": "2024-08-17T09:50:52.000000Z"
                }
            ],
            "first_page_url": "http://localhost:8000/api/notifications?page=1",
            "from": 1,
            "last_page": 1,
            "last_page_url": "http://localhost:8000/api/notifications?page=1",
            "links": [
                {
                    "url": null,
                    "label": "&laquo; Previous",
                    "active": false
                },
                {
                    "url": "http://localhost:8000/api/notifications?page=1",
                    "label": "1",
                    "active": true
                },
                {
                    "url": null,
                    "label": "Next &raquo;",
                    "active": false
                }
            ],
            "next_page_url": null,
            "path": "http://localhost:8000/api/notifications",
            "per_page": 10,
            "prev_page_url": null,
            "to": 10,
            "total": 10
        }
    }
