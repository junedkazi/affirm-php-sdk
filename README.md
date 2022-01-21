# SwaggerClient-php
No description provided (generated by Swagger Codegen https://github.com/swagger-api/swagger-codegen)

This PHP package is automatically generated by the [Swagger Codegen](https://github.com/swagger-api/swagger-codegen) project:

- API version: 1.0.0-oas3
- Build package: io.swagger.codegen.v3.generators.php.PhpClientCodegen

## Requirements

PHP 5.5 and later

## Installation & Usage
### Composer

To install the bindings via [Composer](http://getcomposer.org/), add the following to `composer.json`:

```
{
  "repositories": [
    {
      "type": "git",
      "url": "https://github.com/GIT_USER_ID/GIT_REPO_ID.git"
    }
  ],
  "require": {
    "GIT_USER_ID/GIT_REPO_ID": "*@dev"
  }
}
```

Then run `composer install`

### Manual Installation

Download the files and include `autoload.php`:

```php
    require_once('/path/to/SwaggerClient-php/vendor/autoload.php');
```

## Tests

To run the unit tests:

```
composer install
./vendor/bin/phpunit
```

## Getting Started

Please follow the [installation procedure](#installation--usage) and then run the following:

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');
// Configure HTTP basic authorization: basicAuth
$config = Swagger\Client\Configuration::getDefaultConfiguration()
    ->setUsername('YOUR_USERNAME')
    ->setPassword('YOUR_PASSWORD');

$apiInstance = new Swagger\Client\Api\TransactionsAPIApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$body = new \Swagger\Client\Model\AuthorizeRequest(); // \Swagger\Client\Model\AuthorizeRequest | The request body used to create a transaction.
$idempotency_key = "idempotency_key_example"; // string | 

try {
    $result = $apiInstance->authorizeTransaction($body, $idempotency_key);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling TransactionsAPIApi->authorizeTransaction: ', $e->getMessage(), PHP_EOL;
}
// Configure HTTP basic authorization: basicAuth
$config = Swagger\Client\Configuration::getDefaultConfiguration()
    ->setUsername('YOUR_USERNAME')
    ->setPassword('YOUR_PASSWORD');

$apiInstance = new Swagger\Client\Api\TransactionsAPIApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = "id_example"; // string | The unique identifier of the transaction.
$body = new \Swagger\Client\Model\CaptureRequest(); // \Swagger\Client\Model\CaptureRequest | 
$idempotency_key = "idempotency_key_example"; // string | 

try {
    $result = $apiInstance->captureTransaction($id, $body, $idempotency_key);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling TransactionsAPIApi->captureTransaction: ', $e->getMessage(), PHP_EOL;
}
// Configure HTTP basic authorization: basicAuth
$config = Swagger\Client\Configuration::getDefaultConfiguration()
    ->setUsername('YOUR_USERNAME')
    ->setPassword('YOUR_PASSWORD');

$apiInstance = new Swagger\Client\Api\TransactionsAPIApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$merchant_id = "merchant_id_example"; // string | The Affirm Merchant ID
$limit = 56; // int | The maximum number of results per page. Default is 5.
$after = new \DateTime("2013-10-20"); // \DateTime | The beginning of the date range (inclusive)
$before = new \DateTime("2013-10-20"); // \DateTime | The end of the date range (inclusive)
$from_cursor_uuid = "38400000-8cf0-11bd-b23e-10b96e4ef00d"; // string | Optional paging cursor uuid after which results should be returned. This uuid, along with from_cursor_date is returned in the prev_page field in the 200 response
$from_cursor_date = new \DateTime("2013-10-20"); // \DateTime | Optional paging cursor date after which results should be returned. This date, along with from_cursor_uuid is returned in the prev_page field in the 200 response
$to_cursor_uuid = "38400000-8cf0-11bd-b23e-10b96e4ef00d"; // string | Optional paging cursor uuid before which results should be returned. This uuid, along with to_cursor_date is returned in the next_page field in the 200 response
$to_cursor_date = new \DateTime("2013-10-20"); // \DateTime | Optional paging cursor date before which results should be returned. This date, along with to_cursor_uuid is returned in the next_page field in the 200 response
$ordering = "ordering_example"; // string | Optional parameter to define ordering of results. Default is descending chronological order

try {
    $result = $apiInstance->listSettlementEventSummaries($merchant_id, $limit, $after, $before, $from_cursor_uuid, $from_cursor_date, $to_cursor_uuid, $to_cursor_date, $ordering);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling TransactionsAPIApi->listSettlementEventSummaries: ', $e->getMessage(), PHP_EOL;
}
// Configure HTTP basic authorization: basicAuth
$config = Swagger\Client\Configuration::getDefaultConfiguration()
    ->setUsername('YOUR_USERNAME')
    ->setPassword('YOUR_PASSWORD');

$apiInstance = new Swagger\Client\Api\TransactionsAPIApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$merchant_id = "merchant_id_example"; // string | The Affirm Merchant ID
$limit = 56; // int | The maximum number of results per page. Default is 5.
$after = new \DateTime("2013-10-20"); // \DateTime | The beginning of the date range (inclusive)
$before = new \DateTime("2013-10-20"); // \DateTime | The end of the date range (inclusive)
$from_cursor_uuid = "38400000-8cf0-11bd-b23e-10b96e4ef00d"; // string | Optional paging cursor uuid after which results should be returned. This uuid, along with from_cursor_date is returned in the prev_page field in the 200 response
$from_cursor_date = new \DateTime("2013-10-20"); // \DateTime | Optional paging cursor date after which results should be returned. This date, along with from_cursor_uuid is returned in the prev_page field in the 200 response
$to_cursor_uuid = "38400000-8cf0-11bd-b23e-10b96e4ef00d"; // string | Optional paging cursor uuid before which results should be returned. This uuid, along with to_cursor_date is returned in the next_page field in the 200 response
$to_cursor_date = new \DateTime("2013-10-20"); // \DateTime | Optional paging cursor date before which results should be returned. This date, along with to_cursor_uuid is returned in the next_page field in the 200 response
$ordering = "ordering_example"; // string | Optional parameter to define ordering of results. Default is descending chronological order

try {
    $result = $apiInstance->listSettlementEvents($merchant_id, $limit, $after, $before, $from_cursor_uuid, $from_cursor_date, $to_cursor_uuid, $to_cursor_date, $ordering);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling TransactionsAPIApi->listSettlementEvents: ', $e->getMessage(), PHP_EOL;
}
// Configure HTTP basic authorization: basicAuth
$config = Swagger\Client\Configuration::getDefaultConfiguration()
    ->setUsername('YOUR_USERNAME')
    ->setPassword('YOUR_PASSWORD');

$apiInstance = new Swagger\Client\Api\TransactionsAPIApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$transaction_type = "transaction_type_example"; // string | Type of transaction to be listed, list one of `charge` or `lease`.
$transaction_event_type = "transaction_event_type_example"; // string | Type of transaction events to be listed, list one of `authorize`, `capture`, `refund`, `void`, or `all`.
$limit = "limit_example"; // string | Max number of transaction events to list per page.
$before_date = "before_date_example"; // string | End date of query.
$after_date = "after_date_example"; // string | Start date of query.
$before_ari = "before_ari_example"; // string | Optional end event ARI of query, used during pagination.
$after_ari = "after_ari_example"; // string | Optional start event ARI of query, used during pagination.

try {
    $result = $apiInstance->listTransactionEvents($transaction_type, $transaction_event_type, $limit, $before_date, $after_date, $before_ari, $after_ari);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling TransactionsAPIApi->listTransactionEvents: ', $e->getMessage(), PHP_EOL;
}
// Configure HTTP basic authorization: basicAuth
$config = Swagger\Client\Configuration::getDefaultConfiguration()
    ->setUsername('YOUR_USERNAME')
    ->setPassword('YOUR_PASSWORD');

$apiInstance = new Swagger\Client\Api\TransactionsAPIApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$transaction_type = "transaction_type_example"; // string | Type of transaction to be listed, default lists all, otherwise list one of `charge` or `lease`.
$allow_marqeta_view = true; // bool | If we want to allow marqeta view, only relevant for charges.
$before = "before_example"; // string | End ARI to query on.
$after = "after_example"; // string | Start ARI to query on.
$limit = "limit_example"; // string | Max number of transactions to list.
$before_date = "before_date_example"; // string | End date of query.
$after_date = "after_date_example"; // string | Start date of query.
$before_timestamp = "before_timestamp_example"; // string | Unix timestamp representing the end time of the query.
$after_timestamp = "after_timestamp_example"; // string | Unix timestamp representing the start time of the query.

try {
    $result = $apiInstance->listTransactions($transaction_type, $allow_marqeta_view, $before, $after, $limit, $before_date, $after_date, $before_timestamp, $after_timestamp);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling TransactionsAPIApi->listTransactions: ', $e->getMessage(), PHP_EOL;
}
// Configure HTTP basic authorization: basicAuth
$config = Swagger\Client\Configuration::getDefaultConfiguration()
    ->setUsername('YOUR_USERNAME')
    ->setPassword('YOUR_PASSWORD');

$apiInstance = new Swagger\Client\Api\TransactionsAPIApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = "id_example"; // string | The unique identifier of the transaction.
$expand = "expand_example"; // string | A comma-separated set of related objects to expand in the response.

try {
    $result = $apiInstance->readTransaction($id, $expand);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling TransactionsAPIApi->readTransaction: ', $e->getMessage(), PHP_EOL;
}
// Configure HTTP basic authorization: basicAuth
$config = Swagger\Client\Configuration::getDefaultConfiguration()
    ->setUsername('YOUR_USERNAME')
    ->setPassword('YOUR_PASSWORD');

$apiInstance = new Swagger\Client\Api\TransactionsAPIApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = "id_example"; // string | The unique identifier of the transaction.
$body = new \Swagger\Client\Model\RefundRequest(); // \Swagger\Client\Model\RefundRequest | The request body used to refund a transaction.
$idempotency_key = "idempotency_key_example"; // string | 

try {
    $result = $apiInstance->refundTransaction($id, $body, $idempotency_key);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling TransactionsAPIApi->refundTransaction: ', $e->getMessage(), PHP_EOL;
}
// Configure HTTP basic authorization: basicAuth
$config = Swagger\Client\Configuration::getDefaultConfiguration()
    ->setUsername('YOUR_USERNAME')
    ->setPassword('YOUR_PASSWORD');

$apiInstance = new Swagger\Client\Api\TransactionsAPIApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = "id_example"; // string | The unique identifier of the transaction.
$body = new \Swagger\Client\Model\UpdateRequest(); // \Swagger\Client\Model\UpdateRequest | The request body used to update a transaction.

try {
    $result = $apiInstance->updateTransaction($id, $body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling TransactionsAPIApi->updateTransaction: ', $e->getMessage(), PHP_EOL;
}
// Configure HTTP basic authorization: basicAuth
$config = Swagger\Client\Configuration::getDefaultConfiguration()
    ->setUsername('YOUR_USERNAME')
    ->setPassword('YOUR_PASSWORD');

$apiInstance = new Swagger\Client\Api\TransactionsAPIApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$id = "id_example"; // string | The unique identifier of the transaction.
$body = new \Swagger\Client\Model\VoidRequest(); // \Swagger\Client\Model\VoidRequest | The request body used to void a transaction.
$idempotency_key = "idempotency_key_example"; // string | 

try {
    $result = $apiInstance->voidTransaction($id, $body, $idempotency_key);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling TransactionsAPIApi->voidTransaction: ', $e->getMessage(), PHP_EOL;
}
?>
```

## Documentation for API Endpoints

All URIs are relative to *https://api.affirm.com/api/v1*

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*TransactionsAPIApi* | [**authorizeTransaction**](docs/Api/TransactionsAPIApi.md#authorizetransaction) | **POST** /transactions | Authorize Transaction
*TransactionsAPIApi* | [**captureTransaction**](docs/Api/TransactionsAPIApi.md#capturetransaction) | **POST** /transactions/{id}/capture | Capture Transaction
*TransactionsAPIApi* | [**listSettlementEventSummaries**](docs/Api/TransactionsAPIApi.md#listsettlementeventsummaries) | **GET** /settlements/daily | List Settlement Event Summaries
*TransactionsAPIApi* | [**listSettlementEvents**](docs/Api/TransactionsAPIApi.md#listsettlementevents) | **GET** /settlements/events | List Settlement Events
*TransactionsAPIApi* | [**listTransactionEvents**](docs/Api/TransactionsAPIApi.md#listtransactionevents) | **GET** /transactions/events | List Transaction Events
*TransactionsAPIApi* | [**listTransactions**](docs/Api/TransactionsAPIApi.md#listtransactions) | **GET** /transactions | List Transactions
*TransactionsAPIApi* | [**readTransaction**](docs/Api/TransactionsAPIApi.md#readtransaction) | **GET** /transactions/{id} | Read Transaction
*TransactionsAPIApi* | [**refundTransaction**](docs/Api/TransactionsAPIApi.md#refundtransaction) | **POST** /transactions/{id}/refund | Refund Transaction
*TransactionsAPIApi* | [**updateTransaction**](docs/Api/TransactionsAPIApi.md#updatetransaction) | **POST** /transactions/{id} | Update Transaction
*TransactionsAPIApi* | [**voidTransaction**](docs/Api/TransactionsAPIApi.md#voidtransaction) | **POST** /transactions/{id}/void | Void Transaction

## Documentation For Models

 - [AuthorizeRequest](docs/Model/AuthorizeRequest.md)
 - [CaptureRequest](docs/Model/CaptureRequest.md)
 - [Conflict](docs/Model/Conflict.md)
 - [ErrorBadRequest](docs/Model/ErrorBadRequest.md)
 - [ErrorNotFound](docs/Model/ErrorNotFound.md)
 - [ErrorUnauthorized](docs/Model/ErrorUnauthorized.md)
 - [InternalServerError](docs/Model/InternalServerError.md)
 - [ListTransactionEvents](docs/Model/ListTransactionEvents.md)
 - [ListTransactions](docs/Model/ListTransactions.md)
 - [PaginatedSettlementEventResponse](docs/Model/PaginatedSettlementEventResponse.md)
 - [PaginatedSettlementEventSummaryResponse](docs/Model/PaginatedSettlementEventSummaryResponse.md)
 - [RefundRequest](docs/Model/RefundRequest.md)
 - [SettlementEvent](docs/Model/SettlementEvent.md)
 - [SettlementEventSummary](docs/Model/SettlementEventSummary.md)
 - [Transaction](docs/Model/Transaction.md)
 - [TransactionEvent](docs/Model/TransactionEvent.md)
 - [TransactionEventsForTransaction](docs/Model/TransactionEventsForTransaction.md)
 - [UnexpectedError](docs/Model/UnexpectedError.md)
 - [UpdateRequest](docs/Model/UpdateRequest.md)
 - [UpdateRequestShipping](docs/Model/UpdateRequestShipping.md)
 - [UpdateRequestShippingAddress](docs/Model/UpdateRequestShippingAddress.md)
 - [UpdateRequestShippingName](docs/Model/UpdateRequestShippingName.md)
 - [VoidRequest](docs/Model/VoidRequest.md)

## Documentation For Authorization


## basicAuth

- **Type**: HTTP basic authentication


## Author


