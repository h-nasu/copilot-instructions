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

AI coding assistants become much more useful when they can follow project-specific rules consistently.

However, in many projects, the same problems appear repeatedly:

- the same mistakes happen again
- project rules are not clearly shared with AI
- documentation updates are skipped or inconsistent
- instruction files grow without a clear precedence model
- prompts become scattered and hard to maintain

This repository was created to solve those problems by organizing AI instructions as a structured system instead of a one-off prompt.

---

## What this repository provides

This project gives you a baseline architecture for AI-assisted development.

It includes:

- a dedicated `.ai-instructions/` system for execution rules and documentation policy
- `AGENTS.md` for defining task-completion expectations
- `.github/copilot-instructions.md` for GitHub Copilot-specific collaboration rules
- reusable prompt roles under `.github/prompts/`
- an extensible structure that can be adapted per project, team, or feature

The goal is not just to “add instructions,” but to create a system that AI can reliably follow and teams can maintain over time.

---

## Core design principles

### 1. Instruction-first execution

AI should read instructions before starting any task.

### 2. Ordered precedence

Rules are applied in index order so later files can extend or override earlier rules in a predictable way.

### 3. Documentation is part of delivery

A task should not be considered complete until implementation, testing, and documentation are all done.

### 4. Reusability across projects

The structure is intended to be copied, adapted, and reused in multiple repositories.

### 5. Human-editable and AI-compatible

Instruction files should remain maintainable by users while still being easy for AI systems to consume.

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
```

---

## Directory overview

### `.ai-instructions/`

This is the main instruction system for AI task execution.

It is intended to define:

- execution model
- system rules
- project-specific overrides
- before/after hooks
- workflows
- templates
- documentation rules
- AI-generated working documents

### `AGENTS.md`

This file acts as an execution contract for AI.

It establishes that AI should:

- read `.ai-instructions/` before beginning work
- follow the expected task flow
- treat code, tests, and documentation as required parts of completion

### `.github/copilot-instructions.md`

This file contains GitHub Copilot-oriented collaboration rules.

Its focus includes:

- reducing wasted queries
- avoiding repeated mistakes
- enforcing automatic documentation updates
- encouraging proactive verification and execution

### `.github/prompts/`

This directory stores reusable role-based prompts such as:

- architect
- debugger
- developer
- executor
- producer

These can be used to standardize different AI collaboration modes across projects.

---

## How the instruction system works

The instruction system is designed around a predictable loading order.

AI is expected to read files in this sequence:

1. `overview.md`
2. `specs.md`
3. `specs/`
4. `hooks/`
5. `workflows/`
6. `project-docs.md`
7. `templates/`
8. `documents/`

This layered order allows the project to define broad rules first and then add more specific behavior later.

---

## Override model

Indexed files use ordered precedence such as:

```text
00-default.md
01-project.md
02-feature-x.md
```

This means:

- lower index files establish defaults
- higher index files extend or override earlier rules
- project and feature behavior can evolve without rewriting the entire rule set

This structure helps keep AI instructions maintainable as the repository grows.

---

## Intended use cases

This repository is a good fit if you want to:

- standardize AI behavior across a codebase
- make Copilot instructions more maintainable
- define project-specific coding and documentation rules
- introduce repeatable workflows for AI-driven development
- reduce prompt repetition for common engineering tasks
- create a long-lived instruction system instead of ad hoc prompt files

It is especially useful for:

- teams using GitHub Copilot regularly
- projects with strong documentation requirements
- repositories where AI is expected to follow architecture and workflow rules
- multi-feature projects that need instruction overrides by scope

---

## How to use this boilerplate

### Option 1: Use it as a starting template

Copy the repository structure into your own project and adapt the instruction files to match your team’s workflow.

### Option 2: Adopt only the core instruction system

If you do not need the full structure, start with:

- `.ai-instructions/`
- `AGENTS.md`
- `.github/copilot-instructions.md`

Then expand it as your project matures.

### Option 3: Extend by project or feature

Add indexed files under `specs/`, `hooks/`, `workflows/`, or `documents/` to support:

- project-level rules
- feature-specific rules
- testing policies
- documentation standards
- review or release workflows

---

## Recommended adoption flow

If you are introducing this into a new or existing repository, a practical rollout could look like this:

1. Define global execution rules in `.ai-instructions/specs.md`
2. Add project-specific overrides under `.ai-instructions/specs/`
3. Define required pre/post-task behavior under `hooks/`
4. Create task execution patterns under `workflows/`
5. Define documentation placement and maintenance rules
6. Add reusable role prompts for common collaboration modes
7. Refine the system over time as new patterns emerge

---

## Why this is different from a single prompt file

A single prompt file is easy to start with, but hard to scale.

This boilerplate is structured more like a policy and workflow system:

- rules have locations and precedence
- instructions can evolve safely
- workflows can be standardized
- documentation expectations are explicit
- AI behavior becomes easier to inspect and improve

In other words, this repository treats AI collaboration as part of project architecture rather than a temporary prompt.

---

## Who this is for

This repository is for developers who want more than prompting.

It is for people who want AI to operate inside a defined engineering system.

If you care about consistency, documentation discipline, rule precedence, and reusable AI workflows, this project can serve as a solid foundation.

---

## Acknowledgment

Built as a reusable instruction framework for AI-assisted software development, with emphasis on maintainability, clarity, and efficient collaboration with coding assistants.
```