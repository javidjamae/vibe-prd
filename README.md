# AI Prompt Architecture

A repository-native prompt architecture system that helps you build features quickly with AI coding assistants (Cursor, Claude Code) without drifting, skipping steps, or rebuilding context every time.

## What This Is

This is a **template repository** containing a structured set of prompts and patterns that turn your codebase into a self-documenting AI operating system. It separates three concerns:

1. **System knowledge** – how your app works (in `.ai/system/`)
2. **Patterns** – how to do common tasks correctly (in `.ai/patterns/`)
3. **Workflows** – how to create and execute feature PRDs (in `.ai/workflows/`)

## Quick Start

1. **Copy this into your project:**
   ```bash
   # Copy the entire .ai directory structure into your repo root
   cp -r .ai /path/to/your/project/
   ```

2. **Bootstrap the system:**
   - In Cursor or Claude Code, run:
     ```
     @.ai/workflows/install-system.prompt.md
     ```
   - This scans your codebase and fills out the placeholder files with your repository-specific information

3. **Start building features:**
   - Create a PRD: `@.ai/workflows/create-prd.prompt.md`
   - Execute it: `@.ai/workflows/execute-prd.prompt.md PRD: prd/NN-feature.md`

## Structure

```
.ai/
  system/          # System knowledge (stack, conventions, architecture)
  patterns/        # Implementation patterns (migrations, APIs, etc.)
  workflows/       # Workflow prompts (create PRD, execute PRD, install)
```

## Customization

This template provides a solid foundation, but you can extend it:

- **Add your own patterns**: Create new pattern files in `.ai/patterns/` for common tasks specific to your codebase
- **Add system guidelines**: Extend `.ai/system/` files with additional conventions, rules, or architecture details
- **Modify workflows** (optional): The workflow prompts are system-agnostic and should work for most projects, but you can customize them if needed

## Learn More

See `.ai/README.md` for detailed documentation on how the system works.

---

**Note:** This is a template. The files in `system/` and `patterns/` start as placeholders. Run the install workflow to populate them with your repository's actual information.

