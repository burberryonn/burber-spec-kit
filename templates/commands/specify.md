---
description: Create or refresh the specification for an FSD feature built with Vite + React + TypeScript + Mantine.
scripts:
  sh: scripts/bash/create-new-feature.sh --json "{ARGS}"
  ps: scripts/powershell/create-new-feature.ps1 -Json "{ARGS}"
---

## Prompt

```text
$ARGUMENTS
```

---

## Objective

Populate `specs/[feature]/spec.md` with a complete description of the feature, ready for planning and task breakdown. The output must remain agent-agnostic so Codex, Roo Code, Claude, and others can reuse it.

---

## Process

1. **Execute the bootstrap script**  
   - `{SCRIPT}` produces JSON containing `BRANCH_NAME`, `SPEC_FILE`, and directory paths.  
   - Abort if scaffolding fails; resolve missing directories or rerun the CLI.

2. **Apply the template**  
   - Use `templates/spec-template.md` as the baseline structure.  
   - Fill in placeholders with concrete details from discovery/research.  
   - Keep the stack defaults unless there is an approved exception.

3. **Document scope**  
   - Functional requirements grouped by priority/phases.  
   - Non-functional requirements (performance, accessibility, compliance).  
   - FSD alignment: which directories change, shared components reused, new ones introduced.

4. **Capture data contracts and dependencies**  
   - Entities, APIs, events, or external services.  
   - Validation rules and error handling expectations.

5. **Log success metrics**  
   - Define measurable outcomes with owners.  
   - Note follow-up ADRs or docs to create.

6. **List open questions**  
   - Use `NEEDS CLARIFICATION` markers with IDs (`Q1`, `Q2`, ...).  
   - Assign owners and next steps.

7. **Quality check**  
   - Ensure Markdown headings, tables, and lists render cleanly across agents.  
   - Call out next commands (`/speckit.plan`, `/speckit.tasks`) once the spec is approved.

---

## Output Example

```
# Specification For: Checkout Flow
...
## Functional Requirements
- FR-001: ...

## Open Questions
| ID | Question | Owner | Next Step |
|----|----------|-------|-----------|

Next actions:
1. Review with stakeholders.
2. Generate plan via /speckit.plan.
```
