# ParaSwap

ParaSwap (now operating as Velora) is a DEX aggregator that enables dApps and traders to get the best token swap rates by aggregating liquidity across 170+ decentralized exchanges and liquidity pools on 12 EVM-compatible chains. The platform offers two core trading APIs and a market maker integration API, all accessible via a free public REST API at `https://api.paraswap.io`.

## APIs

### Market API
The core DEX aggregation API. Provides optimal swap routing (GET /prices), transaction call data building (POST /transactions/:network), and a combined endpoint (GET /swap). Supports Augustus smart contract v5 and v6.2. Available on all 12 networks.

### Delta API
An intent-based protocol for gas-less swaps. Users sign an EIP-712 Delta Order; multiple solver agents compete to execute it with MEV protection through the Portikus Intents network. Currently available on Ethereum and Base.

### AugustusRFQ API
Market maker integration API for providing on-chain limit orders, RFQ quotes, and P2P trades for both fungible (ERC-20) and NFT tokens. Implements optional HMAC-SHA256 authentication and optional WebSocket price streaming.

### Tokens API
Returns the curated token list for any supported network (GET /tokens/:network).

### Subgraphs (GraphQL)
TheGraph subgraphs provide historical swap data (Augustus v5) and limit order/RFQ activity (AugustusRFQ) across Ethereum, Arbitrum, Avalanche, Base, BSC, Optimism, and Polygon.

## Supported Networks

| Chain | Chain ID |
|-------|----------|
| Ethereum | 1 |
| Optimism | 10 |
| BSC | 56 |
| Gnosis | 100 |
| Polygon | 137 |
| Sonic | 146 |
| Arbitrum | 42161 |
| Avalanche | 43114 |
| Base | 8453 |
| Unichain | 130 |
| Plasma | 9745 |

## Base URL

```
https://api.paraswap.io
```

## Key Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | /prices | Get optimal swap route and price quote |
| POST | /transactions/:network | Build transaction call data |
| GET | /swap | Combined price + calldata |
| GET | /tokens/:network | Get supported token list |
| GET | /quote | Delta API price quote |
| POST | /delta/orders/build | Build Delta order for signing |
| POST | /orders | Submit signed Delta order |
| GET | /orders/{id} | Track Delta order status |

## Authentication

Public endpoints require no API key. Enterprise dedicated API keys are available for high-throughput production integrations.

## Partner Fee Model

Integrators can register as partners to earn revenue on swaps routed through their integration. Two models are available:
- Surplus model: up to 50% of positive price surplus (capped at 1% in v6.2)
- Flat fee model: up to 2% of swap amount

## SDK

- TypeScript/JavaScript: `@paraswap/sdk` (npm)
- Python: Available via VeloraDEX GitHub
- GitHub: https://github.com/VeloraDEX/sdk

## Resources

- Developer Docs: https://developers.velora.xyz/
- App: https://app.velora.xyz/
- GitHub: https://github.com/VeloraDEX
- Security Audits: https://developers.velora.xyz/security
- Subgraphs: https://developers.velora.xyz/subgraphs
