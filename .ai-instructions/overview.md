# AI Instruction Overview

This file defines the execution contract for AI in this repository.

All instruction files under `.ai-instructions/` are applied **every time**,
unless explicitly disabled by user prompt or workflow.

---

## Flexibility Rule

AI may:
- Propose improvements to instructions
- Generate new instruction files
- Revise existing instructions

ONLY when explicitly requested by the user.

Otherwise, instructions are read-only.

---

## Execution Scope

AI must:
- Read and apply all instruction files
- Respect override rules based on index numbers
- Respect task-specific prompt instructions (e.g. plan-only prompts)

AI must NOT:
- Ignore instructions silently
- Assume missing instructions
- Restrict future instruction edits

---

## Instruction Application Order

Instructions are applied **in this order, always**:

1. overview.md
2. specs.md
3. specs/ (by index)
4. hooks/before/ (by index)
5. workflows/ (by index)
6. hooks/after/ (by index)
7. ai-docs.md
8. project-docs.md
9. templates/
10. documents/ (by index)

Task-specific prompt instructions may further limit execution
(e.g. planning-only, no implementation).

---

## Directory Responsibilities

### specs.md / specs/
Define global and project-specific rules.

### hooks/
Define mandatory steps before and after tasks.

### workflows/
Define how tasks are executed or restricted.

### ai-docs.md
Define Document Model AI must follow.

### project-docs.md
Defines how project documentation must be managed
(regardless of directory name used by the project).

### templates/
Define structure for AI outputs.

### documents/
Stores AI-generated plans, designs, specifications, issues,
and may contain **project-specific execution instructions**.

---

## Override and Extension Rules

All instruction files under `.ai-instructions/` are applied using index order.

- Files with lower index numbers are applied first
- Files with higher index numbers override or extend earlier rules
- Index format must be: `00-`, `01-`, `02-`, etc.

Example:
- `specs/00-default.md`
- `specs/01-project.md`
- `specs/02-feature-x.md`

Later files may:
- Add new rules
- Override existing rules
- Narrow or expand scope

These rules apply to:
- specs/
- hooks/
- workflows/
- templates/
- documents/

AI must always follow index order when reading instructions.

---

## Safety Principle

AI should prefer:
- Explicit instructions
- Indexed overrides
- Documented decisions

over assumptions.
