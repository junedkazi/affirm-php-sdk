# Swagger\Client\TransactionsAPIApi

All URIs are relative to *https://api.affirm.com/api/v1*

Method | HTTP request | Description
------------- | ------------- | -------------
[**authorizeTransaction**](TransactionsAPIApi.md#authorizetransaction) | **POST** /transactions | Authorize Transaction
[**captureTransaction**](TransactionsAPIApi.md#capturetransaction) | **POST** /transactions/{id}/capture | Capture Transaction
[**listSettlementEventSummaries**](TransactionsAPIApi.md#listsettlementeventsummaries) | **GET** /settlements/daily | List Settlement Event Summaries
[**listSettlementEvents**](TransactionsAPIApi.md#listsettlementevents) | **GET** /settlements/events | List Settlement Events
[**listTransactionEvents**](TransactionsAPIApi.md#listtransactionevents) | **GET** /transactions/events | List Transaction Events
[**listTransactions**](TransactionsAPIApi.md#listtransactions) | **GET** /transactions | List Transactions
[**readTransaction**](TransactionsAPIApi.md#readtransaction) | **GET** /transactions/{id} | Read Transaction
[**refundTransaction**](TransactionsAPIApi.md#refundtransaction) | **POST** /transactions/{id}/refund | Refund Transaction
[**updateTransaction**](TransactionsAPIApi.md#updatetransaction) | **POST** /transactions/{id} | Update Transaction
[**voidTransaction**](TransactionsAPIApi.md#voidtransaction) | **POST** /transactions/{id}/void | Void Transaction

# **authorizeTransaction**
> \Swagger\Client\Model\Transaction authorizeTransaction($body, $idempotency_key)

Authorize Transaction

Authorizes a transaction. Transaction authorization occurs after a user completes the Affirm checkout flow and returns to the merchant site. Authorizing a transaction generates a unique `id` that will be used as a reference moving forward.

### Example
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
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**\Swagger\Client\Model\AuthorizeRequest**](../Model/AuthorizeRequest.md)| The request body used to create a transaction. | [optional]
 **idempotency_key** | **string**|  | [optional]

### Return type

[**\Swagger\Client\Model\Transaction**](../Model/Transaction.md)

### Authorization

[basicAuth](../../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: */*

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **captureTransaction**
> \Swagger\Client\Model\TransactionEvent captureTransaction($id, $body, $idempotency_key)

Capture Transaction

Include the `id` returned in the `authorize transaction` response to capture a transaction.

### Example
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
$id = "id_example"; // string | The unique identifier of the transaction.
$body = new \Swagger\Client\Model\CaptureRequest(); // \Swagger\Client\Model\CaptureRequest | 
$idempotency_key = "idempotency_key_example"; // string | 

try {
    $result = $apiInstance->captureTransaction($id, $body, $idempotency_key);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling TransactionsAPIApi->captureTransaction: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **string**| The unique identifier of the transaction. |
 **body** | [**\Swagger\Client\Model\CaptureRequest**](../Model/CaptureRequest.md)|  | [optional]
 **idempotency_key** | **string**|  | [optional]

### Return type

[**\Swagger\Client\Model\TransactionEvent**](../Model/TransactionEvent.md)

### Authorization

[basicAuth](../../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: */*

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **listSettlementEventSummaries**
> \Swagger\Client\Model\PaginatedSettlementEventSummaryResponse listSettlementEventSummaries($merchant_id, $limit, $after, $before, $from_cursor_uuid, $from_cursor_date, $to_cursor_uuid, $to_cursor_date, $ordering)

List Settlement Event Summaries

Lists settlement event summaries by merchant.

### Example
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
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **merchant_id** | **string**| The Affirm Merchant ID |
 **limit** | **int**| The maximum number of results per page. Default is 5. | [optional]
 **after** | **\DateTime**| The beginning of the date range (inclusive) | [optional]
 **before** | **\DateTime**| The end of the date range (inclusive) | [optional]
 **from_cursor_uuid** | [**string**](../Model/.md)| Optional paging cursor uuid after which results should be returned. This uuid, along with from_cursor_date is returned in the prev_page field in the 200 response | [optional]
 **from_cursor_date** | **\DateTime**| Optional paging cursor date after which results should be returned. This date, along with from_cursor_uuid is returned in the prev_page field in the 200 response | [optional]
 **to_cursor_uuid** | [**string**](../Model/.md)| Optional paging cursor uuid before which results should be returned. This uuid, along with to_cursor_date is returned in the next_page field in the 200 response | [optional]
 **to_cursor_date** | **\DateTime**| Optional paging cursor date before which results should be returned. This date, along with to_cursor_uuid is returned in the next_page field in the 200 response | [optional]
 **ordering** | **string**| Optional parameter to define ordering of results. Default is descending chronological order | [optional]

### Return type

[**\Swagger\Client\Model\PaginatedSettlementEventSummaryResponse**](../Model/PaginatedSettlementEventSummaryResponse.md)

### Authorization

[basicAuth](../../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: */*

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **listSettlementEvents**
> \Swagger\Client\Model\PaginatedSettlementEventResponse listSettlementEvents($merchant_id, $limit, $after, $before, $from_cursor_uuid, $from_cursor_date, $to_cursor_uuid, $to_cursor_date, $ordering)

List Settlement Events

Lists settlement events by merchant.

### Example
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
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **merchant_id** | **string**| The Affirm Merchant ID |
 **limit** | **int**| The maximum number of results per page. Default is 5. | [optional]
 **after** | **\DateTime**| The beginning of the date range (inclusive) | [optional]
 **before** | **\DateTime**| The end of the date range (inclusive) | [optional]
 **from_cursor_uuid** | [**string**](../Model/.md)| Optional paging cursor uuid after which results should be returned. This uuid, along with from_cursor_date is returned in the prev_page field in the 200 response | [optional]
 **from_cursor_date** | **\DateTime**| Optional paging cursor date after which results should be returned. This date, along with from_cursor_uuid is returned in the prev_page field in the 200 response | [optional]
 **to_cursor_uuid** | [**string**](../Model/.md)| Optional paging cursor uuid before which results should be returned. This uuid, along with to_cursor_date is returned in the next_page field in the 200 response | [optional]
 **to_cursor_date** | **\DateTime**| Optional paging cursor date before which results should be returned. This date, along with to_cursor_uuid is returned in the next_page field in the 200 response | [optional]
 **ordering** | **string**| Optional parameter to define ordering of results. Default is descending chronological order | [optional]

### Return type

[**\Swagger\Client\Model\PaginatedSettlementEventResponse**](../Model/PaginatedSettlementEventResponse.md)

### Authorization

[basicAuth](../../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: */*

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **listTransactionEvents**
> \Swagger\Client\Model\ListTransactionEvents listTransactionEvents($transaction_type, $transaction_event_type, $limit, $before_date, $after_date, $before_ari, $after_ari)

List Transaction Events

Lists transaction events.

### Example
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
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **transaction_type** | **string**| Type of transaction to be listed, list one of &#x60;charge&#x60; or &#x60;lease&#x60;. |
 **transaction_event_type** | **string**| Type of transaction events to be listed, list one of &#x60;authorize&#x60;, &#x60;capture&#x60;, &#x60;refund&#x60;, &#x60;void&#x60;, or &#x60;all&#x60;. |
 **limit** | **string**| Max number of transaction events to list per page. | [optional]
 **before_date** | **string**| End date of query. | [optional]
 **after_date** | **string**| Start date of query. | [optional]
 **before_ari** | **string**| Optional end event ARI of query, used during pagination. | [optional]
 **after_ari** | **string**| Optional start event ARI of query, used during pagination. | [optional]

### Return type

[**\Swagger\Client\Model\ListTransactionEvents**](../Model/ListTransactionEvents.md)

### Authorization

[basicAuth](../../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: */*

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **listTransactions**
> \Swagger\Client\Model\ListTransactions listTransactions($transaction_type, $allow_marqeta_view, $before, $after, $limit, $before_date, $after_date, $before_timestamp, $after_timestamp)

List Transactions

### Example
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
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **transaction_type** | **string**| Type of transaction to be listed, default lists all, otherwise list one of &#x60;charge&#x60; or &#x60;lease&#x60;. |
 **allow_marqeta_view** | **bool**| If we want to allow marqeta view, only relevant for charges. | [optional]
 **before** | **string**| End ARI to query on. | [optional]
 **after** | **string**| Start ARI to query on. | [optional]
 **limit** | **string**| Max number of transactions to list. | [optional]
 **before_date** | **string**| End date of query. | [optional]
 **after_date** | **string**| Start date of query. | [optional]
 **before_timestamp** | **string**| Unix timestamp representing the end time of the query. | [optional]
 **after_timestamp** | **string**| Unix timestamp representing the start time of the query. | [optional]

### Return type

[**\Swagger\Client\Model\ListTransactions**](../Model/ListTransactions.md)

### Authorization

[basicAuth](../../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: */*

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **readTransaction**
> \Swagger\Client\Model\Transaction readTransaction($id, $expand)

Read Transaction

Retrieves transaction data.

### Example
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
$id = "id_example"; // string | The unique identifier of the transaction.
$expand = "expand_example"; // string | A comma-separated set of related objects to expand in the response.

try {
    $result = $apiInstance->readTransaction($id, $expand);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling TransactionsAPIApi->readTransaction: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **string**| The unique identifier of the transaction. |
 **expand** | **string**| A comma-separated set of related objects to expand in the response. | [optional]

### Return type

[**\Swagger\Client\Model\Transaction**](../Model/Transaction.md)

### Authorization

[basicAuth](../../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: */*

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **refundTransaction**
> \Swagger\Client\Model\TransactionEvent refundTransaction($id, $body, $idempotency_key)

Refund Transaction

Refunds a transaction. You can either refund the entire amount or specify a partial amount.

### Example
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
$id = "id_example"; // string | The unique identifier of the transaction.
$body = new \Swagger\Client\Model\RefundRequest(); // \Swagger\Client\Model\RefundRequest | The request body used to refund a transaction.
$idempotency_key = "idempotency_key_example"; // string | 

try {
    $result = $apiInstance->refundTransaction($id, $body, $idempotency_key);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling TransactionsAPIApi->refundTransaction: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **string**| The unique identifier of the transaction. |
 **body** | [**\Swagger\Client\Model\RefundRequest**](../Model/RefundRequest.md)| The request body used to refund a transaction. | [optional]
 **idempotency_key** | **string**|  | [optional]

### Return type

[**\Swagger\Client\Model\TransactionEvent**](../Model/TransactionEvent.md)

### Authorization

[basicAuth](../../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: */*

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **updateTransaction**
> \Swagger\Client\Model\TransactionEvent updateTransaction($id, $body)

Update Transaction

Updates a transaction by specifying the values of the parameters passed. Any parameters that you don't provide won't change.

### Example
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
$id = "id_example"; // string | The unique identifier of the transaction.
$body = new \Swagger\Client\Model\UpdateRequest(); // \Swagger\Client\Model\UpdateRequest | The request body used to update a transaction.

try {
    $result = $apiInstance->updateTransaction($id, $body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling TransactionsAPIApi->updateTransaction: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **string**| The unique identifier of the transaction. |
 **body** | [**\Swagger\Client\Model\UpdateRequest**](../Model/UpdateRequest.md)| The request body used to update a transaction. | [optional]

### Return type

[**\Swagger\Client\Model\TransactionEvent**](../Model/TransactionEvent.md)

### Authorization

[basicAuth](../../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: */*

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **voidTransaction**
> \Swagger\Client\Model\TransactionEvent voidTransaction($id, $body, $idempotency_key)

Void Transaction

Voids an entire transaction.

### Example
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

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **string**| The unique identifier of the transaction. |
 **body** | [**\Swagger\Client\Model\VoidRequest**](../Model/VoidRequest.md)| The request body used to void a transaction. | [optional]
 **idempotency_key** | **string**|  | [optional]

### Return type

[**\Swagger\Client\Model\TransactionEvent**](../Model/TransactionEvent.md)

### Authorization

[basicAuth](../../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: */*

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

