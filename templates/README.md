# Templates

Reusable debugging templates for incident notes, triage, and repeatable investigation.

Use these templates to keep production debugging consistent across incidents.

## Incident Triage Template

```text
Incident Title:
Date/Time (UTC):
Severity:
Owner:

Symptom:
User Impact:
Affected Systems:

First Alert Source:
First Known Bad Timestamp:
Current Status:

What Changed Recently:
- Code:
- Config:
- Infrastructure:
- Traffic Pattern:

Immediate Actions Taken:
1.
2.
3.

Next 20-Minute Plan:
1.
2.
3.
```

## Root Cause Note Template

```text
Issue Summary:

Trigger Event:

Root Cause:

Why It Was Not Caught Earlier:

Fix Implemented:

Verification Evidence:
- Logs:
- Metrics:
- Traces:
- Tests:

Rollback Plan (if needed):

Prevention Actions:
1.
2.
3.
```

## Post-Incident Follow-up Template

```text
Incident:
Date:

What Worked Well:
1.
2.

What Slowed Us Down:
1.
2.

Detection Gaps:
1.
2.

Action Items:
- [ ] Add alert:
- [ ] Add regression test:
- [ ] Improve runbook:
- [ ] Improve dashboard:

Owner + Due Date:
```

## Fast Debugging Checklist Template

```text
[ ] Reproduced the issue
[ ] Identified first failing layer
[ ] Captured request/trace ID
[ ] Checked recent changes
[ ] Tested one hypothesis at a time
[ ] Verified fix under similar load
[ ] Added prevention guardrail
```

## Usage Tips

| Tip | Why It Helps |
|-----|--------------|
| Keep notes timestamped | Makes incident timeline reliable |
| Capture evidence before patching | Prevents misleading conclusions |
| Keep fixes and verification together | Reduces reopen risk |
| Record prevention actions immediately | Stops repeat incidents |
---
---
📌 Deployment Rollback Template
Rollback Reason:
Deployment Version:
Rollback Trigger Time:

Affected Services:
Current User Impact:

Rollback Steps:
1.
2.
3.

Verification After Rollback:
- Error rate normalized
- Latency stabilized
- Services healthy
- Alerts cleared

Final Status:
🔍 Environment Comparison Template
Issue:
Working Environment:
Failing Environment:

Compare:
- Runtime version:
- Environment variables:
- Database version:
- API endpoints:
- Feature flags:
- Secrets/config:

Observed Differences:
1.
2.
3.
⚡ Performance Investigation Template
Performance Issue:
Affected Endpoint/Service:

Observed Symptoms:
- High CPU:
- High Memory:
- Slow Queries:
- Network Delay:

Metrics Collected:
- p95 latency:
- Error rate:
- Throughput:
- Saturation:

Likely Bottleneck:
Next Verification Step:
🗄️ Database Investigation Template
Database Issue:
Database Type:
Affected Queries/Tables:

Symptoms:
- Slow query
- Deadlock
- Pool exhaustion
- Replication lag

Evidence:
- EXPLAIN output:
- Active sessions:
- Lock information:
- Query timing:

Fix Attempted:
Verification Result:
🌐 Frontend Bug Investigation Template
Frontend Issue:
Browser:
Environment:

Symptoms:
- Hydration mismatch
- Blank screen
- Infinite loading
- Stale data
- API failure

Console Errors:
Network Errors:

Component Affected:
Recent Changes:
Likely Cause:
☁️ Kubernetes Incident Template
Cluster:
Namespace:
Affected Pod/Service:

Incident Type:
- CrashLoopBackOff
- OOMKilled
- Failed scheduling
- Network issue

Evidence:
- Pod logs:
- Events:
- Resource usage:
- Deployment changes:

Immediate Mitigation:
Long-Term Fix:
🔒 Security Investigation Template
Security Incident:
Severity:
Detection Source:

Suspicious Activity:
- Failed logins
- Token misuse
- Traffic spike
- Injection attempt

Affected Systems:
Evidence Collected:
Containment Actions:
Recovery Status:
📊 Monitoring Gap Template
Incident:
Missing Alert:
Why Existing Monitoring Failed:

Metrics Missing:
1.
2.

Logs Missing:
1.
2.

Recommended Alerts:
1.
2.

Dashboard Improvements:
1.
2.
🧩 Root Cause Analysis Deep Dive Template
Incident Summary:

Technical Trigger:
Hidden Contributing Factors:

Why Detection Failed:
Why Recovery Took Time:

System Weaknesses:
1.
2.
3.

Long-Term Prevention Plan:
1.
2.
3.

Last updated: 2026-04-15
