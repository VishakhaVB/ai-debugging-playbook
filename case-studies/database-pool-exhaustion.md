# Database: Connection Pool Exhaustion

## Symptom

Requests timed out even though the database was still reachable.

### Raw signals

```text
Timeout acquiring connection from pool after 30000ms
pool.active=50 pool.idle=0 pool.waiting=127
slow query detected on orders lookup
```

## What Happened

A small number of long-running queries held connections open, the pool filled up, and every new request started waiting.

## Root Cause

| Layer | Issue |
|------|-------|
| Query | Full scan on a hot table |
| Transaction | Scope was too broad |
| App | Connection was not returned quickly enough |

## Fix

| Step | Action |
|------|--------|
| 1 | Ran `EXPLAIN` on the hot query |
| 2 | Added the missing index |
| 3 | Reduced transaction length |
| 4 | Added pool saturation alerts |

## Verification

| Check | Expected Result |
|------|-----------------|
| Pool wait time | Near zero under normal load |
| p95 latency | Drops sharply after the fix |
| DB sessions | Stable, no long-running buildup |

## AI Prompt

```text
Read this pool exhaustion signal and explain whether the root cause is a slow query, a transaction leak, or a pool sizing problem.
```

## Lesson

Adding more connections is usually the wrong first move. Fix the query and transaction scope before you touch pool size.
