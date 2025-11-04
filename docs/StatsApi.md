# StatsApi

All URIs are relative to *http://localhost*

|Method | HTTP request | Description|
|------------- | ------------- | -------------|
|[**getIdentityCreation**](#getidentitycreation) | **GET** /v1/stats/identity-creation | |
|[**getNetworkStats**](#getnetworkstats) | **GET** /v1/stats | |
|[**getTxVolume**](#gettxvolume) | **GET** /v1/stats/tx-volume | |

# **getIdentityCreation**
> Array<IdentityActivity> getIdentityCreation()


### Example

```typescript
import {
    StatsApi,
    Configuration
} from '@chainvue/sdk';

const configuration = new Configuration();
const apiInstance = new StatsApi(configuration);

let chainId: string; // (optional) (default to undefined)

const { status, data } = await apiInstance.getIdentityCreation(
    chainId
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **chainId** | [**string**] |  | (optional) defaults to undefined|


### Return type

**Array<IdentityActivity>**

### Authorization

[api_key](../README.md#api_key)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**200** | Daily identity creation and update count for last 30 days |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **getNetworkStats**
> NetworkStats getNetworkStats()


### Example

```typescript
import {
    StatsApi,
    Configuration
} from '@chainvue/sdk';

const configuration = new Configuration();
const apiInstance = new StatsApi(configuration);

let chainId: string; // (optional) (default to undefined)

const { status, data } = await apiInstance.getNetworkStats(
    chainId
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **chainId** | [**string**] |  | (optional) defaults to undefined|


### Return type

**NetworkStats**

### Authorization

[api_key](../README.md#api_key)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**200** | Network statistics |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **getTxVolume**
> Array<DailyVolume> getTxVolume()


### Example

```typescript
import {
    StatsApi,
    Configuration
} from '@chainvue/sdk';

const configuration = new Configuration();
const apiInstance = new StatsApi(configuration);

let chainId: string; // (optional) (default to undefined)

const { status, data } = await apiInstance.getTxVolume(
    chainId
);
```

### Parameters

|Name | Type | Description  | Notes|
|------------- | ------------- | ------------- | -------------|
| **chainId** | [**string**] |  | (optional) defaults to undefined|


### Return type

**Array<DailyVolume>**

### Authorization

[api_key](../README.md#api_key)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**200** | Daily transaction volume for last 7 days |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

