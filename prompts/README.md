# Prompts

Copy-paste prompts for debugging with ChatGPT, Copilot, and other AI tools.

Use these when you need to fix errors fast and keep the conversation grounded in real evidence.

## Quick Use Rules

1. Always include exact error text.
2. Add timeframe and environment (local, staging, production).
3. Ask for root cause, not only a patch.
4. Request verification steps and rollback checks.
5. Treat AI output as a hypothesis until validated.

## Log Analysis Prompts

```text
Analyze these logs and return:
1) most likely root cause
2) top 3 alternate causes
3) exact next debugging steps
4) what evidence is still missing

[paste logs with timestamps + request IDs]
```

```text
Group this incident log stream by failure pattern.
Highlight which pattern likely started first and which are secondary effects.

[paste logs]
```

## Stack Trace Prompts

```text
Explain this stack trace from top to bottom.
Point out:
1) first meaningful error
2) likely failing module
3) safest minimal fix
4) test cases to prevent regression

[paste stack trace]
```

```text
I suspect this stack trace is a symptom, not root cause.
List likely upstream causes and how to confirm each quickly.

[paste stack trace + related logs]
```

## Release Diff Prompts

```text
Review this deploy diff and tell me:
1) highest risk change
2) likely production-only failure points
3) whether rollback is safer than patch-forward
4) fastest validation plan

[paste diff]
```

```text
Compare this previous stable release with current release.
Focus on backend issues, frontend bugs, and config drift.

[paste two release summaries or diffs]
```

## Production Incident Prompts

```text
Given this incident timeline, identify the probable trigger event and blast radius.
Then provide a 20-minute triage plan.

[paste timeline + metrics + alerts]
```

```text
Turn this incident data into a short root cause note:
- trigger
- impact
- root cause
- fix
- prevention

[paste notes]
```

## Prompt Quality Checklist

| Check | Why It Matters |
|------|-----------------|
| Includes exact error | Prevents vague answers |
| Includes timestamps | Enables event correlation |
| Includes environment | Avoids local-vs-prod confusion |
| Asks for verification | Reduces false confidence |
| Asks for alternatives | Avoids single-path bias |

Last updated: 2026-04-15
