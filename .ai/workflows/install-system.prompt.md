# Prompt: Install System Knowledge

You are an AI assistant helping to bootstrap the AI prompt architecture for this repository.

Your job is to scan the existing codebase and extract the information needed to fill out the placeholder files in `.ai/system/` and `.ai/patterns/`.

---

## ⚠️ What This Does

This workflow will **overwrite placeholder files** with actual content extracted from your codebase.

- **Placeholder files** (containing "How to Fill This Out" sections) will be **completely rewritten** with repository-specific information
- **Already-filled files** (without placeholder instructions) will be **skipped** and left unchanged
- The placeholder instructions will be **removed** and replaced with real content

**Before running this**: If you have any placeholder files with important notes or custom instructions you want to preserve, back them up first.

---

## What you will do

You will go through each file in `.ai/system/` and `.ai/patterns/` and:

1. Read the file to check if it's a placeholder or already filled out
2. If it's a placeholder:
   - Scan the codebase to find relevant examples and patterns
   - Extract concrete information from the code
   - **Overwrite the placeholder content** with actual repository-specific content
3. If it's already filled out, skip it and note that it's complete

**Note**: This process will **replace** placeholder content. If a file has been manually edited and contains real content, it will be preserved (you'll skip it). Only placeholder files with "How to Fill This Out" sections will be overwritten.

---

## Process

Work through each file in `.ai/system/` and `.ai/patterns/` in order:

1. **Read the file** to check if it's a placeholder or already filled out
2. **If it's a placeholder** (contains "How to Fill This Out" section):
   - Read the file's instructions carefully - each placeholder file contains detailed guidance on what to find and how to scan
   - Follow the scanning instructions in that file
   - Extract concrete information from the codebase
   - Fill out the file with actual repository-specific content
3. **If it's already filled out**, skip it and note that it's complete

Each placeholder file contains its own detailed instructions on:
- What information to find
- How to scan the codebase for that information
- What examples to look for

Follow those instructions for each file.

---

## Output format

For each file you fill out:

1. **Read the entire file first** to understand its current state
2. **If the file is already filled out** (no "How to Fill This Out" section), skip it and note that it's already complete
3. **If the file is a placeholder**:
   - **Preserve the header** (title, status, purpose) but update status to indicate completion
   - **Remove the placeholder instructions** (everything from "How to Fill This Out" onwards)
   - **Replace with actual content** extracted from the codebase
   - **Include concrete examples** from the actual codebase
   - **Reference actual file paths** when relevant
   - **Be specific** - use real framework names, versions, and patterns

**Important**: This process will **overwrite** placeholder content with actual repository-specific content. The placeholder instructions will be removed and replaced with real information extracted from your codebase.

---

## What to do if information is missing

If you cannot find information for a section:

1. **Document what you searched for**
2. **Explain what might indicate this pattern exists** (even if you didn't find it)
3. **Suggest where this information might be found** (e.g., "Check with team", "Review deployment docs")
4. **Mark clearly** that this section needs manual review

---

## Verification

After filling out each file:

1. **Check that examples are real** - verify file paths exist
2. **Ensure consistency** - patterns should match across files
3. **Test readability** - would a new AI agent understand this?
4. **Flag uncertainties** - clearly mark anything that needs human verification

---

## Goal

Transform placeholder files into actionable, repository-specific guidance that accurately reflects how this codebase actually works.

