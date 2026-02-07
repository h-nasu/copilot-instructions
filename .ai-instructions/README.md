# .ai-instructions

This directory defines how AI should understand, plan, execute, test,
and document work in this repository.

It is designed to be:
- Tool-agnostic
- Model-agnostic
- Editable by users and AI
- Maintainable over time

This README explains:
- What each file and directory is for
- How to add, extend, or override rules
- How AI is expected to use these instructions

---

## Core Concept

All files under `.ai-instructions/` are **instructions**, unless explicitly stated otherwise.
AI must always read and apply them before performing any task.

Instructions may be:
- Written by users
- Generated or revised by AI when explicitly requested

---

## Override and Extension Rules (Very Important)

Rules are applied in **index order**.

- Files with lower index numbers run first
- Files with higher index numbers override or extend earlier rules
- Index format: `00-`, `01-`, `02-`, etc.

Example:
- `specs/00-default.md`
- `specs/01-project.md`
- `specs/02-feature-x.md`

Later files may:
- Add new rules
- Override existing rules
- Narrow or expand scope

This applies to:
- specs/
- hooks/
- workflows/
- templates/
- documents/

---

## Directory Overview

### overview.md
The authoritative entry point.
Defines execution model, precedence, and responsibilities.

### specs.md
Global system rules and policies.
Applies unless overridden by files under `specs/`.

### specs/
Project- or feature-specific system rules.
Use indexed files to override or extend `specs.md`.

### project-docs.md
Defines how **project documentation** must be created and maintained.
Prevents AI from creating documents in arbitrary locations.

### hooks/
Mandatory behavior executed before and after tasks.
Used to enforce planning, testing, and documentation discipline.

### workflows/
Defines how tasks are executed.
Different workflows may exist for planning-only, execution, review, etc.

### templates/
Defines structure for AI-generated outputs.
Templates guide formatting, not logic.

### documents/
AI-generated artifacts such as:
- Plans
- Specifications
- Designs
- Task breakdowns
- Test reports
- Issue analysis

Content here **may include project-specific instructions**
and may influence later task execution.

---

## Language Settings

Language rules for **project documentation** are defined in:
- project-docs.md

Unless explicitly stated:
- Language rules do NOT apply to `.ai-instructions/documents/`

---

## Editing Instructions

- Users may edit any file at any time
- AI may edit instruction files **only when explicitly asked**
- AI must never silently change instructions

---

## Entry Point for AI

AI must always read:
1. overview.md
2. specs.md
3. specs/
4. hooks/
5. workflows/
6. project-docs.md
7. templates/
8. documents/

in that order.
