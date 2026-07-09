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

## Skills.sh Discoverability

There is no separate skills.sh publish command. Public GitHub repositories are installable through the `skills` CLI, and skills.sh can discover them from CLI usage. The canonical install target is:

```bash
npx skills add jp4g/robinhood-chain-skill --skill robinhood-chain
```

Manual install locations:

- Claude Code personal: `~/.claude/skills/robinhood-chain/`
- Claude Code project: `.claude/skills/robinhood-chain/`
- Codex personal: `~/.codex/skills/robinhood-chain/`
- Codex/project-compatible: `.agents/skills/robinhood-chain/`

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

## Smoke Prompts

Try these in a fresh agent session after installing:

- "Use the Robinhood Chain skill to configure wagmi/viem for Robinhood Chain Testnet."
- "Use the Robinhood Chain skill to plan a Stock Token price card for AAPL."
- "Use the Robinhood Chain skill to check whether Goldsky, Allium, or another named service supports Robinhood Chain."

## Notes

- Robinhood docs are the source of truth for chain identity and Robinhood-operated endpoints.
- ChainList is included for wallet/RPC discovery.
- Connected-service links are a starting point, not a comprehensive catalog; agents should verify provider support live.
