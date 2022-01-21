# PaginatedSettlementEventSummaryResponse

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**count** | **int** | The number of settlement summary events returned on the current page. | 
**data** | [**\Swagger\Client\Model\SettlementEventSummary[]**](SettlementEventSummary.md) |  | 
**prev_page** | **string** | URL-encoded parameters that include the date and UUID of the previous results for cursor-based pagination. Empty string if no previous results. Previous results refer to newer results if sorted in descending chronological order, and will refer to older results if sorted in ascending chronological order. | 
**next_page** | **string** | URL-encoded parameters that include the date and UUID of the next results for cursor-based pagination. Empty string if no next results. Next results refer to older results if sorted in descending chronological order, and will refer to newer results if sorted in ascending chronological order. | 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)

