# System Stack

> **Status**: Placeholder - Needs to be filled out
>
> **Purpose**: Describe the technical shape of the system. This file answers "How is this system built?" not "What should we build?"

## How to Fill This Out

This file should describe the technical foundation of your application.

### What to Find

1. **Frameworks and Versions**
   - What framework are you using? (Next.js, React, Vue, etc.)
   - What version?
   - Any critical dependencies and their versions?

2. **Routing Model**
   - How does routing work in this app?
   - File-based routing? Config-based?
   - Any special routing conventions?

3. **Styling System**
   - CSS framework? (Tailwind, CSS Modules, styled-components?)
   - Component library? (ShadCN, Material-UI, etc.)
   - Any design system constraints?

4. **Data Layer**
   - Database? (PostgreSQL, MySQL, MongoDB?)
   - ORM or query builder? (Prisma, Drizzle, etc.)
   - How is data accessed? (API routes, server components, etc.)

5. **Authentication**
   - Auth provider? (Supabase Auth, NextAuth, Clerk, etc.)
   - How are sessions managed?
   - Where are auth checks performed?

6. **Hosting and Deployment**
   - Where is this deployed? (Vercel, AWS, etc.)
   - CI/CD setup?
   - Environment management?

7. **Testing Tools and Expectations**
   - Testing framework? (Jest, Vitest, Playwright?)
   - What level of testing is expected? (Unit, integration, E2E?)
   - Any testing conventions?

### How to Scan

- Read `package.json` for dependencies and scripts
- Look for framework config files (`next.config.js`, `vite.config.ts`, etc.)
- Check for database schema files (`schema.prisma`, `supabase/`, etc.)
- Look for test configuration (`jest.config.js`, `vitest.config.ts`, etc.)
- Check for deployment configs (`.vercel/`, `Dockerfile`, CI/CD files)
- Look for auth configuration files

### Example Statements

- "We use Next.js App Router (v14+)"
- "ShadCN components only, no custom component libraries"
- "Supabase with RLS enforced in the database"
- "Integration tests use a real database"
- "TypeScript strict mode enabled"

### Key Rule

This file never explains *what to build*. Only *how this system is shaped*.

Keep it factual, stable, and boring. This is reference material that rarely changes.

---

## Your Content Goes Here

Replace this section with your actual stack information extracted from the codebase.

