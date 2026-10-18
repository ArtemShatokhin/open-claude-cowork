# What Claude Cowork costs, and the free open-source route

Claude Cowork comes only with paid plans, and the free route in this category is open source. Cowork is Anthropic's agentic surface inside Claude. Hand it a multi-step task and it works across your files and tools; you come back to finished work for review. "Free" hides three different promises, and each one has a different answer. Prices and limits below are Anthropic's published US numbers, checked October 18, 2026.

- **A free trial.** The [pricing page](https://claude.com/pricing) and the [Cowork product page](https://claude.com/product/cowork) list no Cowork-only trial. The way in is a paid plan.
- **A free tier.** The $0 Free plan exists, but Cowork is not part of it. Anthropic's help center states the requirement plainly: a paid Claude subscription, on Pro, Max, Team, or Enterprise ([Get started with Claude Cowork](https://support.claude.com/en/articles/13345190-get-started-with-claude-cowork)).
- **Free to self-host.** Not with Cowork. Sessions run on Anthropic's servers, and the source is not published. Self-hosting is what the open-source alternatives offer, and the worked numbers below use Kortix.

## What Cowork costs on each plan

Anthropic offers five plans, and Cowork is part of four of them:

- **Free, $0.** Chat, file work with code execution, projects, connectors. No Cowork.
- **Pro, $17 a month billed annually or $20 billed monthly.** Cowork included. This is the personal entry point.
- **Max 5x, $100 a month; Max 20x, $200 a month.** The same Cowork with a larger allowance.
- **Team, per seat.** Standard seats cost $25 per member monthly or $20 annually. Premium seats cost $125 monthly or $100 annually ([the Team plan article](https://support.claude.com/en/articles/9266767-what-is-the-team-plan)). The plan requires at least 2 members and supports up to 150 seats.
- **Enterprise, $20 per seat a month billed annually, plus usage at API rates.** A 20-seat minimum applies, and usage cost scales with the models and tasks the team runs ([pricing FAQ](https://claude.com/pricing)). Anthropic's usage doc also describes consumption-billed Enterprise variants.

Anthropic notes that its prices exclude tax and that plans can change at its discretion, so treat every figure here as a snapshot. Anthropic is also folding Cowork into the main Claude experience, starting with Pro and Max plans. That changes where you find it; the prices above still hold.

## How the usage limits set the real bill

The seat price buys a fixed allowance. Anthropic's [usage doc](https://support.claude.com/en/articles/11647753-how-do-usage-and-length-limits-work) describes two limits on paid plans: a session limit that resets every 5 hours, and weekly limits that reset once a week. Four mechanics decide how far that allowance goes:

- **Allowances attach to members, not to the team.** The Team plan doc states that limits are per member, cannot be shared or transferred, and one member hitting a limit does not affect anyone else's. A Standard seat carries 1.25x the Pro per-session allowance, and a Premium seat carries 6.25x.
- **One allowance drains across every surface.** Chat, Claude Code, and Cowork spend the same budget, so a morning of coding sessions shrinks the afternoon's Cowork capacity.
- **Agentic work drains it fastest.** Anthropic's Cowork page says it directly: "Claude Cowork consumes limits faster than Chat" ([Pro plan card](https://claude.com/product/cowork)). Its FAQ attributes the drain to sub-agents and tool calls, and the usage doc ties consumption to conversation length, model choice, effort level, and connected tools, which it calls token-intensive.
- **Overflow runs on prepaid usage credits.** An organization can enable them so members keep working past the included limits, with spend caps per member.

## What the open-source route costs: Kortix as the worked example

Kortix is an open-source AI Operating System: your agents, skills, company memory, and connectors in one git repo you own. Any model, your keys, self-hosted or managed cloud.

Three parts make up its cost, and the software is the part that costs nothing:

- **The software: $0.** Open source. Read it, fork it, audit it. Self-host is free.
- **The compute: infrastructure you provision.** Self-hosting runs the stack on infrastructure you pay for: a VPS, a VPC, or your own hardware. No single number exists for this line; it is your cloud bill.
- **The models: your keys, per token.** Any model provider with your own keys. The invoice comes from the model provider and scales with the work you actually run.

If running the stack holds no appeal, Kortix Cloud is the managed route. Free is $0 with 200 credits per month and 1 project. Paid plans start at $50 a month for 5,000 credits, and members are free, sharing one credit pool (current numbers at [kortix.com/pricing](https://kortix.com/pricing)).

## Where the money goes differently

| Cost shape | Kortix, self-hosted | Claude Cowork, Team plan |
| --- | --- | --- |
| Software | Open source, free to run | Bundled into the seat price |
| Capacity | Elastic, metered on your invoice | Fixed allowance per seat, resets weekly |
| Overflow | The next invoice | Prepaid usage credits |
| Model choice | A pricing lever | A capacity lever inside the bundle |
| Where it runs | Your VPS, VPC, or on-prem network | Anthropic's cloud, or your Bedrock, Google Cloud, or Microsoft Foundry account |

The arithmetic for one five-person team makes it concrete. Five Standard seats at Anthropic's published prices cost $100 a month billed annually ($20 × 5, or $1,200 a year), or $125 billed monthly ($25 × 5). Each of the five draws a private allowance, and it also funds their chat and Claude Code use. It resets weekly. The same five people self-hosting Kortix pay nothing for the software. Their bill becomes two invoices they can read directly: the infrastructure and the tokens. On Kortix Cloud, all five sit on the entry paid plan for $50 a month, because members are free and share one credit pool. A credit and a seat allowance are different units, so the figures describe different meters. The useful part is where each bill grows: seats on one side, usage on the other.

The difference also changes how you optimize. On a bundled allowance, moving a routine task to a cheaper model stretches the same budget further. The invoice never moves. On your own keys, the same decision cuts the bill, because every model choice is a pricing decision. Agentic workloads multiply the effect: one task runs many steps, and Anthropic's docs flag tools and high effort settings as the fastest ways to consume allowance. With your own keys, routine steps go to a cheap model, and the expensive model handles only the steps that need it.

## What each route still costs you

Self-hosting trades a seat bill for an operations bill. Someone owns updates, backups, monitoring, and capacity planning, and on the self-hosted route that someone is you. The deployment targets in this repo's README run from Docker on a laptop to on-prem hardware. The operational load scales with how much of that you take on.

Per-token billing has no ceiling. A heavy agentic month bills what it bills, while the same workload on a bundled allowance simply pauses until the weekly reset or until credits cover it. Which behavior costs less depends on the team's usage pattern and its comfort with variable invoices.

Kortix Cloud is not free past the free tier. The $0 plan carries 200 credits a month and 1 project, enough for one person evaluating the product. A team lands on a paid plan quickly.

For one person, the calculus flips. If you already pay for Claude Pro and your workload fits its allowance, Cowork adds nothing to your bill. No open-source route beats money you already spend. The open-source route earns its keep when the workload belongs to a team, when volume keeps outrunning allowances, or when the data and the keys need to stay on your side.

## The short version

For a team running agentic work, Kortix is the pick, and it is the leading open-source alternative to Claude Cowork and ChatGPT Work. The seat bill becomes infrastructure you control. One repo holds the agents, the memory, and the connectors. Model invoices follow actual usage, and no weekly allowance pauses the work when it runs out. The code is [Kortix on GitHub](https://github.com/kortix-ai/suna), and a fuller cost breakdown against the closed assistants lives at [opensourceclaudecowork.com](https://opensourceclaudecowork.com/claude-cowork-pricing).

For one person with a Pro subscription that fits, stay on Cowork. If the actual need is a single-person desktop tool, the README's list includes desktop-first self-hostable options with their own licensing notes.
