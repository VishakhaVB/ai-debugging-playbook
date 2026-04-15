# Tools

Useful tools and references for debugging, observability, and AI-assisted workflows.

This page is a practical shortlist, not an exhaustive catalog.

## Debugging Tools

| Tool | Best For | Quick Usage |
|------|----------|-------------|
| Chrome DevTools | Frontend bugs, network failures, performance | Use Network + Console + Performance together |
| Postman | API debugging | Reproduce requests with exact headers and payload |
| curl / httpie | Fast endpoint checks | Great for automation and shell-based triage |
| jq | JSON parsing in logs | Filter noisy payloads into readable signals |
| ripgrep | Code-level tracing | Search symbols, errors, and config keys quickly |

## Log Analysis Tools

| Tool | Best For | Quick Usage |
|------|----------|-------------|
| ELK / OpenSearch | Centralized log search | Filter by trace ID and timeframe first |
| Loki | Lightweight log aggregation | Pair with Grafana dashboards |
| Splunk | Enterprise incident analysis | Build saved searches for repeating failures |
| Vector / Fluent Bit | Log pipeline reliability | Ensure logs are structured before indexing |

## Observability Tools

| Tool | Best For | Quick Usage |
|------|----------|-------------|
| Prometheus | Metrics collection and alerting | Track p95 latency, error rate, saturation |
| Grafana | Visualization and alert dashboards | Build per-service incident views |
| OpenTelemetry | Unified tracing + metrics + logs | Add span context for cross-service debugging |
| Jaeger | Distributed tracing | Follow one request through all hops |
| Datadog | Unified production debugging | Correlate logs, metrics, traces in one place |

## AI Tools

| Tool | Best For | Quick Usage |
|------|----------|-------------|
| ChatGPT | Root cause hypotheses, log interpretation | Ask for ranked causes + verification steps |
| GitHub Copilot | In-editor debugging support | Ask for path tracing before code changes |
| Claude | Long incident timeline analysis | Useful for long logs and postmortem drafting |
| Gemini | Mixed inputs (logs + screenshots + docs) | Good for cross-format debugging context |

## Tool Selection Cheat Sheet

| Situation | Use This First |
|-----------|----------------|
| Frontend bug with no backend error | Chrome DevTools |
| API fails only in production | curl + centralized logs |
| High latency under load | Prometheus + traces |
| Unknown regression after deploy | Diff view + logs + AI analysis |
| Intermittent microservice failure | Trace ID flow in Jaeger / Datadog |

## Minimal Incident Stack (Recommended)

If you want one clean stack to start with:

1. Prometheus + Grafana (metrics + alerts)
2. Loki (logs)
3. OpenTelemetry + Jaeger (traces)
4. ChatGPT or Copilot (analysis support)

Last updated: 2026-04-15
