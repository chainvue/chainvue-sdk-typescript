## @chainvue/sdk@v0.2.0

This generator creates TypeScript/JavaScript client that utilizes [axios](https://github.com/axios/axios). The generated Node module can be used in the following environments:

Environment
* Node.js
* Webpack
* Browserify

Language level
* ES5 - you must have a Promises/A+ library installed
* ES6

Module system
* CommonJS
* ES6 module system

It can be used in both TypeScript and JavaScript. In TypeScript, the definition will be automatically resolved via `package.json`. ([Reference](https://www.typescriptlang.org/docs/handbook/declaration-files/consumption.html))

### Building

To build and compile the typescript sources to javascript use:
```
npm install
npm run build
```

### Publishing

First build the package then run `npm publish`

### Consuming

navigate to the folder of your consuming project and run one of the following commands.

_published:_

```
npm install @chainvue/sdk@v0.2.0 --save
```

_unPublished (not recommended):_

```
npm install PATH_TO_GENERATED_PACKAGE --save
```

### Documentation for API Endpoints

All URIs are relative to *http://localhost*

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*AddressesApi* | [**getAddress**](docs/AddressesApi.md#getaddress) | **GET** /v1/addresses/{address} | 
*AddressesApi* | [**getAddressBalance**](docs/AddressesApi.md#getaddressbalance) | **GET** /v1/addresses/{address}/balance | 
*AddressesApi* | [**getAddressTransactions**](docs/AddressesApi.md#getaddresstransactions) | **GET** /v1/addresses/{address}/transactions | 
*AddressesApi* | [**getRichlist**](docs/AddressesApi.md#getrichlist) | **GET** /v1/addresses/richlist | 
*BlocksApi* | [**getBlock**](docs/BlocksApi.md#getblock) | **GET** /v1/blocks/{height_or_hash} | 
*BlocksApi* | [**getLatestBlock**](docs/BlocksApi.md#getlatestblock) | **GET** /v1/blocks/latest | 
*BlocksApi* | [**listBlocks**](docs/BlocksApi.md#listblocks) | **GET** /v1/blocks | 
*ChainsApi* | [**listChains**](docs/ChainsApi.md#listchains) | **GET** /v1/chains | 
*CurrenciesApi* | [**getCurrency**](docs/CurrenciesApi.md#getcurrency) | **GET** /v1/currencies/{currency_id} | Get currency details
*CurrenciesApi* | [**listCurrencies**](docs/CurrenciesApi.md#listcurrencies) | **GET** /v1/currencies | List all currencies
*HealthApi* | [**apiStatus**](docs/HealthApi.md#apistatus) | **GET** /v1/status | 
*HealthApi* | [**healthCheck**](docs/HealthApi.md#healthcheck) | **GET** /health | 
*IdentitiesApi* | [**getIdentity**](docs/IdentitiesApi.md#getidentity) | **GET** /v1/identities/{name_or_address} | 
*IdentitiesApi* | [**searchIdentities**](docs/IdentitiesApi.md#searchidentities) | **GET** /v1/identities | 
*SearchApi* | [**universalSearch**](docs/SearchApi.md#universalsearch) | **GET** /v1/search | 
*StatsApi* | [**getIdentityCreation**](docs/StatsApi.md#getidentitycreation) | **GET** /v1/stats/identity-creation | 
*StatsApi* | [**getNetworkStats**](docs/StatsApi.md#getnetworkstats) | **GET** /v1/stats | 
*StatsApi* | [**getTxVolume**](docs/StatsApi.md#gettxvolume) | **GET** /v1/stats/tx-volume | 
*TransactionsApi* | [**getMempool**](docs/TransactionsApi.md#getmempool) | **GET** /v1/transactions/mempool | 
*TransactionsApi* | [**getTransaction**](docs/TransactionsApi.md#gettransaction) | **GET** /v1/transactions/{txid} | 
*TransactionsApi* | [**listTransactions**](docs/TransactionsApi.md#listtransactions) | **GET** /v1/transactions | 


### Documentation For Models

 - [Address](docs/Address.md)
 - [ApiResponseAddress](docs/ApiResponseAddress.md)
 - [ApiResponseAddressData](docs/ApiResponseAddressData.md)
 - [ApiResponseAddressMeta](docs/ApiResponseAddressMeta.md)
 - [ApiResponseBlock](docs/ApiResponseBlock.md)
 - [ApiResponseChain](docs/ApiResponseChain.md)
 - [ApiResponseChainData](docs/ApiResponseChainData.md)
 - [ApiResponseCurrency](docs/ApiResponseCurrency.md)
 - [ApiResponseCurrencyData](docs/ApiResponseCurrencyData.md)
 - [ApiResponseCurrencyDetail](docs/ApiResponseCurrencyDetail.md)
 - [ApiResponseCurrencyDetailData](docs/ApiResponseCurrencyDetailData.md)
 - [ApiResponseHealthStatus](docs/ApiResponseHealthStatus.md)
 - [ApiResponseHealthStatusData](docs/ApiResponseHealthStatusData.md)
 - [ApiResponseIdentity](docs/ApiResponseIdentity.md)
 - [ApiResponseIdentityData](docs/ApiResponseIdentityData.md)
 - [ApiResponseNetworkStats](docs/ApiResponseNetworkStats.md)
 - [ApiResponseNetworkStatsData](docs/ApiResponseNetworkStatsData.md)
 - [ApiResponseSearchResult](docs/ApiResponseSearchResult.md)
 - [ApiResponseSearchResultData](docs/ApiResponseSearchResultData.md)
 - [ApiResponseString](docs/ApiResponseString.md)
 - [ApiResponseTransaction](docs/ApiResponseTransaction.md)
 - [ApiResponseVecAddress](docs/ApiResponseVecAddress.md)
 - [ApiResponseVecBlock](docs/ApiResponseVecBlock.md)
 - [ApiResponseVecChain](docs/ApiResponseVecChain.md)
 - [ApiResponseVecCurrency](docs/ApiResponseVecCurrency.md)
 - [ApiResponseVecIdentity](docs/ApiResponseVecIdentity.md)
 - [ApiResponseVecSearchResult](docs/ApiResponseVecSearchResult.md)
 - [ApiResponseVecTransaction](docs/ApiResponseVecTransaction.md)
 - [Block](docs/Block.md)
 - [Chain](docs/Chain.md)
 - [Currency](docs/Currency.md)
 - [CurrencyDetail](docs/CurrencyDetail.md)
 - [CurrencyReserve](docs/CurrencyReserve.md)
 - [DailyVolume](docs/DailyVolume.md)
 - [HealthStatus](docs/HealthStatus.md)
 - [Identity](docs/Identity.md)
 - [IdentityActivity](docs/IdentityActivity.md)
 - [ListBlocks200Response](docs/ListBlocks200Response.md)
 - [ListBlocks200ResponseDataInner](docs/ListBlocks200ResponseDataInner.md)
 - [ListBlocks200ResponseMeta](docs/ListBlocks200ResponseMeta.md)
 - [ListBlocks200ResponseMetaPagination](docs/ListBlocks200ResponseMetaPagination.md)
 - [ListTransactions200Response](docs/ListTransactions200Response.md)
 - [ListTransactions200ResponseDataInner](docs/ListTransactions200ResponseDataInner.md)
 - [NetworkStats](docs/NetworkStats.md)
 - [PaginatedApiResponseAddress](docs/PaginatedApiResponseAddress.md)
 - [PaginatedApiResponseBlock](docs/PaginatedApiResponseBlock.md)
 - [PaginatedApiResponseCurrency](docs/PaginatedApiResponseCurrency.md)
 - [PaginatedApiResponseTransaction](docs/PaginatedApiResponseTransaction.md)
 - [PaginatedResponseMeta](docs/PaginatedResponseMeta.md)
 - [PaginationMeta](docs/PaginationMeta.md)
 - [ResponseMeta](docs/ResponseMeta.md)
 - [SearchResult](docs/SearchResult.md)
 - [Transaction](docs/Transaction.md)


<a id="documentation-for-authorization"></a>
## Documentation For Authorization


Authentication schemes defined for the API:
<a id="api_key"></a>
### api_key

- **Type**: Bearer authentication (API Key)

