# Confidence Threshold & Failure Detection Rules

AI must continuously evaluate confidence and execution quality
during task execution.

If confidence drops below threshold or failure patterns are detected,
AI must stop normal execution and recommend invoking a specialized role prompt.

---

## Confidence Threshold Rule

AI must self-evaluate confidence at the end of each phase.

Confidence is considered LOW if any of the following are true:
- Multiple assumptions are required
- Requirements are interpreted differently across phases
- The solution feels heuristic or guess-based
- Repeated revisions are needed without convergence

When confidence is LOW:
- Do NOT continue normal execution
- Trigger failure detection
- Recommend a role prompt

---

## Failure Detection Rules

AI must classify the dominant failure type.

---

### Requirement / Planning Failure → Producer

Indicators:
- Requirements are vague, conflicting, or incomplete
- Success criteria are unclear
- Plan changes frequently
- Scope is unstable

Recommended role:
- `producer.prompt.md`

---

### Specification Failure → Architect

Indicators:
- Behavior is undefined or inconsistent
- Interfaces are unclear
- UI/UX expectations are not explicit
- System components lack clear responsibility

Recommended role:
- `architect.prompt.md`

---

### Design Failure → Architect

Indicators:
- Architecture is repeatedly revised
- Code structure feels forced
- Dependencies are unclear or circular

Recommended role:
- `architect.prompt.md`

---

### Task / Procedure Failure → Developer

Indicators:
- Tasks cannot be executed as written
- Task order is incorrect
- Implementation steps are missing

Recommended role:
- `developer.prompt.md`

---

### Implementation Failure → Developer

Indicators:
- Logic errors
- Missing or insufficient tests
- Behavior differs from design

Recommended role:
- `developer.prompt.md`

---

### Debugging Failure → Debugger

Indicators:
- Bugs persist after multiple fixes
- Root cause cannot be identified
- Fixes cause regressions
- Tests are unreliable or flaky

Recommended role:
- `debugger.prompt.md`

---

## Mandatory Behavior

When failure is detected, AI must output:

**Execution Halted**  
**Confidence Level:** Low  
**Detected Failure Type:** <type>  
**Recommended Role Prompt:** <prompt file>  
**Reason:** <concise explanation>

AI must not continue task execution until a role prompt is applied
or the user explicitly instructs to proceed.
