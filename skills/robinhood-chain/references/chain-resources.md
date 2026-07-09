# Robinhood Chain Resource Map

Last reviewed: 2026-07-08. Use this as a seed map, not a complete catalog. Provider availability changes quickly; verify against live vendor docs before making a claim.

## Official Robinhood Sources

- Docs home: https://docs.robinhood.com/chain/
- Product page: https://robinhood.com/us/en/chain/
- Network config and endpoints: https://docs.robinhood.com/chain/connecting/
- Wallet setup: https://docs.robinhood.com/chain/add-network-to-wallet/
- Bridging: https://docs.robinhood.com/chain/bridging/
- Stock Tokens: https://docs.robinhood.com/chain/stock-tokens/
- Building with Stock Tokens: https://docs.robinhood.com/chain/building-with-stock-tokens/
- Token contracts: https://docs.robinhood.com/chain/contracts/
- Protocol contracts: https://docs.robinhood.com/chain/protocol-contracts/
- Differences from Ethereum: https://docs.robinhood.com/chain/differences-from-ethereum/
- Gas and fees: https://docs.robinhood.com/chain/gas-and-fees/
- Transaction finality: https://docs.robinhood.com/chain/transaction-finality/
- Deploy contracts: https://docs.robinhood.com/chain/deploy-smart-contracts/
- Account abstraction: https://docs.robinhood.com/chain/account-abstraction/
- Cross-chain messaging: https://docs.robinhood.com/chain/cross-chain-messaging/
- Oracles and price feeds: https://docs.robinhood.com/chain/oracles-and-price-feeds/
- Full node: https://docs.robinhood.com/chain/run-a-full-node/
- Notices and upgrades: https://docs.robinhood.com/chain/notices-and-upgrades/
- Terms: https://docs.robinhood.com/chain/terms-of-service/
- Status: https://status.robinhoodchain.offchain.io/
- Testnet faucet: https://faucet.testnet.chain.robinhood.com/

## Chain Identity and RPC Discovery

- ChainList mainnet: https://chainlist.org/chain/4663
- ChainList testnet: https://chainlist.org/chain/46630
- ChainList API: https://chainlist.org/rpcs.json
- DefiLlama ChainList repo: https://github.com/DefiLlama/chainlist

Useful live check:

```bash
curl -s https://chainlist.org/rpcs.json | jq '.[] | select(.chainId == 4663 or .chainId == 46630)'
```

Official public endpoints:

- Mainnet RPC: `https://rpc.mainnet.chain.robinhood.com`
- Testnet RPC: `https://rpc.testnet.chain.robinhood.com`
- Mainnet sequencer feed: `wss://feed.mainnet.chain.robinhood.com`
- Testnet sequencer feed: `wss://feed.testnet.chain.robinhood.com`

## Provider and Connected-Service Seeds

This list is intentionally broad and non-exhaustive. Use it to start current research.

- Alchemy RPC, WebSocket, AA, Data API, gas sponsorship: https://www.alchemy.com/rpc/robinhood
- Alchemy quickstart: https://www.alchemy.com/docs/reference/robinhood-chain-api-quickstart
- QuickNode RPC: https://www.quicknode.com/chains/robinhood
- Blockdaemon connection docs: https://docs.blockdaemon.com/docs/how-to-connect-to-robinhood
- Validation Cloud: https://www.validationcloud.io/robinhood
- Goldsky indexing, subgraphs, Mirror, Turbo, Edge RPC: https://goldsky.com/chains/robinhood
- Allium launch support and data APIs: https://www.allium.so/blog/supporting-robinhood-chain-at-launch/
- Allium supported blockchain docs: https://docs.allium.so/historical-data/supported-blockchains/evm/robinhood_testnet
- SQD data/indexing: https://sqd.dev/chains/robinhood/
- Chainlink Robinhood tokenized equity feeds: https://docs.chain.link/data-feeds/tokenized-equity-feeds/robinhood
- LayerZero Robinhood deployment: https://docs.layerzero.network/v2/deployments/chains/robinhood
- Uniswap supported chains: https://developers.uniswap.org/docs/trading/swapping-api/supported-chains
- Uniswap v4 deployments: https://developers.uniswap.org/docs/protocols/v4/deployments

Robinhood docs also name ecosystem partners such as LayerZero, Chainlink, Fireblocks, BitGo, Allium, Coingecko, Uniswap, Rialto, Morpho, Lighter, Arcus, Paxos USDG, and Zerion. Check the provider's own docs before relying on availability.

## Common Agent Answers

- "Where do I find RPCs?" Start with Robinhood's connecting page, then ChainList and provider docs. Public RPCs are rate-limited; use provider endpoints for production.
- "Do subgraphs work?" Do not assume The Graph network support. Check Goldsky first for Robinhood subgraphs, then check The Graph supported networks or the requested indexer/vendor directly.
- "Can I deploy normal Solidity contracts?" Yes, but do not stop there. Check Arbitrum Nitro differences, gas/finality, Blockscout verification, and Robinhood-specific compliance/order behavior.
- "Where are token addresses?" Link the official Token Contracts page. Do not paste a stale token list unless the user specifically asks for a point-in-time snapshot.
- "Where are oracle feed addresses?" Link Robinhood Oracles & Price Feeds and Chainlink's current Robinhood feed pages. Do not hardcode stale feed addresses.
- "How do I bridge?" Link Robinhood Bridging first. For programmatic bridge or messaging work, also use Protocol Contracts and Cross-Chain Messaging.
