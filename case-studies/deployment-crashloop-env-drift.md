# Deployment: Crash Loop + Env Drift

## Symptom

The app worked locally, passed tests, and then crashed repeatedly after deployment.

### Raw signals

```text
CrashLoopBackOff
error: missing required env var DATABASE_URL
container exited with code 1
```

## What Happened

The production container expected an environment variable that existed in local and staging setups but was missing in the deployed runtime.

## Root Cause

| Layer | Issue |
|------|-------|
| Deployment | Missing or renamed secret/env var |
| Runtime | Startup path failed fast on config validation |
| Process | No preflight check caught the mismatch |

## Fix

| Step | Action |
|------|--------|
| 1 | Compared local, staging, and production environment variables |
| 2 | Restored the missing secret reference |
| 3 | Added startup validation for required config |
| 4 | Added a deployment checklist for future releases |

## Verification

| Check | Expected Result |
|------|-----------------|
| Pod status | Running instead of restarting |
| Startup logs | Clean boot sequence |
| Health checks | Pass consistently after deployment |

## AI Prompt

```text
Explain this CrashLoopBackOff, identify the likely config mismatch, and tell me what to compare between local and production environments.
```

## Lesson

If an app only fails after release, assume config drift before you assume code is broken.
