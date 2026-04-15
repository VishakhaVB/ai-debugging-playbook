# Case Studies

Practical incident patterns and debugging writeups drawn from real-world failure modes.

Use these as fast references when you need to compare a live incident against a known pattern instead of guessing from scratch.

## What This Folder Covers

| Area | What You’ll Find |
|------|------------------|
| Frontend incidents | Browser failures, hydration issues, bad state flow, and API integration problems |
| Backend incidents | Timeouts, auth failures, retry storms, and slow request paths |
| Database incidents | Pool exhaustion, lock contention, slow queries, and replication lag |
| Deployment incidents | Crash loops, env drift, config mismatches, and failed rollouts |

## Case Study Index

| Case Study | Problem | Best For |
|------------|---------|----------|
| [Frontend: CORS + hydration mismatch](frontend-cors-hydration-mismatch.md) | App breaks in the browser, but only in one environment | Frontend debugging under production pressure |
| [Backend: timeout + retry storm](backend-timeout-retry-storm.md) | Requests slow down, then fail harder under load | Latency, saturation, and cascading failure analysis |
| [Database: connection pool exhaustion](database-pool-exhaustion.md) | Pool is full, queries pile up, and requests time out | SQL bottlenecks and transaction scope problems |
| [Deployment: crash loop + env drift](deployment-crashloop-env-drift.md) | App runs locally but crashes after release | Release validation and production-only failures |

## How To Use These Cases

1. Match the symptom first, not the technology label.
2. Read the raw error, then the root cause, then the fix.
3. Compare the failure pattern with your incident timeline.
4. Copy the verification steps before changing code or config.
5. Use the AI prompt examples as a starting point, not the final answer.

## Pattern Library

| Pattern | What It Usually Means |
|---------|-----------------------|
| Works locally, fails in prod | Environment mismatch, secrets, routing, or build differences |
| Only fails under load | Concurrency, pool limits, retry storms, or downstream saturation |
| One browser breaks | Browser-specific behavior, cached assets, extensions, or hydration issues |
| One deploy breaks everything | Config drift, missing env vars, bad migration, or rollback gap |
| Error changes after retry | Non-idempotent behavior, queue duplication, or cascading failure |

## Maintenance Notes

- Add new case studies when a real incident teaches a reusable pattern.
- Keep examples short, factual, and tied to evidence.
- Prefer postmortem-grade clarity over generic troubleshooting tips.

Last updated: 2026-04-15
