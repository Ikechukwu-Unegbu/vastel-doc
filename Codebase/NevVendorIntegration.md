
# Technical Documentation for Integrating a New Vendor Class

This documentation provides a step-by-step guide on how to create and integrate a new vendor class on Vastel.

## Table of Contents
1. [Introduction](#introduction)
2. [Prerequisites](#prerequisites)
3. [Creating the New Vendor Class](#creating-the-new-vendor-class)
4. [Implementing Methods](#implementing-methods)
    - [Get Wallet Balance](#get-wallet-balance)
    - [Airtime Top-up](#airtime-top-up)
    - [Electricity Bill Payment](#electricity-bill-payment)
    - [Cable Subscription](#cable-subscription)
    - [Data Purchase](#data-purchase)
    - [Result Checker](#result-checker)
    - [Verify Account Balance](#verify-account-balance)
    - [Store API Response](#store-api-response)
    - [Query Transaction From Vendor](#query-transaction-from-vendor)
5. [Add the Vendor to the Service Factory](#add-the-vendor-to-the-service-factory)
6. [Testing the Integration](#testing-the-integration)
7. [Conclusion](#conclusion)

---

## Introduction
The `PosTraNetService` class is a vendor service class that handles various functionalities such as:
- Airtime top-up
- Electricity bill payment
- Cable subscription
- Data purchase
- Result checking

This documentation will guide you through creating a similar vendor class and integrating it into the existing Laravel application.

## Prerequisites
Before you start, ensure you have the following:
- A Laravel application set up.
- Basic understanding of Laravel and PHP.
- Access to the vendor API documentation.
- Knowledge of the existing `PosTraNetService` class.

---

## Creating the New Vendor Class
### 1. Create a New Class File
Create a new PHP class file in the `App\Services\Vendor` namespace. For example, create a class called `NewVendorService`:

```php
<?php

namespace App\Services\Vendor;

use App\Models\Vendor;
use App\Helpers\ApiHelper;
use Illuminate\Support\Str;
use App\Models\Data\DataPlan;
use App\Models\Data\DataType;
use App\Models\Utility\Cable;
use App\Models\Data\DataNetwork;
use App\Models\Utility\CablePlan;
use Illuminate\Support\Facades\DB;
use App\Helpers\Admin\VendorHelper;
use App\Models\Utility\Electricity;
use App\Services\CalculateDiscount;
use Illuminate\Support\Facades\Log;
use App\Models\Data\DataTransaction;
use Illuminate\Support\Facades\Auth;
use Illuminate\Support\Facades\Http;
use App\Models\Education\ResultChecker;
use App\Models\Utility\CableTransaction;
use App\Models\Utility\AirtimeTransaction;
use App\Models\Utility\ElectricityTransaction;
use App\Services\Account\AccountBalanceService;
use App\Services\Beneficiary\BeneficiaryService;
use App\Models\Education\ResultCheckerTransaction;

class NewVendorService
{
    protected static $vendor;
    protected static $authUser;

    protected const WALLET_URL = "/user/";
    protected const AIRTIME_URL = "/topup/";
    protected const RESULT_CHECKER_URL = "/epin/";
    protected const ELECTRICITY_URL = "/billpayment/";
    protected const CABLE_URL = "/cablesub/";
    protected const DATA_URL = "/data/";

    public function __construct(Vendor $vendor)
    {
        self::$vendor = $vendor;
        self::$authUser = new AccountBalanceService(Auth::user());
    }

    // Implement the methods as described below
}
```

### 2. Define Constants and Headers
Define the API URL constants and the `headers` method.

```php
protected static function headers()
{
    return [
        'Authorization' => "Token " . self::$vendor->token,
        'Content-Type'  => 'application/json'
    ];
}

protected static function url($url, $data = [])
{
    $url = self::$vendor->api . $url;

    $response = Http::withHeaders(static::headers())->post($url, $data);

    return (is_object($response->object())) ? $response->object() : null;
}
```

---

## Implementing Methods

### Get Wallet Balance
```php
public static function getWalletBalance()
{
    $response = self::url(self::WALLET_URL);
    return $response->balance ?? null;
}
```

### Airtime Top-up
```php
public static function airtime($networkId, $amount, $mobileNumber)
{
    $data = [
        'network' => $networkId,
        'amount' => $amount,
        'mobile_number' => $mobileNumber
    ];

    return self::url(self::AIRTIME_URL, $data);
}
```

### Electricity Bill Payment
```php
public static function electricity($discoId, $meterNumber, $meterType, $amount, $customerName, $customerMobile, $customerAddress)
{
    $data = [
        'disco_id' => $discoId,
        'meter_number' => $meterNumber,
        'meter_type' => $meterType,
        'amount' => $amount,
        'customer_name' => $customerName,
        'customer_mobile' => $customerMobile,
        'customer_address' => $customerAddress,
    ];

    return self::url(self::ELECTRICITY_URL, $data);
}
```

### Cable Subscription
```php
public static function cable($cableId, $cablePlan, $iucNumber, $customer)
{
    $data = [
        'cable_id' => $cableId,
        'plan' => $cablePlan,
        'iuc_number' => $iucNumber,
        'customer' => $customer
    ];

    return self::url(self::CABLE_URL, $data);
}
```

### Data Purchase
```php
public static function data($networkId, $typeId, $dataId, $mobileNumber)
{
    $data = [
        'network_id' => $networkId,
        'type_id' => $typeId,
        'data_id' => $dataId,
        'mobile_number' => $mobileNumber
    ];

    return self::url(self::DATA_URL, $data);
}
```

### Result Checker
```php
public static function resultChecker($examId, $quantity)
{
    $data = [
        'exam_id' => $examId,
        'quantity' => $quantity
    ];

    return self::url(self::RESULT_CHECKER_URL, $data);
}
```

### Verify Account Balance
```php
protected static function verifyAccountBalance($amount)
{
    if (!self::$authUser->verifyAccountBalance($amount)) {
        $errorResponse = [
            'status' => false,
            'error' => 'Insufficient Account Balance.',
            'message' => "You need at least ₦{$amount} to purchase this plan. Please fund your wallet to continue."
        ];
        return (object) $errorResponse;
    }

    return (object) ['status' => true];
}
```

### Store API Response
```php
public static function storeApiResponse($transaction, $response)
{
    // Implementation for storing API responses.
}
```

### Query Transaction From Vendor
```php
public static function queryTransactionFromVendor($data, $type)
{
    // Implementation for querying transaction from vendor.
}
```

---

## Add the Vendor to the Service Factory
### Locate the Factory
Open the `VendorServiceFactory` file.

### Add the New Vendor
Register the new vendor in the factory class.

```php
public static function getService(string $vendorName)
{
    switch ($vendorName) {
        case 'PosTraNet':
            return new PosTraNetService();
        case 'GladTiding':
            return new GladTidingService();
        case 'VTPass':
            return new VTPassService();
        case 'NewVendor':
            return new NewVendorService();
        default:
            throw new \Exception("Vendor service '{$vendorName}' not found.");
    }
}
```

---

## Testing the Integration
### Unit Testing
Ensure you have unit tests for each method to verify that the new vendor class works as expected.

### Manual Testing
Perform manual testing by integrating the new vendor class into your application and testing each functionality.

---

## Conclusion
By following this documentation, you should be able to create and integrate a new vendor class in your Laravel application. The new class will handle various functionalities such as airtime top-up, electricity bill payment, cable subscription, data purchase, and result checking, similar to the existing `PosTraNetService` class.
