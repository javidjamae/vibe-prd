# Logging and Observability Pattern

> **Status**: Placeholder - Needs to be filled out
>
> **Purpose**: Describes how to implement logging and observability correctly in this codebase.

## How to Fill This Out

This pattern should describe the **mechanics** of logging, monitoring, and observability. It should ensure consistent, useful observability across the codebase.

### What to Find

1. **Which Files to Touch**
   - Where is logging configured?
   - Where are metrics defined?
   - Any observability infrastructure?

2. **What Sequence to Follow**
   - How to add logging
   - How to add metrics
   - How to add tracing
   - How to add error tracking
   - How to add performance monitoring

3. **Common Mistakes to Avoid**
   - Logging too much/too little
   - Missing context
   - Security issues (logging secrets)
   - Performance impact

4. **How to Verify Correctness**
   - How to test logging
   - How to verify metrics
   - How to check observability dashboards
   - What to monitor in production

5. **Examples**
   - Example log statement
   - Example metric emission
   - Example error tracking
   - Example performance monitoring

### How to Scan

- Check `package.json` for logging libraries (Winston, Pino, Bunyan, etc.)
- Search for logging calls in code (`console.log`, `logger`, `log`, etc.)
- Look for error tracking setup (Sentry, Rollbar, etc. - check config files, env vars)
- Check for monitoring/metrics tools (Datadog, New Relic, Prometheus, etc.)
- Find logging configuration files (logger config, log levels, etc.)
- Look for observability utilities or helpers
- Check for structured logging patterns (JSON logs, log formatting)
- Look for performance monitoring setup

### Pattern Structure

```
## Overview
Brief description of the observability system

## Logging System
- What logging library? (Winston, Pino, console, etc.)
- Where are logs sent? (stdout, file, service, etc.)
- Log levels and when to use them

## Adding Logs
1. Import logger
2. Choose appropriate log level
3. Add context
4. Include relevant data
5. Never log secrets

## Log Levels
- error: System errors, exceptions
- warn: Warnings, deprecations
- info: Important business events
- debug: Development debugging
- trace: Very detailed tracing

## Metrics
- What metrics system? (Prometheus, Datadog, etc.)
- What metrics to track
- How to emit metrics
- Metric naming conventions

## Error Tracking
- What error tracking service? (Sentry, Rollbar, etc.)
- How to report errors
- Error context requirements
- When to report vs log

## Performance Monitoring
- What APM tool? (New Relic, Datadog, etc.)
- What to monitor
- Performance budgets
- Slow query tracking

## Structured Logging
- Log format (JSON, text, etc.)
- Required fields
- Context propagation
- Correlation IDs

## Common Mistakes
- Logging sensitive data
- Too many/few logs
- Missing context
- etc.
```

### Key Rule

Patterns never contain feature intent. They describe *implementation mechanics only*.

This pattern should work for any logging or observability need, regardless of what feature it's for.

---

## Your Content Goes Here

Replace this section with your actual logging and observability pattern extracted from the codebase.

