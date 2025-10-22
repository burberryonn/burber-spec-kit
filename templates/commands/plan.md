---
description: Draft or refresh the feature plan for the FSD + Vite + React + TypeScript + Mantine stack.
scripts:
  sh: scripts/bash/setup-plan.sh --json
  ps: scripts/powershell/setup-plan.ps1 -Json
agent_scripts:
  sh: scripts/bash/update-agent-context.sh __AGENT__
  ps: scripts/powershell/update-agent-context.ps1 -AgentType __AGENT__
---

## Prompt

```text
$ARGUMENTS
```

If you need additional context, ask for it before rewriting the plan.

---

## Responsibilities

1. **Bootstrap metadata**  
   - `{SCRIPT}` returns JSON containing `FEATURE_SPEC`, `FEATURE_DIR`, `PLAN_TEMPLATE`, `BRANCH`, and other pointers.
   - Abort if required files are missing; generate them (e.g. `/speckit.specify`) first.

2. **Collect supporting material**  
   - `templates/plan-template.md` – structure and sections.  
   - `specs/.../spec.md` – requirements and FSD expectations.  
   - `.specify/memory/constitution.md` – global guardrails.

3. **Align with the stack**  
   - Assure Vite + React + TS (strict) + Mantine + Zustand + i18next remain the baseline.  
   - Call out Mantine theme work, routing, data flows, and CI gates.

4. **Outline phases and deliverables**  
   - Phase 0 Research → Phase 1 Design → Phase 2 Tasks → Phase 3 Implementation (extend if needed).  
   - For each phase, list objectives, dependencies, and verification.

5. **Keep the plan agent-neutral**  
   - Use plain Markdown: headings, tables, checklists are fine.  
   - Mention how to sync context scripts for agents: run `update-agent-context` with `__AGENT__` set to `claude`, `codex`, `roo`, etc.  
   - Avoid proprietary formatting that would break IDE-based assistants.

6. **Highlight follow-ups**  
   - Document `NEEDS CLARIFICATION` items.  
   - Reference ADRs, docs, or checklists to be updated.  
   - Confirm DoD (lint, typecheck, build, preview, tests, accessibility).

7. **Post-plan actions**  
   - Encourage running the agent context script for the assistant in use (`claude`, `gemini`, `cursor`, `qwen`, `opencode`, `codex`, `windsurf`, `kilocode`, `auggie`, `roo`, `q`).  
   - Remind the team to share the plan with stakeholders before implementation.

---

## Output Expectations

```
# Feature Plan: ...

## Overview
- ...

## Stack Expectations
- ...

## Phases
1. ...

## Acceptance Matrix
| Deliverable | Status | Notes | Verification |
```
