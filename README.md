# Robinhood Chain Skill

Agent Skill for building on Robinhood Chain with Claude, Codex, and other skills-compatible agents.

This skill is intentionally small. It gives agents Robinhood-specific routing context and links to live docs for network config, ChainList RPC lookup, Stock Tokens, bridges, account abstraction, oracles, nodes, explorers, and connected services. It avoids copying generic EVM material.

## Install

```bash
npx skills add jp4g/robinhood-chain-skill --skill robinhood-chain
```

For Codex project installs, the `skills` CLI targets `.agents/skills/`. For Claude Code project installs, use:

```bash
npx skills add jp4g/robinhood-chain-skill --skill robinhood-chain --agent claude-code
```

## Skill

- `skills/robinhood-chain/`

## Notes

- Robinhood docs are the source of truth for chain identity and Robinhood-operated endpoints.
- ChainList is included for wallet/RPC discovery.
- Connected-service links are a starting point, not a comprehensive catalog; agents should verify provider support live.
