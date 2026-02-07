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
