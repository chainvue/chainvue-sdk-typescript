# ChainVue TypeScript SDK

> Official TypeScript/JavaScript SDK for the ChainVue Blockchain API

[![npm version](https://img.shields.io/npm/v/@chainvue/sdk)](https://www.npmjs.com/package/@chainvue/sdk)
[![npm downloads](https://img.shields.io/npm/dm/@chainvue/sdk)](https://www.npmjs.com/package/@chainvue/sdk)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

Access multi-chain blockchain data for Verus Protocol with full TypeScript support, auto-generated from OpenAPI specifications.

## Features

- ✅ **Full Type Safety** - Auto-generated TypeScript definitions
- ✅ **Promise-Based** - Modern async/await API
- ✅ **Multi-Chain Support** - Query different blockchains with chain_id
- ✅ **Complete Coverage** - All ChainVue API endpoints included
- ✅ **IDE Autocomplete** - IntelliSense support out of the box
- ✅ **Lightweight** - Only dependency is axios

## Installation

```bash
npm install @chainvue/sdk
```

```bash
yarn add @chainvue/sdk
```

```bash
pnpm add @chainvue/sdk
```

## Quick Start

```typescript
import { Configuration, BlocksApi } from '@chainvue/sdk';

// Configure the SDK
const config = new Configuration({
  basePath: 'https://api.chainvue.io'
});

// Create API instance
const blocksApi = new BlocksApi(config);

// Get latest block
const response = await blocksApi.getLatestBlock();
console.log(response.data);
```

## Usage Examples

### Blocks

```typescript
import { Configuration, BlocksApi } from '@chainvue/sdk';

const config = new Configuration({
  basePath: 'https://api.chainvue.io'
});
const blocksApi = new BlocksApi(config);

// Get latest block
const latest = await blocksApi.getLatestBlock();
console.log(`Latest block: #${latest.data.data?.height}`);

// Get block by height
const block = await blocksApi.getBlock('4500000');
console.log(block.data);

// Get block by hash
const blockByHash = await blocksApi.getBlock('0000000000000abc...');
console.log(blockByHash.data);
```

### Transactions

```typescript
import { Configuration, TransactionsApi } from '@chainvue/sdk';

const config = new Configuration({
  basePath: 'https://api.chainvue.io'
});
const txApi = new TransactionsApi(config);

// Get transaction by txid
const tx = await txApi.getTransaction('abc123...');
console.log(tx.data);

// Get mempool transactions
const mempool = await txApi.getMempool();
console.log(`Mempool has ${mempool.data.data?.length} pending transactions`);
```

### Addresses

```typescript
import { Configuration, AddressesApi } from '@chainvue/sdk';

const config = new Configuration({
  basePath: 'https://api.chainvue.io'
});
const addressApi = new AddressesApi(config);

// Get address information
const address = await addressApi.getAddress('RCG8KwJNDVwpUBcdoa6AoHqHVJsA1uMYMR');
console.log(address.data);

// Get address balance
const balance = await addressApi.getAddressBalance('RCG8KwJNDVwpUBcdoa6AoHqHVJsA1uMYMR');
console.log(`Balance: ${balance.data.data?.balance} VRSC`);

// Get address transactions
const txs = await addressApi.getAddressTransactions('RCG8KwJNDVwpUBcdoa6AoHqHVJsA1uMYMR');
console.log(txs.data);
```

### Identities (VerusID)

```typescript
import { Configuration, IdentitiesApi } from '@chainvue/sdk';

const config = new Configuration({
  basePath: 'https://api.chainvue.io'
});
const identityApi = new IdentitiesApi(config);

// Get identity by name
const identity = await identityApi.getIdentity('Mike@');
console.log(identity.data);

// Search identities
const results = await identityApi.searchIdentities('Mike');
console.log(results.data);
```

### Universal Search

```typescript
import { Configuration, SearchApi } from '@chainvue/sdk';

const config = new Configuration({
  basePath: 'https://api.chainvue.io'
});
const searchApi = new SearchApi(config);

// Search across blocks, transactions, addresses, identities, and currencies
const results = await searchApi.universalSearch('Mike');
console.log(results.data);
```

### Chains

```typescript
import { Configuration, ChainsApi } from '@chainvue/sdk';

const config = new Configuration({
  basePath: 'https://api.chainvue.io'
});
const chainsApi = new ChainsApi(config);

// List all supported chains
const chains = await chainsApi.listChains();
console.log(chains.data);
```

### Health Check

```typescript
import { Configuration, HealthApi } from '@chainvue/sdk';

const config = new Configuration({
  basePath: 'https://api.chainvue.io'
});
const healthApi = new HealthApi(config);

// Check API health
const health = await healthApi.healthCheck();
console.log(health.data);

// Get API status
const status = await healthApi.apiStatus();
console.log(status.data);
```

## Configuration

### Basic Configuration

```typescript
import { Configuration } from '@chainvue/sdk';

const config = new Configuration({
  basePath: 'https://api.chainvue.io'
});
```

### Custom Timeout

```typescript
import { Configuration } from '@chainvue/sdk';
import axios from 'axios';

const axiosInstance = axios.create({
  timeout: 30000 // 30 seconds
});

const config = new Configuration({
  basePath: 'https://api.chainvue.io',
  baseOptions: {
    timeout: 30000
  }
});
```

### Custom Headers

```typescript
import { Configuration } from '@chainvue/sdk';

const config = new Configuration({
  basePath: 'https://api.chainvue.io',
  baseOptions: {
    headers: {
      'X-Custom-Header': 'value'
    }
  }
});
```

## Error Handling

```typescript
import { Configuration, BlocksApi } from '@chainvue/sdk';

const config = new Configuration({
  basePath: 'https://api.chainvue.io'
});
const blocksApi = new BlocksApi(config);

try {
  const block = await blocksApi.getBlock('invalid');
} catch (error) {
  if (error.response) {
    // The request was made and the server responded with a status code
    console.error(`Error ${error.response.status}: ${error.response.data.error}`);
  } else if (error.request) {
    // The request was made but no response was received
    console.error('No response received:', error.request);
  } else {
    // Something happened in setting up the request
    console.error('Error:', error.message);
  }
}
```

## Real-World Examples

### Monitor Address for Incoming Payments

```typescript
import { Configuration, AddressesApi } from '@chainvue/sdk';

async function monitorPayment(
  address: string,
  expectedAmount: number
): Promise<boolean> {
  const config = new Configuration({
    basePath: 'https://api.chainvue.io'
  });
  const addressApi = new AddressesApi(config);

  while (true) {
    const balance = await addressApi.getAddressBalance(address);
    const currentBalance = parseFloat(balance.data.data?.balance || '0');

    if (currentBalance >= expectedAmount) {
      console.log(`Payment received! Balance: ${currentBalance} VRSC`);
      return true;
    }

    console.log(`Waiting... Current balance: ${currentBalance} VRSC`);
    await new Promise(resolve => setTimeout(resolve, 10000)); // Check every 10s
  }
}

// Usage
await monitorPayment('RCG8KwJNDVwpUBcdoa6AoHqHVJsA1uMYMR', 100);
```

### Get Transaction Confirmations

```typescript
import { Configuration, TransactionsApi, BlocksApi } from '@chainvue/sdk';

async function getConfirmations(txid: string): Promise<number> {
  const config = new Configuration({
    basePath: 'https://api.chainvue.io'
  });
  const txApi = new TransactionsApi(config);
  const blocksApi = new BlocksApi(config);

  const tx = await txApi.getTransaction(txid);
  const latestBlock = await blocksApi.getLatestBlock();

  const txHeight = tx.data.data?.block_height || 0;
  const currentHeight = latestBlock.data.data?.height || 0;

  return currentHeight - txHeight;
}

// Usage
const confirmations = await getConfirmations('abc123...');
console.log(`Transaction has ${confirmations} confirmations`);
```

### Fetch Recent Blocks

```typescript
import { Configuration, BlocksApi } from '@chainvue/sdk';

async function getRecentBlocks(count: number = 10) {
  const config = new Configuration({
    basePath: 'https://api.chainvue.io'
  });
  const blocksApi = new BlocksApi(config);

  const latest = await blocksApi.getLatestBlock();
  const latestHeight = latest.data.data?.height || 0;

  const blocks = [];
  for (let i = 0; i < count; i++) {
    const block = await blocksApi.getBlock(`${latestHeight - i}`);
    blocks.push(block.data);
  }

  return blocks;
}

// Usage
const recentBlocks = await getRecentBlocks(5);
console.log('Recent blocks:', recentBlocks);
```

### Multi-Chain Query

```typescript
import { Configuration, AddressesApi } from '@chainvue/sdk';

async function getMultiChainBalance(address: string) {
  const config = new Configuration({
    basePath: 'https://api.chainvue.io'
  });
  const addressApi = new AddressesApi(config);

  // Query testnet
  const testnetBalance = await addressApi.getAddressBalance(
    address,
    'iJhCezBExJHvtyH3fGhNnt2NhU4Ztkf2yq' // VRSCTEST chain_id
  );

  console.log('Testnet balance:', testnetBalance.data.data?.balance);

  // You can query other chains by passing their chain_id
  return testnetBalance.data;
}

// Usage
await getMultiChainBalance('RCG8KwJNDVwpUBcdoa6AoHqHVJsA1uMYMR');
```

## Available API Classes

| Class | Description | Endpoints |
|-------|-------------|-----------|
| **BlocksApi** | Block data queries | `getLatestBlock`, `getBlock` |
| **TransactionsApi** | Transaction queries | `getTransaction`, `getMempool` |
| **AddressesApi** | Address information | `getAddress`, `getAddressBalance`, `getAddressTransactions` |
| **IdentitiesApi** | VerusID queries | `getIdentity`, `searchIdentities` |
| **ChainsApi** | Chain information | `listChains` |
| **SearchApi** | Universal search | `universalSearch` |
| **HealthApi** | API health checks | `healthCheck`, `apiStatus` |

## TypeScript Types

All data models are fully typed:

```typescript
import { Block, Transaction, Address, Identity, Chain } from '@chainvue/sdk';

// Full IntelliSense support
const block: Block = {
  chain_id: 'iJhCezBExJHvtyH3fGhNnt2NhU4Ztkf2yq',
  hash: '0x...',
  height: 4500000,
  // ... TypeScript will autocomplete all fields
};
```

## Response Format

All API responses follow this structure:

```typescript
{
  success: boolean;
  data?: T;  // Your requested data
  error?: string;  // Error message if success is false
  meta: {
    request_id: string;
    timestamp: string;
  };
}
```

## Development

This SDK is **auto-generated** from the ChainVue OpenAPI specification.

**Important:** Do not manually edit generated files (api/, models/, etc.). All changes will be overwritten when the SDK is regenerated.

## Links

- **Live API:** [https://api.chainvue.io](https://api.chainvue.io)
- **npm Package:** [@chainvue/sdk](https://www.npmjs.com/package/@chainvue/sdk)
- **SDK Repository:** [chainvue/chainvue-sdk-typescript](https://github.com/chainvue/chainvue-sdk-typescript)
- **OpenAPI Spec:** [openapi.json](https://api.chainvue.io/api-docs/openapi.json)

## Supported Environments

- Node.js 12+
- Modern browsers (with bundler)
- Webpack
- Vite
- Rollup
- ES5+ with Promises/A+ library

## License

MIT License - see [LICENSE](LICENSE) file for details.

## Support

- **Issues:** [GitHub Issues](https://github.com/chainvue/chainvue-sdk-typescript/issues)
- **Discussions:** [GitHub Discussions](https://github.com/chainvue/chainvue-sdk-typescript/discussions)
