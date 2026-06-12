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

---
---
# 🧠 AI Anti-Hallucination Prompts

These prompts help reduce confident but incorrect AI debugging responses.

## Evidence Validation Prompt

```text
Do not assume missing information.
If evidence is insufficient, explicitly say what additional logs, metrics, traces, or configuration details are needed before concluding root cause.

[paste logs]
```

## Confidence Ranking Prompt

```text
Rank each hypothesis by confidence level from 1-10.

For every hypothesis, provide:
- supporting evidence
- conflicting evidence
- fastest validation method
- safest rollback option

[paste incident]
```

---

# ⚡ Performance Debugging Prompts

## Bottleneck Analysis Prompt

```text
Analyze this performance issue.

Identify:
1) CPU bottleneck
2) memory bottleneck
3) database bottleneck
4) network bottleneck
5) likely saturation point

[paste metrics + traces]
```

## Latency Investigation Prompt

```text
Given this latency graph and request trace,
identify where time is being spent and what optimization would give the biggest impact first.

[paste trace]
```

---

# 🔒 Security Incident Prompts

## Security Log Analysis Prompt

```text
Review these logs for possible security issues.

Look for:
- suspicious authentication patterns
- privilege escalation
- token misuse
- injection attempts
- unusual traffic spikes

[paste logs]
```

## Payload Risk Analysis Prompt

```text
Analyze this request payload and determine whether it could exploit:
- SQL injection
- XSS
- SSRF
- command injection
- path traversal

[paste payload]
```

---

# 🧪 Regression Testing Prompts

## Regression Prevention Prompt

```text
Given this bug and fix,
generate:
1) regression test cases
2) edge cases
3) load test scenarios
4) rollback validation checks

[paste bug + fix]
```

---

# ☁️ Kubernetes / DevOps Prompts

## Kubernetes Incident Prompt

```text
Analyze this Kubernetes incident.

Identify:
1) failing component
2) likely infrastructure cause
3) whether issue is app-level or cluster-level
4) safest recovery strategy

[paste kubectl describe + logs]
```

## CrashLoopBackOff Prompt

```text
Explain why this pod entered CrashLoopBackOff.

Return:
- probable root cause
- verification commands
- safest fix path
- rollback considerations

[paste pod logs]
```

---

# 🗄️ Database Query Optimization Prompts

## SQL Optimization Prompt

```text
Review this SQL query and execution plan.

Explain:
1) why it is slow
2) scan type used
3) missing indexes
4) whether joins are inefficient
5) safest optimization strategy

[paste query + EXPLAIN]
```

---

# 🌐 Frontend Debugging Prompts

## Frontend Failure Analysis Prompt

```text
Analyze this frontend issue.

Focus on:
- rendering lifecycle
- async state flow
- API timing
- hydration mismatch
- stale cache risks

[paste component + logs]
```

---

# 📊 Observability & Monitoring Prompts

## Observability Analysis Prompt

```text
Given these metrics, traces, and logs,

identify:
1) first bad signal
2) likely cascading failures
3) system saturation indicators
4) whether alerts triggered too late

[paste observability data]
```

---

# 🚨 Incident Commander Prompts

## Incident Command Prompt

```text
Act as an incident commander.

Given this outage:
1) estimate severity
2) define immediate priorities
3) suggest stakeholder communication
4) identify rollback decision points
5) create a triage sequence

[paste incident details]
```

---

# 🧩 Root Cause Deep Dive Prompt

## Deep RCA Prompt

```text
Do a deep root cause analysis instead of a surface-level fix.

Return:
1) trigger event
2) hidden contributing factors
3) why safeguards failed
4) why monitoring failed to detect earlier
5) long-term prevention strategy

[paste incident]
```

---

# 🔥 “What Changed?” Prompt

One of the most effective prompts for real production incidents.

```text
This system was previously stable.

Given the following:
- deploy diff
- config changes
- dependency updates
- traffic changes

identify the MOST likely regression source first.

[paste changes]
```

---

# 📦 Suggested Future Additions

| Section                     | Why It Helps                          |
| --------------------------- | ------------------------------------- |
| AI Mistakes Examples        | Teaches safe AI usage                 |
| Good vs Bad Prompts         | Improves prompt quality               |
| Incident Response Templates | Useful during outages                 |
| Prompt Engineering Tips     | Helps developers ask better questions |
| Vendor-Specific Prompts     | AWS, Docker, Redis, Nginx, React      |
| Copy-Paste CLI Commands     | Practical debugging help              |
| Red Flags Checklist         | Catches dangerous debugging habits    |

---

# ⭐ Recommended Prompt Packs

* Production Outage Prompt Pack
* Kubernetes Emergency Prompt Set
* Frontend Incident Prompt Kit
* SQL Optimization Prompt Library
* SRE On-Call Prompt Collection


Last updated: 2026-04-15
