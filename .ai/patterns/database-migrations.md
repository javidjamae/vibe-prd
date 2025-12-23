# Database Migrations Pattern

> **Status**: Placeholder - Needs to be filled out
>
> **Purpose**: Describes how to create and apply database migrations correctly in this codebase.

## How to Fill This Out

This pattern should describe the **mechanics** of database schema changes. It should ensure migrations are created, tested, and applied correctly.

### What to Find

1. **Which Files to Touch**
   - Where do migration files live?
   - What naming convention is used?
   - Any migration tooling configuration?

2. **What Sequence to Follow**
   - How to create a new migration
   - How to write migration SQL/DSL
   - How to test migrations
   - How to apply migrations
   - Rollback procedures

3. **Common Mistakes to Avoid**
   - What breaks most often?
   - Destructive operations to avoid
   - Data migration pitfalls
   - Migration ordering issues

4. **How to Verify Correctness**
   - How to test migrations locally
   - How to verify schema changes
   - How to check migration history
   - What to validate before deploying

5. **Examples**
   - Example migration file
   - Example of adding a table
   - Example of modifying a table
   - Example of data migration

### How to Scan

- Look for migration directories (`migrations/`, `prisma/migrations/`, `supabase/migrations/`, etc.)
- Check migration tooling in `package.json` (Prisma, Drizzle, Supabase CLI, etc.)
- Read existing migration files to understand format and naming conventions
- Check for migration scripts in `package.json` (e.g., `migrate`, `db:migrate`, `supabase db push`)
- Look for migration configuration files
- Check for migration-related documentation or README files
- Look for migration testing patterns

### Pattern Structure

```
## Overview
Brief description of the migration system

## Migration Tool
- What tool? (Prisma, Drizzle, raw SQL, etc.)
- Where are migrations stored?
- How are they versioned?

## Creating a Migration
1. Generate migration file
2. Write migration code
3. Test locally
4. Review changes

## Applying Migrations
1. Local development
2. Staging
3. Production

## Rollback
- How to rollback
- When rollback is safe
- Data preservation

## Common Mistakes
- Never modify existing migrations
- Always test on copy of production data
- etc.
```

### Key Rule

Patterns never contain feature intent. They describe *implementation mechanics only*.

This pattern should work for any database change, regardless of what feature it's for.

---

## Your Content Goes Here

Replace this section with your actual database migration pattern extracted from the codebase.

