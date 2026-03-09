---
agent: agent
tools: ['read/readFile', 'search/listDirectory', 'edit/editFiles', 'execute/runInTerminal', 'search/fileSearch']
description: 'Run this before any development task to enforce the full workflow'
---

Before starting this task, you MUST:

1. Read `.ai-instructions/overview.md` 
2. Read `.ai-instructions/specs.md`
3. Read all files in `.ai-instructions/specs/` (by index)
4. Read all files in `.ai-instructions/hooks/before/` (by index)
5. Read all files in `.ai-instructions/workflows/` (by index)
6. Confirm you have read them by summarizing key rules found
7. Then proceed with the task: {{task}}
8. After task, read `.ai-instructions/hooks/after/` and execute any post-task requirements
