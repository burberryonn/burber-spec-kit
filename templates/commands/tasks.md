---
description: Build or update tasks.md so execution follows the agreed phases.
scripts:
  sh: scripts/bash/check-prerequisites.sh --json
  ps: scripts/powershell/check-prerequisites.ps1 -Json
---

## Prompt

```text
$ARGUMENTS
```

---

## Intent

Translate the feature plan into actionable tasks that respect the FSD architecture and quality bars. Keep the Markdown simple so every agent (Claude, Codex, Roo Code, etc.) can read and update it.

---

## Steps

1. **Gather inputs**  
   - `{SCRIPT}` resolves `FEATURE_DIR`, `PLAN_PATH`, `SPEC_PATH`, plus supporting files (`research.md`, `data-model.md`, `contracts/`, `quickstart.md`).  
   - Abort if the spec or plan is missing—generate them first.

2. **Review plan phases**  
   - Foundations, Composition, Release slices (P1, P2, P3...).  
   - Extract DoD, CI requirements, and dependencies for each phase.

3. **Draft task list**  
   - Use the format `[ID] [P?] [Story] summary`.  
   - Group tasks under stage headings.  
   - Highlight follow-ups with `[P]` when they are optional or deferred.

4. **Ensure completeness**  
   - Every plan deliverable should map to at least one task.  
   - Include verification work (tests, docs, checklists, ADRs).  
   - Note who owns each task if known, or leave placeholders.

5. **Cross-check with spec**  
   - Confirm tasks cover all functional requirements and data contracts.  
   - Flag mismatches or missing work as `NEEDS CLARIFICATION`.

6. **Agent hand-off**  
   - Provide clear progress markers (`- [ ]` / `- [x]`).  
   - Mention next commands (e.g. `/speckit.implement`) once tasks are ready.  
   - Run `update-agent-context` for the chosen assistant to sync shared notes.

---

## Output Structure

```
# Tasks: Checkout Flow

## Stage 1. Foundations
- [ ] T001 ...

## Stage 2. Composition Layer
- [ ] T010 ...

## Verification & Documentation
- [ ] T090 ...
```
