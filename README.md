# AI Agent Working Contract

A one-page contract I put in every repo before an AI coding agent touches it.

I run my companies as a non-coding founder. AI agents write most of my code. In October 2026 one of them spent three days building a social media platform for me and kept reporting progress: "7 layers live", "AWS infrastructure operational", "posts published to 10 channels".

When I audited it, none of that was true. The AWS account had no Lambda functions, no database, no queue and a bill of $0.00. The "published" posts had never left the server. One health check returned `OPERATIONAL` for a node name I made up on the spot.

The agent wasn't lying on purpose. It was doing what my prompts rewarded: make the screen look finished. Nothing in my instructions asked it to prove anything.

This repo is the fix. It's the contract I now give every agent (Claude Code, Gemini/Antigravity, Cursor, Copilot, local models), and the routine I follow as the person approving the work.

## What's inside

| File | What it's for |
|---|---|
| [`AGENTS.md`](AGENTS.md) | The contract. Drop it in your repo root. Most agents read `AGENTS.md` automatically; for the rest, start every chat with "Read AGENTS.md first." |
| [`PLAYBOOK.md`](PLAYBOOK.md) | How I run a session as the reviewer: the plan → GO → evidence → independent check loop, red flags, and the replies I paste when an agent claims "done" without proof. |
| [`honest-audit.md`](honest-audit.md) | Copy-paste prompt: an honest audit of a codebase an agent has already worked on. Changes nothing, tells you what is real. |
| [`independent-verify.md`](independent-verify.md) | Copy-paste prompt for a fresh chat that re-checks every "VERIFIED" claim. |

## The rules in one screen

1. **No evidence, no "done".** Every claim comes with the command that was run and its raw output, a test result, or a URL that opens. Anything unverified is labelled `NOT VERIFIED`.
2. **No fake data in code.** Status, health, "connected", "published" and every metric must come from a real check. A hard-coded success string is a bug.
3. **One task, one small feature.** Plan first, wait for GO, then build. No surprise modules, dashboards or "agent swarms".
4. **Secrets never in code, chat or logs.** Agents never ask for credentials.
5. **Staging first.** Production only after a human says PROMOTE.
6. **The builder doesn't grade its own work.** Verification happens in a fresh chat with an auditor prompt.

## Does it work?

The first task I gave under this contract was an honest audit of the code from those three days. The same agent that had reported "100% operational" listed its own hard-coded success strings by file and line, flagged security holes it had left open, and wrote `NOT DEPLOYED` next to every AWS service it had claimed. The next task, a security lockdown, came back with a plan, waited for my approval, and only then wrote the code, with tests.

Same model, same project. The only change was the contract.

## Use it

Copy `AGENTS.md` into your repo, adjust section 5 to your stack, and keep the playbook open while you review. Pull requests with rules that caught a real failure in your own projects are welcome.

## About

I'm Noor Siddiqui, a founder in Dubai. I build self-hosted, human-in-the-loop AI systems for B2B trade and compliance, and I'm the founder of IZN AI. More on my [profile](https://github.com/NoorSiddiquiDubai).

MIT licensed.
