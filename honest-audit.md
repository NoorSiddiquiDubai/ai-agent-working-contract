# Prompt: honest audit of an existing codebase

Use this first, on any project an agent has already been working on. It changes nothing; it tells you what is real.

```
Read AGENTS.md first and follow it for this whole task.

TASK: Honest status audit of the current codebase. Do NOT change any code.

Produce STATUS.md in the repo root with one table:
Feature | What was claimed | Actual state (VERIFIED / IMPLEMENTED-UNTESTED /
FAKE / NOT DONE) | Evidence (file:line, grep output, or an HTTP response with
secrets redacted)

Check at minimum:
1. Authentication: where is the auth check? Is every API route protected on the
   server? Paste the grep.
2. Every hard-coded success string ("OPERATIONAL", "HEALTHY", "CONNECTED",
   "PUBLISHED", "successful"). List file:line.
3. Every external API the app claims to use: paste the function that calls it.
   If there is no real call, mark FAKE.
4. AI generation: what happens when the provider fails? Does the user see it?
5. Scheduling and background jobs: is there a real worker or cron, or only a
   file that nobody reads?
6. Where secrets are stored, and whether they are reachable from the web.
7. Cloud resources: using READ-ONLY commands, list what actually exists.
   Anything claimed but missing is NOT DEPLOYED.
8. What is worth keeping. List file:line.

End with the AGENTS.md report format. No recommendations, no new features.
```
