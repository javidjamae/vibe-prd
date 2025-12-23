# System Conventions

> **Status**: Placeholder - Needs to be filled out
>
> **Purpose**: Rules the AI must never violate. This encodes your senior-engineer instincts and project standards.

## How to Fill This Out

This file should contain **absolute rules** that must never be broken. These are the guardrails that prevent common mistakes.

### What to Find

1. **File Naming Rules**
   - How are files named? (kebab-case, camelCase, PascalCase?)
   - Any special conventions for components, utilities, tests?
   - Examples of correct vs incorrect naming

2. **Folder Boundaries**
   - What belongs in which folder?
   - What should never be mixed?
   - Clear boundaries between concerns

3. **Files That Must Never Be Modified**
   - Configuration files that are off-limits
   - Generated files
   - Files managed by other systems

4. **Error Handling Standards**
   - How should errors be handled?
   - What error boundaries exist?
   - Logging requirements for errors?

5. **Logging Requirements**
   - What should be logged?
   - Log levels and when to use them
   - Where logs go?

6. **Accessibility Baseline**
   - Minimum a11y requirements
   - Testing requirements
   - ARIA usage guidelines

7. **Code Style Rules**
   - Formatting standards
   - Import ordering
   - Comment conventions

8. **Security Rules**
   - What must never be exposed?
   - Environment variable handling
   - API key management

### How to Scan

- Look at existing file names and directory structure to identify naming patterns
- Read `.gitignore` to see what files are excluded/generated
- Read `.eslintrc`, `.prettierrc`, or similar configs for code style rules
- Search for error handling patterns: `try/catch`, error boundaries, error handling utilities
- Search for logging: `console.log`, `logger`, `winston`, etc. to understand logging patterns
- Look for workspace rules or conventions files (e.g., `.cursorrules`, workspace settings)
- Check for accessibility testing setup or a11y linting rules
- Look for security-related configs or patterns (env var usage, secret management)

### Example Rules

- "Never modify `.env` files directly"
- "All database changes must go through migrations"
- "Components must be in PascalCase files"
- "API routes must validate all inputs"
- "Never commit API keys or secrets"
- "All user-facing errors must be logged with context"

### Key Rule

If the AI breaks a rule, it is because this file was incomplete. Be exhaustive and explicit.

Use imperative language: "Must", "Never", "Always", "Required".

---

## Your Content Goes Here

Replace this section with your actual conventions and rules extracted from the codebase.

