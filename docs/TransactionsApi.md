# TransactionsApi

All URIs are relative to *http://localhost*

|Method | HTTP request | Description|
|------------- | ------------- | -------------|
|[**getMempool**](#getmempool) | **GET** /v1/transactions/mempool | |
|[**getTransaction**](#gettransaction) | **GET** /v1/transactions/{txid} | |

# **getMempool**
> Array<Transaction> getMempool()


### Example

```typescript
import {
    TransactionsApi,
    Configuration
} from '@chainvue/sdk';

const configuration = new Configuration();
const apiInstance = new TransactionsApi(configuration);

let chainId: string; // (optional) (default to undefined)

const { status, data } = await apiInstance.getMempool(
    chainId
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **chainId** | [**string**] |  | (optional) defaults to undefined|


### Return type

**Array<Transaction>**

### Authorization

[api_key](../README.md#api_key)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**200** | Mempool transactions |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **getTransaction**
> Transaction getTransaction()


### Example

```typescript
import {
    TransactionsApi,
    Configuration
} from '@chainvue/sdk';

const configuration = new Configuration();
const apiInstance = new TransactionsApi(configuration);

let txid: string; //Transaction ID (default to undefined)
let chainId: string; // (optional) (default to undefined)

const { status, data } = await apiInstance.getTransaction(
    txid,
    chainId
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **txid** | [**string**] | Transaction ID | defaults to undefined|
| **chainId** | [**string**] |  | (optional) defaults to undefined|


### Return type

**Transaction**

### Authorization

[api_key](../README.md#api_key)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**200** | Transaction found |  -  |
|**404** | Transaction not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

