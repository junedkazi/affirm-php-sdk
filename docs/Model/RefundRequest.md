# RefundRequest

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**amount** | **int** | The amount to be refunded in cents. If the request omits this parameter, the entire remaining amount on the transaction will be fully refunded. | [optional] 
**reference_id** | **string** | An optional, unique identifier that may be associated with each transaction event and reconciled with the system of record used by the merchant. | [optional] 
**metadata** | **object** | Unstructured metadata containing any additional data to be passed into each refund request. | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)

