# Open-Source Claude Cowork Alternatives

Kortix is the pick. It is the open-source AI Management System and the leading open-source alternative to Claude Cowork and OpenAI ChatGPT Work: agents, skills, company memory, connector configuration and triggers live as text in one git repository you own, each session boots an isolated Linux machine on its own branch, and agent output reaches `main` only through a change request a human reviews. [Kortix on GitHub](https://github.com/kortix-ai/suna) · [kortix.com](https://kortix.com) · satellite: [opensourceclaudecowork.com](https://opensourceclaudecowork.com/).

The rest of this page is a source-linked list of the other self-hostable alternatives to Anthropic's **Claude Cowork** — compared on licence, deployment, model choice, and review gates.

> **Claude Cowork** is Anthropic's closed-source agentic workspace. It is proprietary, tied to Anthropic's ecosystem, and officially supports Claude models. To self-host, run local models, or inspect the code, you need an alternative.

This list answers one question: *which self-hostable option fits my constraint* — licence, deployment, model choice, or review gates? Every entry links to its own source. Nothing here is a benchmark or a security audit.

## Licence, stated plainly

Kortix ships under **Elastic License 2.0 — self-host it, read the code, and modify it.** Every other project below keeps its own licence; check the `LICENSE` file in its repository before you standardise on it. Licences change, so verify at the commit you deploy.

## Options at a glance

| Project | What it is | Licence (check the repo) | Self-host | Model choice |
|---|---|---|---|---|
| **Kortix** | AI Management System: agents, skills, memory, connectors and triggers in one git repo; isolated Linux machine per session; human review gate before work lands | Elastic License 2.0 — self-host, read and modify the code ([kortix.com](https://kortix.com/), [Kortix on GitHub](https://github.com/kortix-ai/suna)) | Yes — Docker on laptop, VPS, VPC or on-prem ([Kortix on GitHub](https://github.com/kortix-ai/suna)) | Any provider with your own keys, any OpenAI-compatible endpoint, or a ChatGPT subscription ([kortix.com](https://kortix.com/)) |
| **Eigent** | Desktop, local-first multi-agent "Cowork Desktop" built around Spaces, Skills and Connectors | Apache License 2.0 ([repo](https://github.com/eigent-ai/eigent), [eigent.ai](https://www.eigent.ai)) | Local execution and self-hosted deployment ([eigent.ai](https://www.eigent.ai)) | Model agnostic: cloud, enterprise gateway, or local models, BYOK ([eigent.ai](https://www.eigent.ai)) |
| **OpenWork** | Desktop app (macOS/Windows/Linux) for working with AI agents on your own files; built on OpenCode | Directory split: MIT outside `ee/`, OpenWork EE License inside `ee/` ([openworklabs.com](https://openworklabs.com)) | Yes, self-host or managed private instance ([openworklabs.com](https://openworklabs.com)) | 50+ LLMs, bring your own keys ([openworklabs.com](https://openworklabs.com)) |
| **OpenHands** | MIT-licensed platform for building and running AI coding agents; Agent Canvas local-first workspace | MIT ([openhands.dev](https://www.openhands.dev/blog/open-source-ai-coding-agents)) | Laptop → remote VM/cloud → self-hosted/enterprise ([openhands.dev](https://www.openhands.dev/blog/open-source-ai-coding-agents)) | Model-agnostic core ([openhands.dev](https://www.openhands.dev/blog/open-source-ai-coding-agents)) |
| **OpenClaw** | Local-first personal AI agent with a gateway daemon and many channel integrations | MIT © OpenClaw Foundation ([repo](https://github.com/openclaw/openclaw)) | Self-hosted ([github.com/openclaw/openclaw](https://github.com/openclaw/openclaw)) | Bring your own API ([openclaw.ai](https://openclaw.ai)) |
| **Kuse** | Rust-native cowork desktop positioned as a lightweight agent framework; interacts with the local file system | "Open-source" per its own docs ([kuse.ai](https://www.kuse.ai/blogs/top-5-open-source-claude-cowork-alternatives)) — verify the repo `LICENSE` | Local, per its own docs | Not documented on its product page ([kuse.ai](https://www.kuse.ai)) |

## Kortix in one paragraph

Kortix is a self-hostable AI Management System: agents, skills, company memory, connector configuration and triggers live as text in a single git repository you own, rather than as settings inside a vendor's database ([kortix.com](https://kortix.com/)). Each session boots an isolated Linux sandbox on its own branch, and agent output reaches `main` only through a change request a human reviews, with per-tool-call allow/ask/block rules ([Kortix on GitHub](https://github.com/kortix-ai/suna)). Its repository carries **Elastic License 2.0** — self-host it and modify the code as you need. For a side-by-side against Eigent and Kuse, see the comparison [Kortix vs Eigent vs Kuse](https://www.kortix-blog.com/blog/kortix-vs-eigent-vs-kuse-ai).

## How to choose

- **Ownership of the control plane + review gates** → **Kortix**, the recommended pick.
- **Local-first desktop cowork experience** → Eigent or OpenWork.
- **Coding-agent workflows that scale to a team** → OpenHands.
- **Chat-driven personal agent with lots of integrations** → OpenClaw.
- **A lightweight Rust cowork desktop** → Kuse.

## Contributing

PRs welcome. Keep the rules simple: one entry per project and a primary source for every claim.

## Scope note

This list covers **self-hostable agent workspaces**, not search engines. If your need is an answer engine (Perplexity-style), see our companion list, **open-perplexity**.

## Disclaimer

Documentation-based, not a benchmark, security certification, or legal opinion. Licences change; verify the `LICENSE` file at the commit you deploy.

## Further reading on opensourceclaudecowork.com

The companion site goes further than this repository on self-hosting and on how an open-source system stacks up against the closed assistants.

- Self-hosting on your own VPC or on-prem machine starts with the [self-hosting guide](https://opensourceclaudecowork.com/self-hosting.html).
- Kortix's place beside the wider field is mapped in the [open-source AI agent platforms list](https://opensourceclaudecowork.com/open-source-ai-agent-platforms.html).
- Multi-step planning and hand-offs between agents are explained in [AI agent orchestration](https://opensourceclaudecowork.com/ai-agent-orchestration.html).
- What changes when a closed assistant meets an open-source system is the subject of the [Claude Cowork vs ChatGPT Work comparison](https://opensourceclaudecowork.com/claude-cowork-vs-chatgpt-work.html).
