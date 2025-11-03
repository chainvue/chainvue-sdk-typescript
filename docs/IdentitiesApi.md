# IdentitiesApi

All URIs are relative to *http://localhost*

|Method | HTTP request | Description|
|------------- | ------------- | -------------|
|[**getIdentity**](#getidentity) | **GET** /v1/identities/{name_or_address} | |
|[**searchIdentities**](#searchidentities) | **GET** /v1/identities | |

# **getIdentity**
> Identity getIdentity()


### Example

```typescript
import {
    IdentitiesApi,
    Configuration
} from '@chainvue/sdk';

const configuration = new Configuration();
const apiInstance = new IdentitiesApi(configuration);

let nameOrAddress: string; //Identity name (e.g., Mike@) or i-address (default to undefined)
let chainId: string; // (optional) (default to undefined)

const { status, data } = await apiInstance.getIdentity(
    nameOrAddress,
    chainId
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **nameOrAddress** | [**string**] | Identity name (e.g., Mike@) or i-address | defaults to undefined|
| **chainId** | [**string**] |  | (optional) defaults to undefined|


### Return type

**Identity**

### Authorization

[api_key](../README.md#api_key)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**200** | Identity found |  -  |
|**404** | Identity not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **searchIdentities**
> Array<Identity> searchIdentities()


### Example

```typescript
import {
    IdentitiesApi,
    Configuration
} from '@chainvue/sdk';

const configuration = new Configuration();
const apiInstance = new IdentitiesApi(configuration);

let chainId: string; // (optional) (default to undefined)
let search: string; // (optional) (default to undefined)

const { status, data } = await apiInstance.searchIdentities(
    chainId,
    search
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **chainId** | [**string**] |  | (optional) defaults to undefined|
| **search** | [**string**] |  | (optional) defaults to undefined|


### Return type

**Array<Identity>**

### Authorization

[api_key](../README.md#api_key)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**200** | List of identities |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

