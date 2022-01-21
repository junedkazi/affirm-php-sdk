# SettlementEventSummary

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**date** | **string** | The date corresponding to the settlement events that are being summarized. | 
**deposit_id** | **string** | The ID that a user sees on their bank statement | 
**total_sales** | **int** | The sum of the disbursements during a given day (before fees), in cents. | 
**total_refunds** | **int** | The sum of the refunds disbursed during a given day (before fees), in cents. | 
**total_fees** | **int** | The sum of the fees during a given day, in cents. | 
**total_settled** | **int** | total_sales - total_fees or total_refunds - total_fees | 
**account_last_four** | **string** | Last four digits of the disbursed to bank account number | [optional] 
**currency** | **string** | Currency of the deposit associated with the settlement summary | 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)

