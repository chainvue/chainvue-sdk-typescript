# CurrencyDetail


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**chain_id** | **string** |  | [default to undefined]
**created_at** | **string** |  | [optional] [default to undefined]
**created_block** | **number** |  | [optional] [default to undefined]
**created_txid** | **string** |  | [optional] [default to undefined]
**currency_id** | **string** |  | [default to undefined]
**currency_type** | **string** |  | [optional] [default to undefined]
**initial_supply** | **string** |  | [optional] [default to undefined]
**is_pbaas_chain** | **boolean** |  | [optional] [default to undefined]
**is_token** | **boolean** |  | [optional] [default to undefined]
**launch_system_id** | **string** |  | [optional] [default to undefined]
**name** | **string** |  | [default to undefined]
**_options** | **number** |  | [default to undefined]
**parent_currency_id** | **string** |  | [optional] [default to undefined]
**proof_protocol** | **number** |  | [optional] [default to undefined]
**raw_data** | **any** |  | [optional] [default to undefined]
**version** | **number** |  | [optional] [default to undefined]
**reserves** | [**Array&lt;CurrencyReserve&gt;**](CurrencyReserve.md) |  | [default to undefined]

## Example

```typescript
import { CurrencyDetail } from '@chainvue/sdk';

const instance: CurrencyDetail = {
    chain_id,
    created_at,
    created_block,
    created_txid,
    currency_id,
    currency_type,
    initial_supply,
    is_pbaas_chain,
    is_token,
    launch_system_id,
    name,
    _options,
    parent_currency_id,
    proof_protocol,
    raw_data,
    version,
    reserves,
};
```

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)
