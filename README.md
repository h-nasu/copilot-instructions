# Copilot Instructions Boilerplate

A reusable boilerplate for building structured AI instruction systems for GitHub Copilot and other coding assistants.

This repository provides a maintainable foundation for defining how AI should understand context, follow project rules, execute tasks, update documentation, and use reusable prompts across a software project.

It is designed for teams and individuals who want AI behavior to be:
- consistent
- auditable
- reusable across projects
- easy to evolve over time

---

## Why this repository exists

AI coding assistants often become inconsistent over time.

Common problems include:
- repeated mistakes across tasks
- missing project context
- inconsistent documentation updates
- unclear rule precedence
- duplicated instruction files
- weak task execution discipline

This boilerplate solves that by organizing AI instructions into a predictable system with:
- a clear entry point
- ordered rule loading
- override/extension mechanics
- task hooks and workflows
- reusable role prompts
- explicit documentation responsibilities

---

## What this repository provides

This project gives you a baseline instruction architecture for AI-assisted development.

It includes:
- a dedicated `.ai-instructions/` system for execution rules and documentation policy
- `AGENTS.md` for defining task-completion expectations
- `.github/copilot-instructions.md` for GitHub Copilot-specific collaboration rules
- reusable prompt roles under `.github/prompts/`
- an extensible structure that can be adapted per project, team, or feature

The goal is not just to “add instructions,” but to create a system that AI can reliably follow.

---

## Core design principles

### 1. Instruction-first execution
AI should read instructions before doing any task.

### 2. Ordered precedence
Rules are applied in index order, so later files can override or extend earlier ones.

### 3. Documentation is part of delivery
A task is not complete until implementation, testing, and documentation are all done.

### 4. Reusability across projects
The structure is intended to be copied, adapted, and maintained in other repositories.

### 5. Human-editable and AI-compatible
Instruction files can be maintained by users and revised by AI when explicitly requested.

---

## Repository structure

```text
.
├── .ai-instructions/
├── .github/
│   ├── copilot-instructions.md
│   └── prompts/
├── .vscode/
├── AGENTS.md
└── README.md
