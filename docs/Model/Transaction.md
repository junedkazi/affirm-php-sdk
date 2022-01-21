# Transaction

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**amount** | **int** | The original amount financed to the customer in this transaction. The value is non-negative and is represented in the smallest currency unit, such as cents instead of dollars. | [optional] 
**amount_refunded** | **int** | The amount refunded back to the customer from this transaction. The value may be less than the total amount financed if a partial refund was issued. The value is non-negative and is represented in the smallest currency unit, such as cents instead of dollars. | [optional] 
**authorization_expiration** | **string** | The time when the transaction can no longer be authorized. The value is formatted in RFC 3339. | [optional] 
**checkout_id** | **string** | A unique identifier referencing the Checkout object. | [optional] 
**created** | **string** | The time when the transaction was created. The value is formatted in RFC 3339. | [optional] 
**currency** | **string** | The local currency of the transaction with its being a valid subset of the ISO 4217 currency code. | [optional] 
**events** | [**\Swagger\Client\Model\TransactionEvent[]**](TransactionEvent.md) | An array of TransactionEvent objects. | [optional] 
**id** | **string** | A unique identifier representing the transaction. | [optional] 
**order_id** | **string** | Identifies the order within the merchant&#x27;s order management system that this transaction corresponds to. | [optional] 
**provider_id** | **int** | A unique identifier of the provider that is financing the transaction. | [optional] 
**remove_tax** | **bool** | A bool denoting if tax was paid by the provider (Affirm, LTO). Used by platform integrations to remove tax. | [optional] 
**status** | **string** | The status of the transaction. | [optional] 
**token** | **string** | A JWT signing the JSON response; if PII is included in the response this is also encrypted. | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)

