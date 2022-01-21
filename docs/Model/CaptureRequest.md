# CaptureRequest

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**order_id** | **string** | Identifies the order within the merchant&#x27;s order management system that this transaction corresponds to. It is only returned in the response if included in the request. | [optional] 
**reference_id** | **string** | An optional, unique identifier that may be associated with each transaction event and reconciled with the system of record used by the merchant. | [optional] 
**shipping_carrier** | **string** | The shipping carrier used to ship the items. | [optional] 
**shipping_confirmation** | **string** | The tracking number of the shipment. | [optional] 
**amount** | **int** | The amount to capture, used only for merchants that are enabled with split capture. The value is positive and is represented in the smallest currency unit, such as cents instead of dollars. | [optional] 
**metadata** | **object** | Unstructured metadata containing any additional data to be passed into each capture request. | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)

