# AI Document Model

This file defines the required AI-generated documents used
to plan, execute, verify, and improve work in this repository.

These documents are authoritative and may influence
subsequent task execution.

---

## General Rules

- AI documents must be created under `.ai-instructions/documents/`
- Each directory represents a phase in task execution
- Index prefixes are mandatory and define execution order
- Documents may be updated iteratively
- Later phases may reference earlier phases

---

## Required Document Phases

### 01-plans/

Purpose:
- Capture AI understanding of the request
- Define approach, assumptions, and constraints

Required before:
- Design
- Task breakdown
- Implementation

---

### 02-specifications/

Purpose:
- Define required UI, APIs, behavior, and constraints
- Clarify what must be built

---

### 03-designs/

Purpose:
- Define architecture and implementation details
- File structure, class design, data flow

---

### 04-tasks/

Purpose:
- Break work into executable tasks
- Each task should be verifiable

---

### 05-developments/

Purpose:
- Record execution results
- Summarize completed work

---

### 06-tests/

Purpose:
- Define test plans
- Record test results, failures, and fixes

---

### 07-changes/

Purpose:
- Track changes made after initial planning
- Record why changes occurred

---

### 08-issues/

Purpose:
- Record issues encountered
- Document countermeasures and lessons learned
