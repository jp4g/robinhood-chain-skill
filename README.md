# Robinhood Chain Skill

Agent Skill for building on Robinhood Chain with Claude, Codex, and other skills-compatible agents.

This skill is intentionally small. It gives agents Robinhood-specific routing context and links to live docs for network config, ChainList RPC lookup, Stock Tokens, bridges, account abstraction, oracles, nodes, explorers, and connected services. It avoids copying generic EVM material.

## Install With Agent Skills CLI

```bash
npx skills add jp4g/robinhood-chain-skill --skill robinhood-chain
```

For Codex project installs, the `skills` CLI targets `.agents/skills/`. For Claude Code installs, use:

```bash
npx skills add jp4g/robinhood-chain-skill --skill robinhood-chain --agent claude-code
```

## Upload To Claude.ai Or Claude API

Do not upload the GitHub repository ZIP directly. Claude custom Skills expect a ZIP whose single top-level entry is the skill folder containing `SKILL.md`.

From a clone of this repo:

```bash
cd skills
zip -r ../robinhood-chain.zip robinhood-chain
```

Upload `robinhood-chain.zip`. Its structure should be:

```text
robinhood-chain.zip
└── robinhood-chain/
    ├── SKILL.md
    ├── agents/openai.yaml
    └── references/chain-resources.md
```

## Skill

- `skills/robinhood-chain/`

## Notes

- Robinhood docs are the source of truth for chain identity and Robinhood-operated endpoints.
- ChainList is included for wallet/RPC discovery.
- Connected-service links are a starting point, not a comprehensive catalog; agents should verify provider support live.
