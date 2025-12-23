# Feature Flags Pattern

> **Status**: Placeholder - Needs to be filled out
>
> **Purpose**: Describes how to implement feature flags correctly in this codebase.

## How to Fill This Out

This pattern should describe the **mechanics** of adding, checking, and managing feature flags. It should ensure flags are used consistently and safely.

### What to Find

1. **Which Files to Touch**
   - Where are feature flags defined?
   - Where are flags checked?
   - Any flag configuration files?

2. **What Sequence to Follow**
   - How to define a new flag
   - How to check a flag
   - How to enable/disable flags
   - How to roll out gradually
   - How to remove flags

3. **Common Mistakes to Avoid**
   - Flag checking mistakes
   - Rollout issues
   - Flag removal oversights
   - Performance concerns

4. **How to Verify Correctness**
   - How to test with flags enabled/disabled
   - How to verify flag state
   - How to monitor flag usage
   - What to check before removing flags

5. **Examples**
   - Example flag definition
   - Example flag check
   - Example gradual rollout
   - Example flag removal

### How to Scan

- Search for feature flag libraries in `package.json` (LaunchDarkly, Unleash, etc.)
- Look for flag configuration files (JSON, YAML, or code files that define flags)
- Find flag checking patterns in code (search for flag checks, conditional rendering)
- Check environment variable usage for flags (env vars that control features)
- Look for feature flag utilities or helpers
- Check for feature flag documentation
- **Note:** If no feature flag system exists, document that and explain when one might be needed

### Pattern Structure

```
## Overview
Brief description of the feature flag system

## Flag System
- What flag service? (LaunchDarkly, custom, env vars, etc.)
- Where are flags configured?
- How are flags stored?

## Defining a Flag
1. Create flag definition
2. Set default value
3. Document flag purpose
4. Add to flag registry

## Checking Flags
- How to check in components
- How to check in API routes
- How to check in background jobs
- Conditional rendering patterns

## Enabling/Disabling Flags
- How to toggle flags
- Environment-specific flags
- User-specific flags
- Gradual rollout

## Flag Lifecycle
1. Create flag (default: disabled)
2. Develop feature behind flag
3. Enable for testing
4. Gradual rollout
5. Enable for all users
6. Remove flag and code

## Common Mistakes
- Forgetting to remove flags
- Checking flags incorrectly
- etc.
```

### Key Rule

Patterns never contain feature intent. They describe *implementation mechanics only*.

This pattern should work for any feature flag, regardless of what feature it's for.

---

## Your Content Goes Here

Replace this section with your actual feature flags pattern extracted from the codebase.

