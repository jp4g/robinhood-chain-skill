# Robinhood Chain Resource Map

Last reviewed: 2026-07-09. Use this as a seed map, not a complete catalog. Provider availability changes quickly; verify against live vendor docs before making a claim.

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
- Report an issue: https://docs.robinhood.com/chain/report-issue/
- Terms: https://docs.robinhood.com/chain/terms-of-service/
- Status: https://status.robinhoodchain.offchain.io/
- Status API summary: https://status.robinhoodchain.offchain.io/v3/summary.json
- Status API components: https://status.robinhoodchain.offchain.io/v3/components.json
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
- Mainnet sequencer: `https://sequencer.mainnet.chain.robinhood.com`
- Testnet sequencer: `https://sequencer.testnet.chain.robinhood.com`

Sequencer endpoints are not general JSON-RPC endpoints. Use RPC URLs for normal JSON-RPC calls.

Alchemy endpoint templates from Robinhood docs:

- Mainnet RPC: `https://robinhood-mainnet.g.alchemy.com/v2/{API_KEY}`
- Testnet RPC: `https://robinhood-testnet.g.alchemy.com/v2/{API_KEY}`
- Mainnet WebSocket: `wss://robinhood-mainnet.g.alchemy.com/v2/{API_KEY}`
- Testnet WebSocket: `wss://robinhood-testnet.g.alchemy.com/v2/{API_KEY}`

Minimal viem/wagmi-style testnet config seed:

```ts
import { defineChain } from "viem";

export const robinhoodTestnet = defineChain({
  id: 46630,
  name: "Robinhood Chain Testnet",
  nativeCurrency: { name: "Ether", symbol: "ETH", decimals: 18 },
  rpcUrls: {
    default: { http: ["https://rpc.testnet.chain.robinhood.com"] },
  },
  blockExplorers: {
    default: {
      name: "Robinhood Chain Testnet Explorer",
      url: "https://explorer.testnet.chain.robinhood.com",
    },
  },
  testnet: true,
});
```

Before production, re-check Robinhood docs, ChainList, provider status, rate limits, and archive support. Confirm any endpoint with `eth_chainId`.

## Provider and Connected-Service Seeds

This list is intentionally broad and non-exhaustive. Use it to start current research, not as proof of support.

### RPC and Node Providers

- Alchemy RPC, WebSocket, AA, Data API, gas sponsorship: https://www.alchemy.com/rpc/robinhood
- Alchemy quickstart: https://www.alchemy.com/docs/reference/robinhood-chain-api-quickstart
- QuickNode RPC: https://www.quicknode.com/chains/robinhood
- Blockdaemon connection docs: https://docs.blockdaemon.com/docs/how-to-connect-to-robinhood
- dRPC chainlist/provider discovery: https://drpc.org/chainlist
- Validation Cloud: https://www.validationcloud.io/robinhood

### Indexing, Subgraphs, Data APIs, and Warehouses

- Goldsky indexing, subgraphs, Mirror, Turbo, Edge RPC: https://goldsky.com/chains/robinhood
- Allium launch support and data APIs: https://www.allium.so/blog/supporting-robinhood-chain-at-launch/
- Allium Robinhood testnet docs: https://docs.allium.so/historical-data/supported-blockchains/evm/robinhood_testnet
- SQD data/indexing: https://sqd.dev/chains/robinhood/
- GoldRush Robinhood Chain API: https://goldrush.dev/chains/robinhood-chain/
- The Graph supported networks negative-check: https://thegraph.com/docs/en/supported-networks/

### Oracles and Cross-Chain Messaging

- Chainlink Robinhood tokenized equity feeds: https://docs.chain.link/data-feeds/tokenized-equity-feeds/robinhood
- Chainlink CCIP Robinhood mainnet: https://docs.chain.link/ccip/directory/mainnet/chain/robinhood-mainnet
- LayerZero Robinhood deployment: https://docs.layerzero.network/v2/deployments/chains/robinhood

### Bridges and Aggregators

- Arbitrum canonical bridge: https://portal.arbitrum.io/bridge
- Stargate generic research seed, not proof of Robinhood support: https://stargate.finance/
- Relay generic research seed, not proof of Robinhood support: https://relay.link/
- Across Robinhood Chain: https://across.to/blog/bridge-to-robinhood-chain-with-across
- LI.FI generic research seed, not proof of Robinhood support: https://li.fi/
- 0x Robinhood Chain: https://0x.org/post/robinhood-chain

