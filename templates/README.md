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

Last updated: 2026-04-15
