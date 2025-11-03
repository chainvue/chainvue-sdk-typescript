## @chainvue/sdk@v0.1.0-test5

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
npm install @chainvue/sdk@v0.1.0-test5 --save
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
*BlocksApi* | [**getBlock**](docs/BlocksApi.md#getblock) | **GET** /v1/blocks/{height_or_hash} | 
*BlocksApi* | [**getLatestBlock**](docs/BlocksApi.md#getlatestblock) | **GET** /v1/blocks/latest | 
*ChainsApi* | [**listChains**](docs/ChainsApi.md#listchains) | **GET** /v1/chains | 
*HealthApi* | [**apiStatus**](docs/HealthApi.md#apistatus) | **GET** /v1/status | 
*HealthApi* | [**healthCheck**](docs/HealthApi.md#healthcheck) | **GET** /health | 
*IdentitiesApi* | [**getIdentity**](docs/IdentitiesApi.md#getidentity) | **GET** /v1/identities/{name_or_address} | 
*IdentitiesApi* | [**searchIdentities**](docs/IdentitiesApi.md#searchidentities) | **GET** /v1/identities | 
*SearchApi* | [**universalSearch**](docs/SearchApi.md#universalsearch) | **GET** /v1/search | 
*TransactionsApi* | [**getMempool**](docs/TransactionsApi.md#getmempool) | **GET** /v1/transactions/mempool | 
*TransactionsApi* | [**getTransaction**](docs/TransactionsApi.md#gettransaction) | **GET** /v1/transactions/{txid} | 


### Documentation For Models

 - [Address](docs/Address.md)
 - [ApiResponse](docs/ApiResponse.md)
 - [ApiResponseMeta](docs/ApiResponseMeta.md)
 - [Block](docs/Block.md)
 - [Chain](docs/Chain.md)
 - [Currency](docs/Currency.md)
 - [HealthStatus](docs/HealthStatus.md)
 - [Identity](docs/Identity.md)
 - [ResponseMeta](docs/ResponseMeta.md)
 - [SearchResult](docs/SearchResult.md)
 - [Transaction](docs/Transaction.md)


<a id="documentation-for-authorization"></a>
## Documentation For Authorization


Authentication schemes defined for the API:
<a id="api_key"></a>
### api_key

- **Type**: Bearer authentication (API Key)

