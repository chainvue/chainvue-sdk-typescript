# SearchApi

All URIs are relative to *http://localhost*

|Method | HTTP request | Description|
|------------- | ------------- | -------------|
|[**universalSearch**](#universalsearch) | **GET** /v1/search | |

# **universalSearch**
> Array<SearchResult> universalSearch()


### Example

```typescript
import {
    SearchApi,
    Configuration
} from '@chainvue/sdk';

const configuration = new Configuration();
const apiInstance = new SearchApi(configuration);

let q: string; // (default to undefined)

const { status, data } = await apiInstance.universalSearch(
    q
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **q** | [**string**] |  | defaults to undefined|


### Return type

**Array<SearchResult>**

### Authorization

[api_key](../README.md#api_key)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**200** | Search results |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

