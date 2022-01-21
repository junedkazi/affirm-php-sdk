# SettlementEvent

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **string** | Unique UUID for the settlement event | 
**date** | [**\DateTime**](\DateTime.md) | The disbursed date, which is the date that the deposit was initiated. | 
**effective_date** | [**\DateTime**](\DateTime.md) | The date of the loan event that caused this Settlement. | 
**purchase_id** | **string** | The ID of the purchase. | 
**order_id** | **string** | The Partner Order ID. | [optional] 
**transaction_event_id** | **string** | The ID of the transaction event that caused the disbursement. | [optional] 
**merchant_id** | **string** | The ID of the merchant. | 
**event_type** | **string** | Type of settlement event. | 
**sales** | **int** | The amount of the disbursement (before fees), in cents. | 
**refunds** | **int** | The amount of the refund (before fees), in cents. | 
**fees** | **int** | The fee amount (in cents). | 
**transaction_fees** | **int** | The transaction fee amount (in cents). | [optional] 
**total_settled** | **int** | The sale or refund amount net the fees (in cents). | 
**mdr** | **float** | Merchant discount rate (merchant fee) associated with the charge. | [optional] 
**deposit_id** | **string** | The ACH identifier of the deposit made in the merchants bank account | 
**currency** | **string** | The currency of the settlement event | 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)

