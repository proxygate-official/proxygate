```
██████╗ ██████╗  ██████╗ ██╗  ██╗██╗   ██╗ ██████╗  █████╗ ████████╗███████╗
██╔══██╗██╔══██╗██╔═══██╗╚██╗██╔╝╚██╗ ██╔╝██╔════╝ ██╔══██╗╚══██╔══╝██╔════╝
██████╔╝██████╔╝██║   ██║ ╚███╔╝  ╚████╔╝ ██║  ███╗███████║   ██║   █████╗
██╔═══╝ ██╔══██╗██║   ██║ ██╔██╗   ╚██╔╝  ██║   ██║██╔══██║   ██║   ██╔══╝
██║     ██║  ██║╚██████╔╝██╔╝ ██╗   ██║   ╚██████╔╝██║  ██║   ██║   ███████╗
╚═╝     ╚═╝  ╚═╝ ╚═════╝ ╚═╝  ╚═╝   ╚═╝    ╚═════╝ ╚═╝  ╚═╝   ╚═╝   ╚══════╝
```

# ProxyGate Agent Skills

[![npm](https://img.shields.io/npm/v/@proxygate/cli?label=CLI&color=00D4FF)](https://www.npmjs.com/package/@proxygate/cli)
[![npm](https://img.shields.io/npm/v/@proxygate/sdk?label=SDK&color=00D4FF)](https://www.npmjs.com/package/@proxygate/sdk)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Twitter Follow](https://img.shields.io/twitter/follow/proxygateai?style=social)](https://twitter.com/proxygateai)

[![Tweet](https://img.shields.io/twitter/url/http/shields.io.svg?style=social)](https://twitter.com/intent/tweet?text=AI%20agents%20can%20now%20buy%20and%20sell%20API%20capacity%20autonomously%20with%20USDC%20on%20Solana%20%E2%9A%A1&url=https://github.com/proxygate-official/proxygate&via=proxygateai&hashtags=AI,Solana,USDC,APIs)

**The Stripe for AI Agents.** Sellers list unused API capacity. AI agents buy access through a transparent proxy. Keys never leave the server. Payments in USDC on Solana.

---

Skills for [Claude Code](https://docs.anthropic.com/en/docs/claude-code), [Codex CLI](https://openai.com/index/codex/), and other AI coding assistants.

## How it works

```
  Seller                    ProxyGate                    Agent
  ┌──────┐                 ┌──────────┐                 ┌──────┐
  │ API  │◄── key stays ──►│ Gateway  │◄── USDC pay ──►│ Bot  │
  │ Key  │    on server     │          │    per call     │      │
  └──────┘                 └──────────┘                 └──────┘
     │                          │                          │
     │  1. List capacity        │  3. Proxy request        │
     │  2. Set price            │  4. Inject key           │
     │                          │  5. Deduct credits       │
     │                          │  6. Settle USDC          │
```

**Sellers** list APIs they have access to. **Agents** pay per call with USDC. The gateway injects the seller's key server-side — the agent never sees it. Settlement happens on Solana.

## Skills

| Skill | What it does |
|-------|-------------|
| [`proxygate`](./proxygate/) | Router — automatically picks the right sub-skill |
| [`pg-setup`](./pg-setup/) | Install CLI, authenticate (API key, WalletConnect, or keypair) |
| [`pg-buy`](./pg-buy/) | Browse APIs, deposit USDC, proxy requests, stream responses |
| [`pg-sell`](./pg-sell/) | Create listings, manage keys, expose services via tunnel |
| [`pg-status`](./pg-status/) | Check balance, usage, listings, earnings |
| [`pg-update`](./pg-update/) | Update CLI and SDK to latest version |

## Install

### Via CLI (recommended)

```bash
npm install -g @proxygate/cli
proxygate skills install
```

### Via Skills CLI

```bash
npx skills add proxygate-official/proxygate
```

### Manual

```bash
git clone https://github.com/proxygate-official/proxygate.git /tmp/pg-skills
cp -r /tmp/pg-skills/proxygate /tmp/pg-skills/pg-* ~/.claude/skills/
```

## Quick start

```bash
# 1. Authenticate
proxygate login                              # interactive — API key or wallet

# 2. Find an API
proxygate search weather

# 3. Call it
proxygate proxy weather-api /v1/forecast \
  -d '{"latitude":52.37,"longitude":4.90}'

# cost: $0.0012 | request: 905b1a53
```

Or just tell your AI assistant:

> "Search for a weather API on ProxyGate and get the forecast for Amsterdam"

The skills handle the rest.

## Auth modes

| Mode | Best for | On-chain? |
|------|----------|-----------|
| **API key** | Agents, scripts, quick start | No |
| **WalletConnect** | Mobile wallet users (Phantom, Solflare) | No |
| **Keypair** | Full access — deposit, withdraw, settle | Yes |

Start with an **API key** — no wallet needed. Get one at [app.proxygate.ai/wallets](https://app.proxygate.ai/wallets).

## Links

| | |
|---|---|
| Website | [proxygate.ai](https://proxygate.ai) |
| Dashboard | [app.proxygate.ai](https://app.proxygate.ai) |
| API docs | [gateway.proxygate.ai/docs](https://gateway.proxygate.ai/docs) |
| CLI | [`@proxygate/cli`](https://www.npmjs.com/package/@proxygate/cli) |
| SDK | [`@proxygate/sdk`](https://www.npmjs.com/package/@proxygate/sdk) |
| Twitter | [@proxygateai](https://twitter.com/proxygateai) |

## License

MIT
