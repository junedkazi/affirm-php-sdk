# TransactionEvent

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**amount** | **int** | The total value of the transaction, including tax and shipping. The value is non-negative and is represented in the smallest currency unit, such as cents instead of dollars. If the type is capture, this field represents the amount captured. If the type is refund, this field represents the amount refunded, including the fee that was refunded. | [optional] 
**created** | **string** | The time when the transaction event was created. The value is formatted in RFC 3339. | [optional] 
**currency** | **string** | The local currency of the transaction with its being a valid subset of the ISO 4217 currency code. | [optional] 
**fee** | **int** | The merchant fee. | [optional] 
**fee_refunded** | **int** | Portion of the refunded amount that is subtracted from the merchant fee. | [optional] 
**id** | **string** | A unique identifier for the transaction event. | [optional] 
**reference_id** | **string** | An optional, unique identifier that may be associated with each transaction event and reconciled with the system of record used by the merchant. | [optional] 
**type** | **string** | The type of event. | [optional] 
**metadata** | **object** | Unstructured metadata containing any additional data that was passed into the transaction event request. | [optional] 
**token** | **string** | A JWT signing the JSON response. | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)

