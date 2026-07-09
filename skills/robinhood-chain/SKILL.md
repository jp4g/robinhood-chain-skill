---
name: robinhood-chain
description: Build, deploy, connect, or research Robinhood Chain, Robinhood Chain Testnet, Stock Tokens, RPCs, ChainList, bridges, explorers, account abstraction, oracles, indexing, data providers, wallets, and connected service support. Use when the user asks about Robinhood's EVM chain or integrating an app, contract, wallet, indexer, provider, or agent with Robinhood Chain.
---

# Robinhood Chain

Use this skill as a routing guide for Robinhood Chain work. Do not teach generic Solidity, EVM, ERC-20, Hardhat, Foundry, viem, ethers, or wallet basics unless the user asks for them; Robinhood Chain is EVM-compatible, so standard EVM knowledge applies.

## Source Order

Prefer live, source-linked data over memory. Robinhood Chain is new enough that provider support and token lists can change quickly.

1. Treat [Robinhood Chain docs](https://docs.robinhood.com/chain/) as canonical for chain IDs, public endpoints, bridges, contracts, Stock Tokens, oracles, account abstraction, node operation, notices, and terms.
2. Use [ChainList mainnet](https://chainlist.org/chain/4663), [ChainList testnet](https://chainlist.org/chain/46630), and the [ChainList API](https://chainlist.org/rpcs.json) to discover current wallet/RPC metadata.
3. Use provider/vendor docs to confirm connected-service support such as RPCs, subgraphs, indexing, data APIs, bridges, AA, wallet infra, analytics, compliance, DEX/liquidity, and oracles. Do not treat the seed list in [chain-resources.md](references/chain-resources.md) as exhaustive.
4. If data conflicts, prefer Robinhood docs for Robinhood-operated endpoints and chain identity, then the vendor's own docs for that vendor's support.

## Stable Network Facts

Verify before production use, but these are the current official basics:

| Network | Chain ID | Hex | Gas | Public RPC | Explorer |
| --- | ---: | --- | --- | --- | --- |
| Robinhood Chain | `4663` | `0x1237` | ETH | `https://rpc.mainnet.chain.robinhood.com` | `https://robinhoodchain.blockscout.com` |
| Robinhood Chain Testnet | `46630` | `0xb626` | ETH | `https://rpc.testnet.chain.robinhood.com` | `https://explorer.testnet.chain.robinhood.com` |

Do not use third-party references that claim testnet chain ID `46646`; the official testnet chain ID is `46630`.

Robinhood public RPCs are rate-limited and not recommended for production. For production traffic, point users to provider endpoints, especially Alchemy, then verify any other provider directly with that provider.

## Robinhood-Specific Checks

When helping with contracts or apps, check Robinhood-specific behavior before writing code:

- Arbitrum Nitro L2 differences: `block.number`, randomness, gas accounting, address aliasing, precompiles, transaction screening, and first-come first-served ordering differ from Ethereum mainnet. Read [Differences from Ethereum](https://docs.robinhood.com/chain/differences-from-ethereum/), [Gas & Fees](https://docs.robinhood.com/chain/gas-and-fees/), and [Transaction Finality](https://docs.robinhood.com/chain/transaction-finality/).
- Stock Tokens: use [Stock Tokens](https://docs.robinhood.com/chain/stock-tokens/), [Building with Stock Tokens](https://docs.robinhood.com/chain/building-with-stock-tokens/), and [Token Contracts](https://docs.robinhood.com/chain/contracts/). Do not copy token address tables into generated docs; link to the current official page.
- Price feeds: use [Oracles & Price Feeds](https://docs.robinhood.com/chain/oracles-and-price-feeds/) and Chainlink's current Robinhood feed pages. Account for sequencer uptime, feed staleness, `uiMultiplier()`, and oracle pause behavior.
- Cross-chain work: use [Bridging](https://docs.robinhood.com/chain/bridging/), [Cross-Chain Messaging](https://docs.robinhood.com/chain/cross-chain-messaging/), and [Protocol Contracts](https://docs.robinhood.com/chain/protocol-contracts/). Remember canonical withdrawals to Ethereum have the Arbitrum challenge period.
- Account abstraction: use [Account Abstraction](https://docs.robinhood.com/chain/account-abstraction/) for ERC-4337, EIP-7702, Alchemy, ZeroDev, Privy, bundler URL, and entry point addresses.
- Nodes and upgrades: use [Run a full node](https://docs.robinhood.com/chain/run-a-full-node/), [Notices & Upgrades](https://docs.robinhood.com/chain/notices-and-upgrades/), and the [status page](https://status.robinhoodchain.offchain.io/).

## Connected Services

When the user asks whether a service works on Robinhood Chain, do current research. Examples include subgraphs, but also RPC providers, archive nodes, token APIs, data warehouses, bridges, oracles, wallets, AA/bundlers/paymasters, compliance tools, explorers, DEXs, and analytics.

Load [chain-resources.md](references/chain-resources.md) when you need a seed map of known sources and provider pages. Then verify current support with the service's own docs or support page before giving a definitive answer.

## Practical Workflow

For any Robinhood Chain task:

1. Identify whether the user targets mainnet or testnet.
2. Pull current network/provider facts from Robinhood docs and ChainList if the answer depends on live endpoints.
3. Route Robinhood-specific logic to the docs linked above.
4. Use normal EVM tooling for the actual implementation once the Robinhood-specific config is known.
5. Cite sources and avoid pasting large copied tables from docs.
