# HealthStatus


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**app_database** | **string** |  | [default to undefined]
**blockchain_database** | **string** |  | [default to undefined]
**redis** | **string** |  | [default to undefined]
**status** | **string** |  | [default to undefined]
**timestamp** | **number** |  | [default to undefined]
**uptime_seconds** | **number** |  | [optional] [default to undefined]
**version** | **string** |  | [default to undefined]

## Example

```typescript
import { HealthStatus } from '@chainvue/sdk';

const instance: HealthStatus = {
    app_database,
    blockchain_database,
    redis,
    status,
    timestamp,
    uptime_seconds,
    version,
};
```

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)
