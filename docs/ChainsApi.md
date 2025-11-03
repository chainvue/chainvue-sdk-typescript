# ChainsApi

All URIs are relative to *http://localhost*

|Method | HTTP request | Description|
|------------- | ------------- | -------------|
|[**listChains**](#listchains) | **GET** /v1/chains | |

# **listChains**
> Array<Chain> listChains()


### Example

```typescript
import {
    ChainsApi,
    Configuration
} from '@chainvue/sdk';

const configuration = new Configuration();
const apiInstance = new ChainsApi(configuration);

const { status, data } = await apiInstance.listChains();
```

### Parameters
This endpoint does not have any parameters.


### Return type

**Array<Chain>**

### Authorization

[api_key](../README.md#api_key)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
|**200** | List of indexed chains |  -  |
|**404** | No chains found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

