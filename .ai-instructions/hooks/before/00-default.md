# Before Task Hook

Before executing any task, AI must:

1. Analyze the request
2. Define requirements
3. Define constraints
4. Define design
5. Define test strategy
6. Create all the planning documents under `.ai-instructions/documents/`

No implementation may start before these documents exist.

AI must create or update documents in:
- 01-plans/
- 02-specifications/
- 03-designs/
- 04-tasks/
