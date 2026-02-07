# Global System Specifications

These rules apply by default.

Rules may be added or overridden by creating indexed files under `specs/`.

Example:
- specs/01-project.md
- specs/02-feature-x.md

Later files override earlier ones.

---

## Architecture

- Prefer simple, maintainable architectures.
- Avoid unnecessary abstractions.
- Follow existing architectural patterns in the repository.
- Changes must not break existing contracts without justification.

---

## Coding Standards

- Follow existing code style and conventions.
- Prefer readability over cleverness.
- Avoid premature optimization.
- Remove unused code and comments.

---

## Security

- Do not introduce known insecure patterns.
- Validate all external input.
- Avoid hardcoded secrets.
- Follow least-privilege principles.

---

## Test-Driven Development

- Define tests before or alongside implementation.
- All new functionality must include test coverage.
- Fix failing tests before proceeding.

---

## Decision-Making Policy

- Do not ask for opinions by default.
- Implement the best solution first.
- After completion, document alternative options and trade-offs if relevant.

---

## Documentation Policy

- Project documentation must be created or updated under `docs/`.
- AI-generated tracking documents must go under `.ai-instructions/documents/`.
- Do not mix client-facing documentation with AI internal tracking.
