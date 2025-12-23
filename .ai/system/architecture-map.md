# Architecture Map

> **Status**: Placeholder - Needs to be filled out
>
> **Purpose**: A high-level map of where things live. This is guardrails for the AI so it never invents structure.

## How to Fill This Out

This file should provide a **spatial map** of your codebase. Where does each type of code belong?

### What to Find

1. **Routing Logic**
   - Where do routes live?
   - How are routes organized?
   - Where is route-level logic handled?

2. **Business Logic**
   - Where does domain logic belong?
   - Service layer? Utils? Components?
   - How is business logic separated from presentation?

3. **Side Effects**
   - Where do API calls happen?
   - Where are mutations performed?
   - How are side effects organized?

4. **Feature Flags**
   - Where are feature flags checked?
   - How are flags configured?
   - Where is flag logic centralized?

5. **Background Work**
   - Where are background jobs triggered?
   - How are async tasks queued?
   - Where do scheduled tasks live?

6. **Data Access**
   - Where are database queries?
   - Where are API clients?
   - How is data fetching organized?

7. **UI Components**
   - Where are reusable components?
   - Where are page-specific components?
   - How is component hierarchy organized?

8. **Configuration**
   - Where is app configuration?
   - Where are environment-specific settings?
   - How is configuration accessed?

### How to Scan

- Map the directory structure - list all top-level directories
- Look for route files (`app/`, `pages/`, `routes/`, `src/app/`, etc.)
- Find API directories (`api/`, `routes/api/`, `app/api/`, etc.)
- Find component directories (`components/`, `src/components/`, `ui/`, etc.)
- Find utility directories (`lib/`, `utils/`, `helpers/`, `src/lib/`, etc.)
- Search for database query patterns (Prisma, Drizzle, raw SQL files)
- Search for job/queue patterns (look for job directories, queue libraries)
- Search for feature flag checks (look for flag libraries, env var checks)
- Identify where business logic lives vs presentation logic
- Note any monorepo structure (packages/, apps/, etc.)

### Example Structure

```
src/
  app/              # Next.js App Router routes
  components/       # Reusable UI components
  lib/              # Business logic and utilities
  hooks/            # React hooks
  types/            # TypeScript type definitions
  api/              # API route handlers
  jobs/             # Background job definitions
```

### Key Rule

This is not human documentation. It is **guardrails for the AI** so it never invents structure.

Be specific about paths and boundaries. Use concrete examples from the actual codebase.

---

## Your Content Goes Here

Replace this section with your actual architecture map extracted from the codebase.

