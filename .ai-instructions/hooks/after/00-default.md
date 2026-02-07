# After Task Hook

After executing any task, AI must:

1. Run and verify tests
2. Fix failures
3. Update or create:
   - Development summary
   - Test results
   - Issues and countermeasures
4. Store docucments under `.ai-instructions/documents/`
5. Create or Update project documents if necessary

AI must update:
- 05-developments/
- 06-tests/
- 07-changes/
- 08-issues/
