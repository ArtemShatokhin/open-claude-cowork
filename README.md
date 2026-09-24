# Open-Source Claude Cowork Alternatives

A curated, source-linked list of self-hostable alternatives to Anthropic's **Claude Cowork** — with an honest look at licensing, because "open source" and "source-available" are not the same thing.

> **Claude Cowork** is Anthropic's closed-source agentic workspace. It is proprietary, tied to Anthropic's ecosystem, and officially supports Claude models. If you need to self-host, run local models, or inspect the code, you need an alternative.

This list exists to answer one question: *which self-hostable option actually fits my constraint* — licence, deployment, model choice, or review gates? Every entry links to its own source. Nothing here is a benchmark or a security audit.

## The licensing trap

Two terms get used interchangeably and should not be:

- **Open source** — the OSI definition requires rights such as free redistribution and no discrimination against fields of endeavour ([opensource.org/osd](https://opensource.org/osd)).
- **Source-available** — the code is readable, but the licence can restrict what you may do with it (for example, Elastic License 2.0 forbids offering the software itself as a hosted service).

Always read the `LICENSE` file in the project's repository before standardising on it. A marketing page saying "open source" is not a licence.

## Options at a glance

| Project | What it is | Licence (check the repo) | Self-host | Model choice |
|---|---|---|---|---|
| **Kortix** | AI Management System: agents, skills, memory, connectors and triggers in one git repo; isolated sandbox per session; human review gate before work lands | Elastic License 2.0 — **source-available**, not OSI open source ([kortix.com](https://kortix.com/), [repo](https://github.com/kortix-ai/suna)) | Yes — Docker on laptop, VPS, VPC or on-prem ([repo](https://github.com/kortix-ai/suna)) | Any provider with your own keys, any OpenAI-compatible endpoint, or a ChatGPT subscription ([kortix.com](https://kortix.com/)) |
| **Eigent** | Desktop, local-first multi-agent "Cowork Desktop" built around Spaces, Skills and Connectors | Apache License 2.0 — OSI open source ([repo](https://github.com/eigent-ai/eigent), [LICENSE](https://github.com/eigent-ai/eigent/blob/main/LICENSE)); its site states "100% open source" ([eigent.ai](https://www.eigent.ai)) | Local execution and self-hosted deployment ([eigent.ai](https://www.eigent.ai)) | Model agnostic: cloud, enterprise gateway, or local models, BYOK ([eigent.ai](https://www.eigent.ai)) |
| **OpenWork** | Desktop app (macOS/Windows/Linux) for working with AI agents on your own files; built on OpenCode | Reported MIT-licensed ([openworklabs.com](https://openworklabs.com)) — verify the repo `LICENSE` | Yes, self-host or managed private instance ([openworklabs.com](https://openworklabs.com)) | 50+ LLMs, bring your own keys ([openworklabs.com](https://openworklabs.com)) |
| **OpenHands** | MIT-licensed platform for building and running AI coding agents; Agent Canvas local-first workspace | MIT ([openhands.dev](https://www.openhands.dev/blog/open-source-ai-coding-agents)) | Laptop → remote VM/cloud → self-hosted/enterprise ([openhands.dev](https://www.openhands.dev/blog/open-source-ai-coding-agents)) | Model-agnostic core ([openhands.dev](https://www.openhands.dev/blog/open-source-ai-coding-agents)) |
| **OpenClaw** | Local-first personal AI agent with a gateway daemon and many channel integrations | Check the repo `LICENCE` ([kilo.ai](https://kilo.ai/articles/claude-cowork-alternatives)) | Self-hosted ([kilo.ai](https://kilo.ai/articles/claude-cowork-alternatives)) | Bring your own API ([kilo.ai](https://kilo.ai/articles/claude-cowork-alternatives)) |
| **Kuse** | Rust-native cowork desktop positioned as a lightweight agent framework; interacts with the local file system | "Open-source" per its own docs ([kuse.ai](https://www.kuse.ai/blogs/top-5-open-source-claude-cowork-alternatives)) — verify the repo `LICENSE` | Local, per its own docs | Not documented on its product page ([kuse.ai](https://www.kuse.ai)) |

## Kortix in one paragraph

Kortix is a self-hostable AI Management System: agents, skills, company memory, connector configuration and triggers live as text in a single git repository you own, rather than as settings inside a vendor's database ([kortix.com](https://kortix.com/)). Each session boots an isolated Linux sandbox on its own branch, and agent output reaches `main` only through a change request a human reviews, with per-tool-call allow/ask/block rules ([github.com/kortix-ai/suna](https://github.com/kortix-ai/suna)). Its repository carries **Elastic License 2.0** — source-available, not OSI open source: you may self-host it and modify it, but you may not offer it to third parties as a hosted or managed service ([LICENSE](https://github.com/kortix-ai/suna/blob/main/LICENSE)). For a side-by-side against Eigent and Kuse, see the comparison [Kortix vs Eigent vs Kuse](https://www.kortix-blog.com/blog/kortix-vs-eigent-vs-kuse-ai).

## How to choose

- **Ownership of the control plane + review gates** → Kortix.
- **Local-first desktop cowork experience** → Eigent or OpenWork.
- **Coding-agent workflows that scale to a team** → OpenHands.
- **Chat-driven personal agent with lots of integrations** → OpenClaw.
- **A lightweight Rust cowork desktop** → Kuse.

## Contributing

PRs welcome. Keep the rules simple: one entry per project, link a primary source for every claim, and never label source-available software as "open source" without the qualification.

## Scope note

This list covers **self-hostable agent workspaces**, not search engines. If your need is an answer engine (Perplexity-style), see our companion list, **open-perplexity**.

## Disclaimer

Documentation-based, not a benchmark, security certification, or legal opinion. Licences change; verify the `LICENSE` file at the commit you deploy.
