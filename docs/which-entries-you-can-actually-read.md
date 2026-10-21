# Which entries you can actually read

A list can call a project open source while the repository reserves part of its own tree for paying customers. Both are true, and the second decides what you may run next quarter. Kortix is the open-source AI Operating System: your agents, their skills, your company memory, and every connector in one git repo you own, with the agents working on real cloud computers. Open source. Read it, fork it, audit it. That single set of terms over the whole tree is the exception in this field, not the rule.

## The split, written down

OpenWork is the clearest case, and its own files say so. The root `LICENSE` states that "all content that resides under the /ee directory of this repository is licensed under the OpenWork Enterprise Edition (EE) License", and that content outside those directories is MIT. It also notes that content released before the EE License was adopted stays under the license it shipped with.

`ee/LICENSE` is short. Production use needs a paid OpenWork subscription for the right number of people, except for organizations of up to five people, evaluation for up to 30 days, or development and testing. You may modify the software and publish patches, and it is "forbidden to copy, merge, publish, distribute, sublicense, and/or sell the Software".

Eigent states Apache License 2.0 at its repository root. OpenHands states MIT at its root. Read both against the same check.

## What each set of terms lets you do

Read the row you care about, not the label. Every cell comes from the license files named above and below.

| Dimension | Kortix | OpenWork | Eigent | OpenHands |
| --- | --- | --- | --- | --- |
| Terms in the root file | Open source | MIT outside `ee/`, EE License inside | Apache 2.0 | MIT |
| Change the code | Yes | Yes; patches to `ee/` stay under EE terms | Yes, keep license and notices | Yes, keep license and notice |
| Run it commercially | Yes | Yes outside `ee/`; above five people, `ee/` needs a subscription | Yes | Yes |
| Redistribute it | Yes | Not from `ee/` without a subscription | Yes, keep license and notices | Yes, keep license and notice |
| Host it for others | Yes | Not from `ee/` without a subscription | Yes | Yes |

## The check that takes ten minutes

Clone the entry and list its top-level directories. A directory with its own `LICENSE` is the signal, usually named `ee`, `enterprise` or `pro`. Read the root `LICENSE` for the paragraph that names it, because that paragraph draws the boundary and may say an older license still governs older commits.

Do this at the commit you plan to deploy, since terms change between commits and an old fork can carry an old license.

One more check: does the material your team actually edits, the instructions, the grants and the memory, sit inside or outside the reserved directory? If the interesting half of the setup lives where you may not redistribute it, the project is a rental with a readable lobby.

Kortix keeps that half in files a team already clones. An agent is `agents/<name>.md` for behavior plus its block in `kortix.yaml` for governance. Fork the config and you have forked the setup.

The survey of [open-source Claude Cowork projects on GitHub](https://opensourceclaudecowork.com/claude-cowork-github-projects) asks this of more repositories and sorts them by what each keeps.

## Sources
- https://github.com/different-ai/openwork/blob/dev/LICENSE · https://github.com/different-ai/openwork/blob/dev/ee/LICENSE
- https://github.com/eigent-ai/eigent/blob/main/LICENSE · https://github.com/OpenHands/OpenHands/blob/main/LICENSE · https://opensourceclaudecowork.com/claude-cowork-github-projects
