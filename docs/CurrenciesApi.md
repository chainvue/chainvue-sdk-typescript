# CurrenciesApi

All URIs are relative to *http://localhost*

|Method | HTTP request | Description|
|------------- | ------------- | -------------|
|[**getCurrency**](#getcurrency) | **GET** /v1/currencies/{currency_id} | |
|[**listCurrencies**](#listcurrencies) | **GET** /v1/currencies | |

# **getCurrency**
> CurrencyDetail getCurrency()


### Example

```typescript
import {
    CurrenciesApi,
    Configuration
} from '@chainvue/sdk';

const configuration = new Configuration();
const apiInstance = new CurrenciesApi(configuration);

let currencyId: string; //Currency ID (default to undefined)
let chainId: string; // (optional) (default to undefined)

const { status, data } = await apiInstance.getCurrency(
    currencyId,
    chainId
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **currencyId** | [**string**] | Currency ID | defaults to undefined|
| **chainId** | [**string**] |  | (optional) defaults to undefined|


### Return type

**CurrencyDetail**

### Authorization

[api_key](../README.md#api_key)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**200** | Currency details with reserves |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **listCurrencies**
> PaginatedApiResponse listCurrencies()


### Example

```typescript
import {
    CurrenciesApi,
    Configuration
} from '@chainvue/sdk';

const configuration = new Configuration();
const apiInstance = new CurrenciesApi(configuration);

let chainId: string; // (optional) (default to undefined)
let limit: number; // (optional) (default to undefined)
let offset: number; // (optional) (default to undefined)
let search: string; // (optional) (default to undefined)

const { status, data } = await apiInstance.listCurrencies(
    chainId,
    limit,
    offset,
    search
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **chainId** | [**string**] |  | (optional) defaults to undefined|
| **limit** | [**number**] |  | (optional) defaults to undefined|
| **offset** | [**number**] |  | (optional) defaults to undefined|
| **search** | [**string**] |  | (optional) defaults to undefined|


### Return type

**PaginatedApiResponse**

### Authorization

[api_key](../README.md#api_key)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**200** | List of currencies |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