### Wallets, Account Abstraction, and App Infrastructure

- Robinhood Wallet setup docs: https://docs.robinhood.com/chain/add-network-to-wallet/
- Alchemy account abstraction: https://docs.robinhood.com/chain/account-abstraction/
- ZeroDev generic research seed, not proof of Robinhood support: https://zerodev.app/
- Privy generic research seed, not proof of Robinhood support: https://www.privy.io/
- Turnkey Robinhood support: https://www.turnkey.com/blog/robinhood-chain-support
- Openfort Robinhood support: https://www.openfort.io/blog/robinhood-chain-support

### DEX, Liquidity, Token Tracking, and Wallet Data

- Uniswap supported chains: https://developers.uniswap.org/docs/trading/swapping-api/supported-chains
- Uniswap v4 deployments: https://developers.uniswap.org/docs/protocols/v4/deployments
- Robinhood mainnet announcement naming ecosystem partners: https://robinhood.com/us/en/newsroom/robinhood-accelerates-global-expansion-robinhood-chain-mainnet-stock-tokens-agentic-trading/
- BitGo Robinhood support: https://www.bitgo.com/resources/blog/bitgo-adds-day-one-support-for-robinhood-chain-mainnet/
- Zerion API Robinhood support: https://zerion.io/blog/zerion-api-supports-robinhood-chain-from-day-one/
- CoinGecko Robinhood Chain Stocks category: https://www.coingecko.com/en/categories/robinhood-chain-stocks-ecosystem

### Compliance, Chain Intelligence, Analytics, and Catalogs

- Chainalysis Robinhood support: https://www.chainalysis.com/blog/robinhood-chain-automatic-token-support/
- Elliptic Robinhood coverage: https://www.elliptic.co/media-center/elliptic-supports-robinhood-chain
- Robinhood public testnet announcement naming TRM: https://robinhood.com/us/en/newsroom/robinhood-chain-launches-public-testnet/
- DefiLlama Robinhood Chain catalog: https://defillama.com/chain/robinhood-chain
- Blockscout explorer: https://robinhoodchain.blockscout.com/

Robinhood docs also name ecosystem partners such as LayerZero, Chainlink, Fireblocks, BitGo, Allium, Coingecko, Uniswap, Rialto, Morpho, Lighter, Arcus, Paxos USDG, and Zerion. Check the provider's own docs before relying on availability.

## Common Agent Answers

- "Where do I find RPCs?" Start with Robinhood's connecting page, then ChainList and provider docs. Public RPCs are rate-limited; use provider endpoints for production.
- "Do subgraphs work?" Do not assume The Graph network support. Check Goldsky first for Robinhood subgraphs, then check The Graph supported networks or the requested indexer/vendor directly.
- "Can I deploy normal Solidity contracts?" Yes, but do not stop there. Check Arbitrum Nitro differences, gas/finality, Blockscout verification, and Robinhood-specific compliance/order behavior.
- "Where are token addresses?" Link the official Token Contracts page. Do not paste a stale token list unless the user specifically asks for a point-in-time snapshot.
- "Where are oracle feed addresses?" Link Robinhood Oracles & Price Feeds and Chainlink's current Robinhood feed pages. Do not hardcode stale feed addresses.
- "How do I build a Stock Token price card?" Resolve the token from official Token Contracts and the feed from Chainlink. Investigate `latestRoundData()`, `decimals()`, `uiMultiplier()`, pending multiplier fields, sequencer uptime, staleness, and `oraclePaused()`. The feed already returns multiplier-adjusted per-token price; do not multiply by `uiMultiplier()` again unless converting to share-equivalent display terms.
- "How do I bridge?" Link Robinhood Bridging first. For programmatic bridge or messaging work, also use Protocol Contracts and Cross-Chain Messaging.
- "Does a named service support Robinhood Chain?" Answer with a verdict: `Supported`, `Testnet-only`, `Partial`, `No published support found`, or `Unknown`. Include product surface, mainnet/testnet, vendor URL, and access date. `Partial` means only some surfaces, networks, APIs, or access tiers are supported. `No published support found` means you checked the vendor's published docs/support pages and found no support claim. `Unknown` means evidence is insufficient, inaccessible, or conflicting.
