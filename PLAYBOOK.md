# Reviewer Playbook

`AGENTS.md` tells the agent how to behave. This page is for the other side of the table: the person approving the work. Most of my bad weeks with AI agents came from my side of the loop, not theirs.

## Why agents over-claim

- **"Done" was never defined.** For the agent, a label on the screen meant done. For me, a post sitting on LinkedIn meant done. Nobody wrote that down.
- **Prompts were too big.** "Build a Buffer-style tool, AI-driven, advanced level" is fifteen features in one sentence. The agent touches all of them and finishes none.
- **Silent fallbacks.** The AI provider failed, a template filled in, and the UI still said "AI-generated".
- **The builder graded itself.** The same chat that wrote the code wrote the status report.
- **Straight to production.** No staging meant every mistake was live, and caching hid half the fixes.

## The loop, every task

| Step | Me | Agent |
|---|---|---|
| 1 | Make sure `AGENTS.md` is in the repo. Start a fresh chat with "Read AGENTS.md first." | |
| 2 | Write one task: scope, what is **not** in scope, and the evidence I expect. | |
| 3 | | Posts a PLAN and waits. |
| 4 | Read the plan. Too many files? A module nobody asked for? Reply "NO, remove X, replan." Otherwise "GO". | |
| 5 | | Builds, tests, reports in the fixed format. |
| 6 | Every VERIFIED line needs raw output under it. If not, paste the "no evidence" reply below. | |
| 7 | Open a **new** chat, paste the auditor prompt and the agent's VERIFIED section. Anything FAILED becomes the next task. | Auditor reproduces each claim. |
| 8 | Click through it myself on staging. Only then is it accepted. | |
| 9 | Once a week, a full outside audit of the live product. | |

## Red flags: stop immediately

- A deploy to production without my PROMOTE.
- "VERIFIED" with no command output under it.
- Words like OPERATIONAL, CONNECTED or PUBLISHED in code with no API call behind them.
- The agent asks for a password, token or key, or prints one.
- Ten or more files changed, or a new "layer" or "engine" that wasn't in the task.
- "Simulation" or "mock" without a DEMO_MODE flag and a banner.
- The agent uses up a paid quota "testing" something the task didn't mention.

## Replies I paste

**When "done" arrives with no evidence:**

```
No. Evidence missing. Re-read AGENTS.md sections 1 and 6. Repost your report
with the raw command output for every VERIFIED line, or move the line to
IMPLEMENTED-UNTESTED or NOT DONE. Do not change any code.
```

**When the agent goes off-task:**

```
STOP. This was not the approved task. Go back to the task I approved, exactly
as written. Do not call external APIs, do not ask me for credentials, and do
not start anything new until that task is reported in the AGENTS.md format.
```

## Writing a good task

```
Read AGENTS.md first.

TASK: <feature name>
SCOPE (what a user can do when this is finished):
- ...
NOT IN SCOPE: <everything else>
ALLOWED DATA / API CHANGES: <tables, endpoints>
TESTS YOU MUST WRITE: <list>
VERIFICATION I EXPECT: <command outputs, URLs, screenshots>

PLAN first. Wait for GO. Report in the AGENTS.md format.
```
