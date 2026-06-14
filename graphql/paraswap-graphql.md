# ParaSwap GraphQL API

ParaSwap (now Velora) exposes historical on-chain data through The Graph protocol subgraphs. The Augustus v5 subgraph tracks all token swaps executed through the ParaSwap Augustus smart contract across its supported EVM chains, including Ethereum, Arbitrum, Avalanche, Base, BSC, Optimism, and Polygon. The data covers every swap event from ParaSwap v0.1.0 through the current v5 release, providing full transaction history with routing method, token pairs, amounts, fees, and gas usage.

A separate AugustusRFQ subgraph covers limit order, peer-to-peer, and NFT trade activity through the RFQ system on Ethereum, Arbitrum, Avalanche, BSC, Optimism, and Polygon. Both subgraph families share the same querying interface: standard GraphQL POST requests with no authentication required for read access. Queries support filtering, sorting, and pagination via The Graph's standard query arguments.

The hosted subgraph endpoints follow the pattern `https://api.thegraph.com/subgraphs/name/paraswap/<subgraph-name>`. The Ethereum mainnet Augustus v5 subgraph is the canonical reference deployment. All endpoints accept POST requests with a JSON body containing a `query` field. No API key is required for the hosted service, though The Graph's decentralized network versions may require GRT-based query fees.

**Endpoint:** https://api.thegraph.com/subgraphs/name/paraswap/paraswap-subgraph

**Documentation:** https://developers.velora.xyz/subgraphs

**References:**
- Documentation: https://developers.velora.xyz/subgraphs
- GettingStarted: https://thegraph.com/hosted-service/subgraph/paraswap/paraswap-subgraph
