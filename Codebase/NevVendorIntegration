
# Technical Documentation for Integrating a New Vendor Class

This document serves as a comprehensive guide to creating and integrating a new vendor class into the Vastel platform. It details the steps for defining the class, implementing functionalities, and ensuring smooth integration into the existing system.

---

## Table of Contents
1. **Introduction**
2. **Prerequisites**
3. **Creating the New Vendor Class**
4. **Defining Constants and Headers**
5. **Implementing Methods**
   - Get Wallet Balance
   - Airtime Top-Up
   - Electricity Bill Payment
   - Cable Subscription
   - Data Purchase
   - Result Checker
   - Verify Account Balance
   - Store API Response
   - Query Transaction From Vendor
6. **Registering the Vendor in the Service Factory**
7. **Testing the Integration**
8. **Conclusion**

---

## Introduction
The Vastel platform uses vendor classes to handle operations such as airtime top-up, electricity bill payment, cable subscription, data purchase, and result checking. This documentation explains how to create and integrate a new vendor class that adheres to the existing standards, ensuring seamless compatibility with the platform.

---

## Prerequisites
Before you begin, ensure that you:
1. Have a **Laravel application** set up.
2. Understand **API integration** and the existing `PosTraNetService` class structure.
3. Have access to the vendor's **API documentation**.
4. Are familiar with **PHP** and **Laravel's service container**.

> **Note**: Familiarity with HTTP request handling using `Http` and database interaction using Eloquent is essential.

---

## Creating the New Vendor Class

### Step 1: **Create the Class**
Create a new class in the `App\Services\Vendor` namespace. For instance, to integrate a vendor named "NewVendor," create `NewVendorService.php` as follows:

```php
<?php

namespace App\Services\Vendor;

use App\Models\Vendor;
use App\Services\Account\AccountBalanceService;
use Illuminate\Support\Facades\Auth;
use Illuminate\Support\Facades\Http;

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

    // Add methods as described in the next sections.
}
```

### Step 2: **Why Use the Vendor Namespace?**
Placing the class in `App\Services\Vendor` ensures consistency with other vendor classes and makes it easier for developers to locate and manage vendor-specific logic.

---

## Defining Constants and Headers

### **Define Constants**
Constants are used for API endpoints:

```php
protected const WALLET_URL = "/user/";
protected const AIRTIME_URL = "/topup/";
protected const RESULT_CHECKER_URL = "/epin/";
protected const ELECTRICITY_URL = "/billpayment/";
protected const CABLE_URL = "/cablesub/";
protected const DATA_URL = "/data/";
```

### **Headers and URL Method**
Headers are essential for authenticating API requests, while the `url` method facilitates sending requests.

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

Below are all the methods required for integrating a new vendor class:

### **1. Get Wallet Balance**
This method retrieves the wallet balance from the vendor:

```php
public static function getWalletBalance()
{
    return self::url(self::WALLET_URL);
}
```

### **2. Airtime Top-Up**
This method handles airtime top-up requests:

```php
public static function airtime($networkId, $amount, $mobileNumber)
{
    $data = [
        "network_id" => $networkId,
        "amount" => $amount,
        "mobile_number" => $mobileNumber
    ];

    return self::url(self::AIRTIME_URL, $data);
}
```

### **3. Electricity Bill Payment**
Handles electricity bill payment:

```php
public static function electricity($discoId, $meterNumber, $meterType, $amount, $customerName, $customerMobile, $customerAddress)
{
    $data = [
        "disco_id" => $discoId,
        "meter_number" => $meterNumber,
        "meter_type" => $meterType,
        "amount" => $amount,
        "customer_name" => $customerName,
        "customer_mobile" => $customerMobile,
        "customer_address" => $customerAddress
    ];

    return self::url(self::ELECTRICITY_URL, $data);
}
```

... (remaining methods in the same format) ...

---

## Registering the Vendor in the Service Factory
...

## Testing the Integration
...

## Conclusion
...
