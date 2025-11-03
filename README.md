# ChainVue TypeScript SDK

Official TypeScript/JavaScript SDK for the ChainVue Blockchain API.

[![npm version](https://badge.fury.io/js/%40chainvue%2Fsdk.svg)](https://www.npmjs.com/package/@chainvue/sdk)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

## Installation

This package is published to GitHub Packages. You'll need to configure npm to use GitHub Packages for the `@chainvue` scope:

### 1. Configure npm Registry

Create or edit `~/.npmrc` (or `.npmrc` in your project root):

```bash
@chainvue:registry=https://npm.pkg.github.com
```

### 2. Install Package

```bash
npm install @chainvue/sdk
# or
yarn add @chainvue/sdk
# or
pnpm add @chainvue/sdk
```

### Authentication (if needed)

If the package requires authentication, add your GitHub Personal Access Token to `~/.npmrc`:

```
//npm.pkg.github.com/:_authToken=YOUR_GITHUB_TOKEN
```

## Quick Start

```typescript
import { ChainVueAPI } from '@chainvue/sdk';

// Initialize the client
const api = new ChainVueAPI({
  basePath: 'https://api.chainvue.io',
  apiKey: 'va_your_api_key_here'
});

// Get the latest block
const block = await api.getLatestBlock();
console.log(`Latest block: #${block.data.height}`);

// Query a transaction
const tx = await api.getTransaction('txid_here');
console.log(tx.data);

// Check address balance
const address = await api.getAddressBalance('RXL3YXG2ceaB6C5hfJcN4fvmLH2C34knhA');
console.log(`Balance: ${address.data.balance} VRSC`);
```

## Features

- ✅ **Full TypeScript support** with auto-generated types
- ✅ **Promise-based API** using async/await
- ✅ **Automatic retries** and error handling
- ✅ **Multi-chain support** (VRSC, VRSCTEST)
- ✅ **Complete API coverage** for all endpoints
- ✅ **IDE autocomplete** and IntelliSense

## API Reference

### Blocks

```typescript
// Get latest block
const latest = await api.getLatestBlock();

// Get block by height or hash
const block = await api.getBlock('12345');
const block = await api.getBlock('00000000000a1b2c3d...');
```

### Transactions

```typescript
// Get transaction
const tx = await api.getTransaction('txid');

// Get mempool
const mempool = await api.getMempool();
```

### Addresses

```typescript
// Get address info
const address = await api.getAddress('RXL3YXG2ceaB6C5hfJcN4fvmLH2C34knhA');

// Get address balance
const balance = await api.getAddressBalance('RXL3YXG2ceaB6C5hfJcN4fvmLH2C34knhA');

// Get address transactions
const txs = await api.getAddressTransactions('RXL3YXG2ceaB6C5hfJcN4fvmLH2C34knhA', {
  page: 1,
  limit: 20
});
```

### Identities (VerusID)

```typescript
// Get identity
const identity = await api.getIdentity('myid@');

// Search identities
const results = await api.searchIdentities('search_term');
```

### Chains

```typescript
// List supported chains
const chains = await api.listChains();
```

### Search

```typescript
// Universal search (finds blocks, txs, addresses, identities)
const result = await api.universalSearch('query');
```

## Configuration

```typescript
import { ChainVueAPI } from '@chainvue/sdk';

const api = new ChainVueAPI({
  basePath: 'https://api.chainvue.io',  // API base URL
  apiKey: 'va_your_api_key',             // Your API key
  timeout: 30000,                         // Request timeout (ms)
  headers: {                              // Custom headers
    'X-Custom-Header': 'value'
  }
});
```

## Error Handling

```typescript
import { ChainVueAPI, ApiError } from '@chainvue/sdk';

const api = new ChainVueAPI({
  basePath: 'https://api.chainvue.io',
  apiKey: 'va_your_api_key'
});

try {
  const block = await api.getBlock('invalid');
} catch (error) {
  if (error instanceof ApiError) {
    console.error(`API Error: ${error.status} - ${error.message}`);
  } else {
    console.error('Unexpected error:', error);
  }
}
```

## Examples

### Monitor Address for Payments

```typescript
async function monitorPayment(address: string, expectedAmount: number) {
  const api = new ChainVueAPI({
    basePath: 'https://api.chainvue.io',
    apiKey: process.env.CHAINVUE_API_KEY!
  });

  while (true) {
    const balance = await api.getAddressBalance(address);

    if (balance.data.balance >= expectedAmount) {
      console.log('Payment received!');
      return true;
    }

    await new Promise(resolve => setTimeout(resolve, 10000)); // Check every 10s
  }
}
```

### Get Transaction Confirmations

```typescript
async function getConfirmations(txid: string) {
  const api = new ChainVueAPI({
    basePath: 'https://api.chainvue.io',
    apiKey: process.env.CHAINVUE_API_KEY!
  });

  const tx = await api.getTransaction(txid);
  const latestBlock = await api.getLatestBlock();

  return latestBlock.data.height - tx.data.height;
}
```

## Multi-Chain Support

```typescript
// Query mainnet
const vrscBalance = await api.getAddressBalance(address, {
  chainId: 'VRSC'
});

// Query testnet
const testBalance = await api.getAddressBalance(address, {
  chainId: 'VRSCTEST'
});
```

## Development

This SDK is auto-generated from the ChainVue OpenAPI specification.

**Do not manually edit the generated files.** Changes will be overwritten on the next generation.

## Links

- [API Documentation](https://api.chainvue.io/swagger-ui)
- [ChainVue Website](https://chainvue.io)
- [GitHub Repository](https://github.com/chainvue/chainvue-sdk-typescript)
- [Report Issues](https://github.com/chainvue/chainvue-sdk-typescript/issues)

## License

MIT License - see [LICENSE](LICENSE) file for details.

## Support

- Email: support@chainvue.io
- Discord: [Join our community](https://discord.gg/chainvue)
- Documentation: https://docs.chainvue.io
