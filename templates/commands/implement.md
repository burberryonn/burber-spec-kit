---
description: Execute tasks.md and deliver the feature using the agreed FSD stack.
scripts:
  sh: scripts/bash/check-prerequisites.sh --json --require-tasks --include-tasks
  ps: scripts/powershell/check-prerequisites.ps1 -Json -RequireTasks -IncludeTasks
---

## Prompt

```text
$ARGUMENTS
```

---

## Mission

Drive implementation in the sequence defined by `tasks.md`, keeping alignment with `plan.md`, `spec.md`, and Spec Kit guardrails. Output should remain agent-friendly (Codex, Roo Code, Claude, etc.).

---

## Checklist

1. **Load execution context**  
   - `{SCRIPT}` populates `FEATURE_DIR`, `PLAN_PATH`, `TASKS_PATH`, and relevant metadata.  
   - If `tasks.md` is missing or outdated, regenerate it before proceeding.

2. **Re-read supporting docs**  
   - `plan.md`: phases, priorities, CI commitments.  
   - `tasks.md`: DoD, owners, dependencies.  
   - Optional: `research.md`, `data-model.md`, `contracts/`, `quickstart.md`.

3. **Follow the task flow**  
   - Work from foundations → composition → release slices.  
   - Honour `[P]` follow-ups and `NEEDS CLARIFICATION` markers.  
   - Keep implementation within the FSD directories and Mantine styling conventions.

4. **Maintain quality gates**  
   - Run `npm run lint`, `npm run typecheck`, `npm run build`, `npm run preview`, and relevant Vitest suites.  
   - Update checklists, docs, ADRs, and changelog entries as tasks close.  
   - Capture verification evidence inline (test output, screenshots, links).

5. **Agent co-operation**  
   - Surface progress in Markdown or concise tables so other assistants can continue the work.  
   - Trigger the context update script for the chosen agent if shared memory must be refreshed.

---

## Suggested Output

```
## Progress
- [x] T001 ...
- [ ] T002 ...

## Verifications
- lint ✅
- typecheck ✅
- build ⏳ (blocked by ...)

## Notes
- Follow-up on ...
```
