# Is there an open-source version of Claude Cowork?

No. Claude Cowork is closed software from Anthropic, and Anthropic publishes no source and offers nothing to host. Since September 16, 2026 there is not even a separate product left: [Anthropic folded Cowork into Claude itself](https://support.claude.com/en/articles/12138966-release-notes).

The useful question for a team is what an open alternative lets you own. Three checks settle it: read the source, read the self-host docs, run the install command. The first two take minutes. The third takes one command and a machine. Run them on Kortix, the open-source AI Operating System. There, a git repository holds the agents, their granted tools, the memory files, and the scheduled triggers as plain text. Every session works on its own cloud computer.

## What open source has to mean

Two properties make a tool in this field genuinely open. The read: the source is published, so you can see what the agent does before it touches real work. The run: a documented path installs that project on hardware you control.

A product can pass one and fail the other. An MIT-licensed desktop shell that forwards every task to a closed model API gives you the read and not the run. A self-host page that never names a machine, a port, or a key gives you neither.

## Check 1: the source is readable

For any candidate tool, open the repository and find a file that governs behavior. Issues and docs alone do not count. A thin client around someone else's SDK is a front end.

Kortix passes this one in public. Its platform source lives at [Kortix on GitHub](https://github.com/kortix-ai/suna), and project configuration is plain YAML. The [starter manifest](https://github.com/kortix-ai/suna/raw/dev/packages/starter/templates/base/kortix.yaml) shows the shape:

```yaml
kortix_version: 2
default_agent: kortix

env:
  required: []
  optional: [STRIPE_API_KEY]

agents:
  kortix:
    file: agents/kortix.md
    connectors: all
    secrets: all
    kortix_permissions: all
    skills: all
```

The manifest holds governance: which connectors, secrets, and permissions an agent may use. The agent's behavior is a separate file, `agents/kortix.md`, a stock OpenCode agent file. Skills, memory, and scheduled triggers are files in the same place. You can read all of it before you start a session.

## Check 2: the self-host docs name real machines

A real self-host path names the operating system, the ports, the DNS records, the keys you bring, and the parts that run off the box. Five minutes of reading should let you describe the server you are about to build.

Kortix documents its path ([Read the docs](https://kortix.com/docs)). The self-hosting page describes one Docker Compose stack that the `kortix self-host` CLI installs, configures, and updates. The requirements are concrete. You bring a Linux server with a public IP, A and AAAA records, and ports 80 and 443. You also bring a sandbox provider key, and a model key you add in the web app after the first sign-in.

The page also states what self-hosting does not cover. Sessions run on Platinum, the reference sandbox provider, not on your server. The instance has to stay reachable so those sandboxes can call back. Hosting the platform and hosting the agent's computer are two decisions, and the page separates them.

## Check 3: the install command runs

The third check is the one a landing page cannot fake for long: paste the documented commands on a machine and see whether the stack comes up.

The same page gives this sequence:

```bash
curl -fsSL https://kortix.com/install | bash
kortix self-host init --domain kortix.example.com --admin-email you@example.com
kortix self-host start
```

The bootstrap installs Docker and the CLI. It writes `docker-compose.yml`, `.env`, a `Caddyfile`, and an updater into `~/.config/kortix/self-host/<instance>/`, then starts the stack with a TLS certificate. `kortix self-host doctor` then checks the instance and names every failing requirement. No server to spare? The managed path is shorter: `kortix init` scaffolds a project, and `kortix ship` brings it live in Kortix Cloud.

## What the closed model buys, and what it costs

Anthropic's product removes real work from your side. There is no server, database, or update job to run. Sessions keep working after you close the laptop. Scheduled tasks run with no device online. The desktop app even carries a browser of its own, per [Anthropic's help pages](https://support.claude.com/en/articles/13345190-get-started-with-claude-cowork).

The same pages name the trade. The work happens on Anthropic's servers, and your sessions and files live in your Claude account. An enterprise can route that work through a cloud account it already owns (Amazon Bedrock, Google Cloud, or Microsoft Foundry). Even then there is no self-hosted edition to download ([product page](https://claude.com/product/cowork)). Access is a paid plan, and the product page says that "Price and plans are subject to change at Anthropic's discretion."

The September 16, 2026 merge removed even the option of a separate release. The capability is a feature of Claude now, and [the announcement](https://claude.com/resources/articles/cowork-is-now-claude) describes it as "available from any conversation" (Anthropic's pages, checked October 2026).

## Where Kortix sits

Kortix is the pick. All three checks pass in public. Open source. Read it, fork it, audit it. Run it on Kortix Cloud, in your VPC, or on your own on-prem network. Self-host is free.

Each session runs on a fresh cloud computer with its own branch, and its output reaches `main` as a change request. Who can merge is a permission in the same manifest. You also choose the model and the reach: any model provider with your own keys, and 3,000+ apps in a click, plus MCP, OpenAPI, Postman, GraphQL and raw HTTP.

## When a desktop app fits better

Three open options in this field ship as desktop applications. For one person's local work, that is the right shape. If the job is your own files on your own machine, a desktop app is smaller to adopt than a server.

| Tool | Source you can read | Self-host | Where agent work runs |
|---|---|---|---|
| Kortix | The full platform | Free, one Compose stack | A cloud computer per session |
| Claude Cowork | None published | No | Anthropic's servers |
| OpenWork | Desktop app MIT | Desktop, plus a control plane | Your machine, or one you run |
| open-claude-cowork | MIT desktop app | Desktop | Your machine |
| Eigent | Apache-2.0 repo | Free, with your own keys | Your machine |

OpenWork ([different-ai/openwork](https://github.com/different-ai/openwork)) is a desktop app for macOS, Windows, and Linux, built on OpenCode. Models come from your own keys or run locally through Ollama. Its README states the split plainly: the desktop app and core platform are MIT. The organization control plane under `ee/` is licensed separately: production use needs a subscription, free for organizations up to five people. Files stay local, and a migration path carries a Cowork setup over.

open-claude-cowork ([composio-community/open-claude-cowork](https://github.com/composio-community/open-claude-cowork)) is the project closest to the name in the question. It is an MIT-licensed Electron desktop chat app wrapping the Claude Agent SDK and Composio's tool router, with 500+ app integrations. The shell is open and the model is not: you supply an Anthropic API key and a Composio key, and the reasoning runs on Anthropic's side.

Eigent ([eigent.ai](https://www.eigent.ai)) is a multi-agent desktop app built around Spaces, Skills, and Connectors. Its site says "100% open source" and offers free self-hosting with your own API keys or local models, alongside paid cloud plans. The [repository](https://github.com/eigent-ai/eigent) is Apache-2.0.

Choose a desktop app when the work lives on one person's machine and the output goes to that person. Choose Kortix when a team shares the work. That means the configuration sits where people can review it, several agents run at once, and a change passes a review before it counts. For the rolling state of this question, see [opensourceclaudecowork.com](https://opensourceclaudecowork.com/is-claude-cowork-open-source).
