# AddressesApi

All URIs are relative to *http://localhost*

|Method | HTTP request | Description|
|------------- | ------------- | -------------|
|[**getAddress**](#getaddress) | **GET** /v1/addresses/{address} | |
|[**getAddressBalance**](#getaddressbalance) | **GET** /v1/addresses/{address}/balance | |
|[**getAddressTransactions**](#getaddresstransactions) | **GET** /v1/addresses/{address}/transactions | |
|[**getRichlist**](#getrichlist) | **GET** /v1/addresses/richlist | |

# **getAddress**
> Address getAddress()


### Example

```typescript
import {
    AddressesApi,
    Configuration
} from '@chainvue/sdk';

const configuration = new Configuration();
const apiInstance = new AddressesApi(configuration);

let address: string; //Blockchain address (default to undefined)
let chainId: string; // (optional) (default to undefined)

const { status, data } = await apiInstance.getAddress(
    address,
    chainId
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **address** | [**string**] | Blockchain address | defaults to undefined|
| **chainId** | [**string**] |  | (optional) defaults to undefined|


### Return type

**Address**

### Authorization

[api_key](../README.md#api_key)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**200** | Address information |  -  |
|**404** | Address not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **getAddressBalance**
> string getAddressBalance()


### Example

```typescript
import {
    AddressesApi,
    Configuration
} from '@chainvue/sdk';

const configuration = new Configuration();
const apiInstance = new AddressesApi(configuration);

let address: string; //Blockchain address (default to undefined)
let chainId: string; // (optional) (default to undefined)

const { status, data } = await apiInstance.getAddressBalance(
    address,
    chainId
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **address** | [**string**] | Blockchain address | defaults to undefined|
| **chainId** | [**string**] |  | (optional) defaults to undefined|


### Return type

**string**

### Authorization

[api_key](../README.md#api_key)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: text/plain


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**200** | Address balance |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **getAddressTransactions**
> Array<Transaction> getAddressTransactions()


### Example

```typescript
import {
    AddressesApi,
    Configuration
} from '@chainvue/sdk';

const configuration = new Configuration();
const apiInstance = new AddressesApi(configuration);

let address: string; //Blockchain address (default to undefined)
let chainId: string; // (optional) (default to undefined)
let limit: number; // (optional) (default to undefined)
let offset: number; // (optional) (default to undefined)
let includeCount: boolean; // (optional) (default to undefined)

const { status, data } = await apiInstance.getAddressTransactions(
    address,
    chainId,
    limit,
    offset,
    includeCount
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **address** | [**string**] | Blockchain address | defaults to undefined|
| **chainId** | [**string**] |  | (optional) defaults to undefined|
| **limit** | [**number**] |  | (optional) defaults to undefined|
| **offset** | [**number**] |  | (optional) defaults to undefined|
| **includeCount** | [**boolean**] |  | (optional) defaults to undefined|


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
|**200** | Address transactions |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **getRichlist**
> PaginatedApiResponseAddress getRichlist()


### Example

```typescript
import {
    AddressesApi,
    Configuration
} from '@chainvue/sdk';

const configuration = new Configuration();
const apiInstance = new AddressesApi(configuration);

let chainId: string; // (optional) (default to undefined)
let limit: number; // (optional) (default to undefined)
let offset: number; // (optional) (default to undefined)
let includeCount: boolean; // (optional) (default to undefined)

const { status, data } = await apiInstance.getRichlist(
    chainId,
    limit,
    offset,
    includeCount
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **chainId** | [**string**] |  | (optional) defaults to undefined|
| **limit** | [**number**] |  | (optional) defaults to undefined|
| **offset** | [**number**] |  | (optional) defaults to undefined|
| **includeCount** | [**boolean**] |  | (optional) defaults to undefined|


### Return type

**PaginatedApiResponseAddress**

### Authorization

[api_key](../README.md#api_key)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**200** | Top addresses by balance |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

