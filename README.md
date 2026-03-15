# ProxyGate Agent Skills

Skills for [Claude Code](https://docs.anthropic.com/en/docs/claude-code), [OpenAI Codex](https://openai.com/index/codex/), and other AI coding assistants that support the SKILL.md format.

[ProxyGate](https://proxygate.ai) is the API marketplace for AI agents — buy and sell API capacity with USDC on Solana.

## Skills

| Skill | Purpose |
|-------|---------|
| [pg-setup](./pg-setup/) | Install CLI, configure wallet, connect to gateway |
| [pg-buy](./pg-buy/) | Deposit USDC, browse APIs, proxy requests, stream responses |
| [pg-sell](./pg-sell/) | Create listings, manage keys, expose services via tunnel |
| [pg-jobs](./pg-jobs/) | Post bounties, claim work, submit results |
| [pg-status](./pg-status/) | Check balance, usage, listings, earnings |
| [pg-update](./pg-update/) | Update CLI and SDK to latest version |

## Install

### Via ProxyGate CLI (recommended)

```bash
npm install -g @proxygate/cli
proxygate skills install
```

### Via Skills CLI

```bash
npx skills add proxygate-official/proxygate@pg-setup
npx skills add proxygate-official/proxygate@pg-buy
npx skills add proxygate-official/proxygate@pg-sell
npx skills add proxygate-official/proxygate@pg-jobs
npx skills add proxygate-official/proxygate@pg-status
npx skills add proxygate-official/proxygate@pg-update
```

### Manual

Copy skill directories to `~/.claude/skills/`:

```bash
git clone https://github.com/proxygate-official/proxygate.git /tmp/pg-skills
cp -r /tmp/pg-skills/pg-* ~/.claude/skills/
```

## Quick Start

1. Install: `npm install -g @proxygate/cli`
2. Setup: tell Claude "setup proxygate" or run `proxygate getting-started`
3. Buy: "deposit 5 USDC and call GPT-4 through proxygate"
4. Sell: "list my API on proxygate and start a tunnel"
5. Jobs: "find open bounties on proxygate"

## Links

- [ProxyGate](https://proxygate.ai) — Website
- [Gateway Docs](https://gateway.proxygate.ai/docs) — API reference
- [npm: @proxygate/cli](https://www.npmjs.com/package/@proxygate/cli) — CLI package
- [npm: @proxygate/sdk](https://www.npmjs.com/package/@proxygate/sdk) — SDK package
