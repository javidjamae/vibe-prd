# Navigation Pattern

> **Status**: Placeholder - Needs to be filled out
>
> **Purpose**: Describes how to implement navigation correctly in this codebase.

## How to Fill This Out

This pattern should describe the **mechanics** of adding navigation items, menus, or routing changes. It should be reusable and composable.

### What to Find

1. **Which Files to Touch**
   - List all files that need to be modified
   - Include file paths and what changes are needed
   - Any configuration files?

2. **What Sequence to Follow**
   - Step-by-step order of operations
   - Dependencies between steps
   - When to test between steps

3. **Common Mistakes to Avoid**
   - What goes wrong most often?
   - What should never be done?
   - Pitfalls specific to this pattern

4. **How to Verify Correctness**
   - How to test the navigation works
   - What to check manually
   - Any automated tests needed?

5. **Examples**
   - Concrete example of adding a nav item
   - Show before/after code snippets
   - Reference actual files if possible

### How to Scan

- Search for navigation components (look for `Nav`, `Menu`, `Sidebar`, `Header` components)
- Look for nav/menu configuration files (JSON, TS, or config files that define nav items)
- Find route registration patterns (how routes are defined and registered)
- Look for existing examples of adding nav items (git history, recent changes)
- Check for navigation-related utilities or helpers
- Look for navigation state management (if any)

### Pattern Structure

```
## Overview
Brief description of what this pattern does

## Files to Modify
- `path/to/file1.tsx` - Add nav item definition
- `path/to/file2.ts` - Update route configuration
- etc.

## Step-by-Step Process
1. First step
2. Second step
3. etc.

## Verification
- Check that nav item appears
- Verify routing works
- Test accessibility

## Common Mistakes
- Don't forget to...
- Never do...
```

### Key Rule

Patterns never contain feature intent. They describe *implementation mechanics only*.

This pattern should work for any navigation change, regardless of what feature it's for.

---

## Your Content Goes Here

Replace this section with your actual navigation pattern implementation guide extracted from the codebase.

