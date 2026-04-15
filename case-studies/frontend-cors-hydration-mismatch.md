# Frontend: CORS + Hydration Mismatch

## Symptom

The app loaded in local development, but production users saw a blank page and intermittent fetch failures.

### Raw signals

```text
TypeError: Failed to fetch
Hydration failed because the initial UI does not match what was rendered on the server.
```

## What Happened

The browser was blocking an API call because the server did not allow the production origin, and the page also had a hydration mismatch caused by a client-only value being rendered on the server.

## Root Cause

| Layer | Issue |
|------|-------|
| API | Missing `Access-Control-Allow-Origin` for the deployed domain |
| UI | Server-rendered markup depended on `window`-derived state |
| Deployment | Local and production config diverged |

## Fix

| Step | Action |
|------|--------|
| 1 | Added the production origin to the backend CORS allowlist |
| 2 | Moved browser-only logic behind a client-side effect |
| 3 | Reproduced the issue in a staging build before release |
| 4 | Added a smoke test for the deployed route |

## Verification

| Check | Expected Result |
|------|-----------------|
| Browser console | No hydration warning |
| Network tab | Request returns 200 with correct CORS headers |
| Reload after cache clear | Page renders consistently |

## AI Prompt

```text
Explain this browser error, separate the CORS issue from the hydration issue, and tell me which one is the root cause versus the symptom.
```

## Lesson

When frontend bugs appear in production only, check browser behavior and server headers before rewriting the component tree.
