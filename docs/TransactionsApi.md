# TransactionsApi

All URIs are relative to *http://localhost*

|Method | HTTP request | Description|
|------------- | ------------- | -------------|
|[**getMempool**](#getmempool) | **GET** /v1/transactions/mempool | |
|[**getTransaction**](#gettransaction) | **GET** /v1/transactions/{txid} | |
|[**listTransactions**](#listtransactions) | **GET** /v1/transactions | |

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

# **listTransactions**
> ListTransactions200Response listTransactions()


### Example

```typescript
import {
    TransactionsApi,
    Configuration
} from '@chainvue/sdk';

const configuration = new Configuration();
const apiInstance = new TransactionsApi(configuration);

let chainId: string; // (optional) (default to undefined)
let limit: number; // (optional) (default to undefined)
let offset: number; // (optional) (default to undefined)
let sort: string; // (optional) (default to undefined)
let minBlockHeight: number; // (optional) (default to undefined)
let maxBlockHeight: number; // (optional) (default to undefined)
let minTimestamp: number; // (optional) (default to undefined)
let maxTimestamp: number; // (optional) (default to undefined)
let address: string; // (optional) (default to undefined)
let includeCount: boolean; // (optional) (default to undefined)

const { status, data } = await apiInstance.listTransactions(
    chainId,
    limit,
    offset,
    sort,
    minBlockHeight,
    maxBlockHeight,
    minTimestamp,
    maxTimestamp,
    address,
    includeCount
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **chainId** | [**string**] |  | (optional) defaults to undefined|
| **limit** | [**number**] |  | (optional) defaults to undefined|
| **offset** | [**number**] |  | (optional) defaults to undefined|
| **sort** | [**string**] |  | (optional) defaults to undefined|
| **minBlockHeight** | [**number**] |  | (optional) defaults to undefined|
| **maxBlockHeight** | [**number**] |  | (optional) defaults to undefined|
| **minTimestamp** | [**number**] |  | (optional) defaults to undefined|
| **maxTimestamp** | [**number**] |  | (optional) defaults to undefined|
| **address** | [**string**] |  | (optional) defaults to undefined|
| **includeCount** | [**boolean**] |  | (optional) defaults to undefined|


### Return type

**ListTransactions200Response**

### Authorization

[api_key](../README.md#api_key)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**200** | List of transactions |  -  |
|**400** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

