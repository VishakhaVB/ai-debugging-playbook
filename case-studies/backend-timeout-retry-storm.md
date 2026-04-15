# Backend: Timeout + Retry Storm

## Symptom

The API started returning timeouts, then the error rate climbed after clients retried the same request.

### Raw signals

```text
request timed out after 30000ms
upstream retry count increased from 1 to 4
p95 latency spiked from 480ms to 4.9s
```

## What Happened

A downstream dependency slowed down, the service held requests open too long, and aggressive retries created more load than the system could absorb.

## Root Cause

| Layer | Issue |
|------|-------|
| Service | No timeout budget for downstream calls |
| Client | Retry policy amplified traffic instead of smoothing it |
| Dependency | One slow external call blocked the request path |

## Fix

| Step | Action |
|------|--------|
| 1 | Added hard timeouts around the slow dependency |
| 2 | Reduced retry count and added exponential backoff |
| 3 | Cached non-critical data to avoid repeated calls |
| 4 | Added tracing to verify the next bottleneck |

## Verification

| Check | Expected Result |
|------|-----------------|
| Error rate | Drops after timeout and retry changes |
| Latency | Returns to baseline under similar traffic |
| Traces | Show requests failing fast instead of hanging |

## AI Prompt

```text
Analyze this backend timeout pattern and tell me whether the main issue is slow dependency latency, bad retry logic, or request fan-out.
```

## Lesson

Timeouts are often the first visible symptom. Retry storms are what turn them into incidents.
