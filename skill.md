---
name: my-superpowers-md
description: Use when creating or updating a repository instruction file such as CLAUDE.md or AGENTS.md, especially when existing guidance must be merged carefully instead of overwritten with a generic template.
---

# my-superpowers-md

Create or update a repository instruction file for the current agent environment.

The goal is to produce a practical instruction file that matches the real project, preserves useful existing guidance, and fills only the missing pieces.

## When to Use

- Need to initialize a new `CLAUDE.md` or `AGENTS.md`
- Need to merge an existing instruction file with a house style or template
- Need to turn project conventions into explicit agent rules
- Need to preserve existing repo-specific guidance while adding missing sections

Do not use when:

- The user only wants a tiny manual edit to an existing file
- The repo already has the right file and the request is unrelated to instruction-file design

## Output Rules

- Claude Code: prefer `CLAUDE.md`
- Codex: prefer `AGENTS.md`
- If the repo already uses a different casing or existing target file, update that file instead of creating a duplicate
- Never overwrite an existing instruction file silently

## Workflow

1. Inspect the repo root for existing instruction files such as `CLAUDE.md`, `AGENTS.md`, and `agents.md`
2. Decide mode:
   - Create mode: no target file exists
   - Merge mode: a target file already exists
3. Reuse the strongest available evidence first: user-provided test data, real data, PDFs, original wording, and existing instruction-file text all outrank agent-authored rewrites
4. Gather only the missing high-signal project information; if critical facts or wording are missing, ask the user before drafting
5. Draft the instruction file using the template below as a starting point, but do not carefully author new rules or polished wording when stronger source material already exists
6. In merge mode, preserve non-conflicting existing guidance, keep repo-specific wording when it is already usable, and surface real conflicts to the user
7. Write the chosen target file

## Guided Questions

Ask only for information that is missing and materially affects the file:

- User background or role
- Project purpose and scope boundary
- Tech stack
- Common commands: install, run, test, build
- Directory structure and key modules
- Coding conventions or collaboration constraints
- Verification expectations before claiming completion
- Missing facts or original wording when the user already has PDFs, existing instruction files, notes, or other stronger source material

## Create Mode

- Start from the template below
- Keep only sections that are relevant to the project
- Prefer concrete repo-specific rules over abstract advice
- Use real commands and real paths when available

## Merge Mode

- Read the existing instruction file completely before editing
- Keep project-specific rules that do not conflict with the new structure
- Add missing sections from the template only where they improve clarity
- If two rules conflict, explain the difference and ask the user which one should win
- Do not rewrite unrelated sections just for style consistency
- Strongly prefer reusing the user's existing test data, real data, PDFs, original wording, and existing instruction-file text over agent-authored rewrites
- If stronger source material exists but is incomplete, ask the user for the missing facts instead of carefully inventing or polishing new content
- Do not carefully author factual, behavioral, or biographical details without user permission when stronger source material is absent

## Template

```markdown
# {CLAUDE.md or AGENTS.md}

## Communication
- Preferred language
- Terminology expectations

## Working Style
- Planning and clarification rules
- Scope-control rules
- Minimal-change preference

## Verification
- Required checks before claiming completion

## Project Context
- User background
- Repo or product purpose

## Development Commands
```bash
# install
# run
# test
# build
```

## Architecture Notes
- Key folders
- Important dependencies
- Risky areas
```

## Common Mistakes

- Blindly overwriting existing repo guidance
- Keeping generic template filler that does not match the repo
- Adding process rules the user did not ask for
- Creating duplicate instruction files because the filename choice was not checked first
- Rewriting user-provided wording when a PDF, original text, or existing instruction file already contains usable language
- Polishing or elaborating factual content without first checking whether the user already has stronger source material
- Carefully drafting details from memory when missing facts should have been confirmed with the user
