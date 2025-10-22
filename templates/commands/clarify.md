---
description: Identify open questions or missing details in the specification and plan.
scripts:
  sh: scripts/bash/check-prerequisites.sh --json
  ps: scripts/powershell/check-prerequisites.ps1 -Json
---

## Prompt

```text
$ARGUMENTS
```

---

## Purpose

Before implementation, surface ambiguities so they can be resolved in `spec.md`, `plan.md`, or supporting research. This command is safe to use with any agent (Claude, Codex, Roo Code, etc.) because it relies on plain Markdown output.

---

## Workflow

1. **Gather inputs**  
   - `{SCRIPT}` loads `FEATURE_DIR`, `spec.md`, and (if present) `plan.md`, `research.md`.  
   - Stop if the spec is missing—run `/speckit.specify` first.

2. **Scan critical sections**  
   - Requirements marked `NEEDS CLARIFICATION`.  
   - Acceptance criteria lacking measurable outcomes.  
   - Missing Mantine component details, routing, state management decisions.  
   - Incomplete DoD items (tests, docs, CI, accessibility).

3. **Record questions**  
   - Use a table or bullet list with IDs (`Q1`, `Q2`, ...).  
   - Include owner, proposed resolution path, and links to context.  
   - Suggest alternatives when possible to speed up decisions.

4. **Echo back recommended updates**  
   - Which files need edits (`spec.md`, `plan.md`, ADR, roadmap).  
   - Which agent workflows should re-run after clarification (e.g. `/speckit.plan`, context scripts).  
   - Note any risk if left unresolved.

---

## Output Skeleton

```
Open Questions:
| ID | Area | Question | Owner | Next Step |
|----|------|----------|-------|----------|
| Q1 | UX   | ...      | ...   | ...      |

Actions:
- Update spec.md section ...
- Ping design for ...
```
