---
description: Review spec, plan, and tasks to confirm the feature is ready for delivery.
scripts:
  sh: scripts/bash/check-prerequisites.sh --json --require-tasks --include-tasks
  ps: scripts/powershell/check-prerequisites.ps1 -Json -RequireTasks -IncludeTasks
---

## Prompt

```text
$ARGUMENTS
```

Use plain Markdown so every agent (Claude, Codex, Roo Code, etc.) can mirror the output.

---

## Objective

Correlate the specification, plan, and tasks to guarantee that scope, sequencing, and acceptance criteria remain consistent with the Spec Kit standards (FSD + Vite + React + TypeScript + Mantine).

---

## Guidance

1. **Run the helper script**  
   - `{SCRIPT}` resolves `FEATURE_DIR`, `PLAN_PATH`, `TASKS_PATH`, and supporting metadata.  
   - The script fails fast if required files are missing—stop and regenerate them with the matching commands first.

2. **Validate source documents**  
   - `spec.md`: confirm requirements, priorities, and FSD structure.  
   - `plan.md`: ensure phases align with the spec and cover tooling expectations.  
   - `tasks.md`: verify tasks map to plan phases and reference the same deliverables.  
   - `.specify/memory/constitution.md`: check guardrails and non-negotiables.

3. **Cross-check coverage**  
   - Tasks must cover every spec deliverable and plan milestone.  
  - Ensure CI gates (`lint`, `typecheck`, `build`, `test`) are part of the DoD.  
   - Highlight gaps (missing UI states, Mantine theme updates, docs).

4. **Summarise findings**  
   - Status: `OK` or `Issues found`.  
   - Detail mismatches (missing tasks, inconsistent phase, outdated guardrails).  
   - Recommend next steps: e.g. update `plan.md` Phase 2, add tasks, refresh checklists.  
   - Flag `NEEDS CLARIFICATION` items to feed back into specs.

5. **Agent hand-off**  
   - Output should be safe to store in `.roo/`, `.codex/`, or other agent memory stores without restructuring.  
   - Call the relevant agent context script if consensus data changed.

---

## Expected Deliverable

```
Status: OK | Issues found

Highlights:
- [Observation]
- ...

Next steps:
1. [...]
```
