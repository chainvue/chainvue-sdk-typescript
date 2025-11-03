# BlocksApi

All URIs are relative to *http://localhost*

|Method | HTTP request | Description|
|------------- | ------------- | -------------|
|[**getBlock**](#getblock) | **GET** /v1/blocks/{height_or_hash} | |
|[**getLatestBlock**](#getlatestblock) | **GET** /v1/blocks/latest | |

# **getBlock**
> Block getBlock()


### Example

```typescript
import {
    BlocksApi,
    Configuration
} from '@chainvue/sdk';

const configuration = new Configuration();
const apiInstance = new BlocksApi(configuration);

let heightOrHash: string; //Block height (numeric) or block hash (default to undefined)
let chainId: string; // (optional) (default to undefined)

const { status, data } = await apiInstance.getBlock(
    heightOrHash,
    chainId
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **heightOrHash** | [**string**] | Block height (numeric) or block hash | defaults to undefined|
| **chainId** | [**string**] |  | (optional) defaults to undefined|


### Return type

**Block**

### Authorization

[api_key](../README.md#api_key)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**200** | Block found |  -  |
|**404** | Block not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **getLatestBlock**
> Block getLatestBlock()


### Example

```typescript
import {
    BlocksApi,
    Configuration
} from '@chainvue/sdk';

const configuration = new Configuration();
const apiInstance = new BlocksApi(configuration);

let chainId: string; // (optional) (default to undefined)

const { status, data } = await apiInstance.getLatestBlock(
    chainId
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **chainId** | [**string**] |  | (optional) defaults to undefined|


### Return type

**Block**

### Authorization

[api_key](../README.md#api_key)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**200** | Latest block found |  -  |
|**404** | No blocks found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

