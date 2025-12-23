# API Endpoints Pattern

> **Status**: Placeholder - Needs to be filled out
>
> **Purpose**: Describes how to create API endpoints correctly in this codebase.

## How to Fill This Out

This pattern should describe the **mechanics** of creating API routes, handlers, and endpoints. It should ensure consistency and correctness.

### What to Find

1. **Which Files to Touch**
   - Where do API routes live?
   - What file structure is used?
   - Any route handler configuration?

2. **What Sequence to Follow**
   - How to create a new endpoint
   - Request/response handling
   - Error handling
   - Authentication/authorization
   - Validation

3. **Common Mistakes to Avoid**
   - Security issues
   - Error handling mistakes
   - Validation oversights
   - Performance issues

4. **How to Verify Correctness**
   - How to test endpoints
   - What to check manually
   - Any automated tests needed?
   - API documentation requirements

5. **Examples**
   - Example endpoint implementation
   - Show request/response structure
   - Error handling example
   - Authentication example

### How to Scan

- Find API route files (`app/api/`, `pages/api/`, `routes/api/`, `src/api/`, etc.)
- Read example API handlers to understand patterns
- Look for auth middleware/helpers (authentication and authorization patterns)
- Find validation libraries/patterns (Zod, Yup, Joi, etc.)
- Check error response formats (how errors are structured and returned)
- Look for API route utilities or shared code
- Check for API documentation or OpenAPI specs
- Look for API testing patterns

### Pattern Structure

```
## Overview
Brief description of the API architecture

## File Structure
- Where endpoints live
- Naming conventions
- Route organization

## Creating an Endpoint
1. Create route file
2. Define handler function
3. Add authentication
4. Add validation
5. Implement business logic
6. Return response
7. Add error handling

## Request/Response Patterns
- Standard request format
- Standard response format
- Error response format

## Authentication & Authorization
- How auth is checked
- How permissions are verified
- Common auth patterns

## Validation
- Input validation approach
- Validation libraries
- Error messages

## Testing
- How to test endpoints
- Test utilities
- Mock data

## Common Mistakes
- Security vulnerabilities
- Missing validation
- etc.
```

### Key Rule

Patterns never contain feature intent. They describe *implementation mechanics only*.

This pattern should work for any API endpoint, regardless of what feature it's for.

---

## Your Content Goes Here

Replace this section with your actual API endpoints pattern extracted from the codebase.

