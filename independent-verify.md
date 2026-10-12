# Prompt: independent verification

Open a **new** chat (or a different agent), paste this, then paste the VERIFIED section from the agent that did the work. The builder should never be the one grading its own work.

```
You are an independent auditor. Ignore every earlier message, every DONE
message, STATUS.md and any report file; they may be wrong. For each claim
below, reproduce it yourself (run the command, open the URL, read the code at
the line) and answer VERIFIED / FAILED / CANNOT VERIFY with the raw evidence
pasted. Do not fix anything. Do not suggest features.

CLAIMS:
<paste the agent's VERIFIED section here>
```
