# CurrenciesApi

All URIs are relative to *http://localhost*

|Method | HTTP request | Description|
|------------- | ------------- | -------------|
|[**getCurrency**](#getcurrency) | **GET** /v1/currencies/{currency_id} | Get currency details|
|[**listCurrencies**](#listcurrencies) | **GET** /v1/currencies | List all currencies|

# **getCurrency**
> ApiResponseCurrencyDetail getCurrency()

Retrieve detailed information about a specific currency including all its reserve currencies and weights. Returns the currency definition along with reserve backing information for fractional reserve currencies.

### Example

```typescript
import {
    CurrenciesApi,
    Configuration
} from '@chainvue/sdk';

const configuration = new Configuration();
const apiInstance = new CurrenciesApi(configuration);

let currencyId: string; //Unique identifier for the currency (i-address format) (default to undefined)
let chainId: string; // (optional) (default to undefined)

const { status, data } = await apiInstance.getCurrency(
    currencyId,
    chainId
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **currencyId** | [**string**] | Unique identifier for the currency (i-address format) | defaults to undefined|
| **chainId** | [**string**] |  | (optional) defaults to undefined|


### Return type

**ApiResponseCurrencyDetail**

### Authorization

[api_key](../README.md#api_key)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**200** | Successfully retrieved currency details with reserves |  -  |
|**400** | Bad request - invalid currency ID format |  -  |
|**401** | Unauthorized - invalid or missing API key |  -  |
|**404** | Currency not found |  -  |
|**500** | Internal server error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **listCurrencies**
> PaginatedApiResponseCurrency listCurrencies()

Retrieve a paginated list of all currencies for a specific chain. Supports optional search filtering by currency name with case-insensitive matching. Results are cached for 60 seconds.

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

**PaginatedApiResponseCurrency**

### Authorization

[api_key](../README.md#api_key)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**200** | Successfully retrieved list of currencies |  -  |
|**400** | Bad request - invalid parameters |  -  |
|**401** | Unauthorized - invalid or missing API key |  -  |
|**500** | Internal server error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

