---
description: Prepare or update readiness checklists before running `/speckit.implement` or release reviews.
scripts:
  sh: scripts/bash/check-prerequisites.sh --json
  ps: scripts/powershell/check-prerequisites.ps1 -Json
---

## Prompt

```text
$ARGUMENTS
```

---

## Why

Checklists give the team an auditable trail before we switch to execution. They must stay aligned with the spec, plan, tasks, and broader governance rules.

---

## Steps

1. **Collect context**  
   `{SCRIPT}` resolves `FEATURE_DIR` plus paths to `spec.md`, `plan.md`, `tasks.md`, `research.md`, and `quickstart.md`.

2. **Choose checklist types**  
   - Delivery / Release readiness  
   - QA validation  
   - UX review  
   - Security / Compliance  
   Create as many markdown files under `FEATURE_DIR/checklists/` as needed (use `templates/checklist-template.md`).

3. **Author checklist items**  
   - Make each item actionable and measurable.  
   - Reference evidence (PR, test run, screenshot) inline.  
   - Include gates for docs, CI, accessibility, and ADR updates.

4. **Review for alignment**  
   - Confirm the checklist mirrors priorities and DoD from `plan.md` and `tasks.md`.  
   - Ensure `NEEDS CLARIFICATION` items feed back into specs.  
   - Note which roles must sign off (QA, Design, Security).

5. **Agent compatibility**  
   - Keep the Markdown plain; any agent (Claude, Codex, Roo Code, etc.) can toggle `[x]` vs `[ ]`.  
   - After edits, run the relevant agent context script if shared state must be refreshed.

---

## Output Template

```
# Checklist <type>: <feature>

- [ ] Item
- [ ] Item
- [ ] Item

Notes:
- Evidence / links
- Follow-ups
```
