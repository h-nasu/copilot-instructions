# Project Documentation Rules

This file defines how **project documentation** must be created
and prevents AI from creating documentation in unintended locations.

---

## Documentation Location

Project documentation must be created only in approved directories
defined by the project (e.g. `docs/`, `documentation/`, etc.).

AI must not invent new documentation roots unless there are no documentation directory found.
If no documentation directory is found create `docs/` only at repository root.

---

## Language Rules

Define the language(s) for project documentation.

- All project documentation will be created in Japanese

This language rules apply ONLY to project documentation.

They do NOT affect `.ai-instructions/documents/`
unless explicitly stated.

---

## Templates

- Templates under `.ai-instructions/templates/documents/` must be used
- New templates must be referenced in this file

---

## Separation of Concerns

- Project documentation is client- or team-facing
- `.ai-instructions/documents/` is AI internal

---

## Client-Side Documentation Rules

Copilot MUST automatically generate and maintain client-side documentation when implementing or modifying client-facing features.

### Documentation Requirements

- Copilot MUST create documentation for:
  - UI components
  - API integrations
  - State management logic
  - Environment setup
  - Deployment procedures
  - Client configuration

- Copilot MUST organize documentation inside a structured directory.

### Directory Structure

Client-side documentation MUST be placed under:

docs/

Copilot MUST automatically create missing subdirectories when needed.

Recommended structure:

docs/
├── overview.md
├── specifications/
│   ├── architecture.md
│   ├── setup.md
│   └── deployment.md
├── api/
│   └── endpoints.md
├── components/
│   └── <component-name>.md
└── state/
    └── state-management.md

### Strict Restrictions

- Copilot MUST NEVER generate, move, or modify files inside:

  client-requirement/

- The `client-requirement/` directory is reserved strictly for raw client-provided materials.
- Copilot MUST treat `client-requirement/` as read-only.
