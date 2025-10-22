---
description: Refresh the project constitution that encodes non-negotiable delivery principles.
scripts:
  sh: scripts/bash/check-prerequisites.sh --json
  ps: scripts/powershell/check-prerequisites.ps1 -Json
---

## Prompt

```text
$ARGUMENTS
```

---

## Goal

Keep `.specify/memory/constitution.md` up to date so every agent (Claude, Codex, Roo Code, etc.) shares the same guardrails about architecture, tooling, and delivery practices.

---

## Steps

1. **Load context**  
   - `{SCRIPT}` locates `FEATURE_DIR`.  
   - If `.specify/memory/constitution.md` exists, read and diff it; otherwise seed it from `templates/memory/constitution.md`.

2. **Capture foundational rules**  
   Include:
   - Stack: Vite + React + TypeScript (strict) + Mantine 7+, Zustand preferred, i18next.  
   - Layout: FSD structure (`app`, `shared`, `entities`, `features`, `widgets`, `pages`, `processes`).  
   - Tooling: ESLint, Prettier, Vitest, GitHub Actions (lint/typecheck/build).  
   - Constraints: No Tailwind unless justified, favour Mantine Emotion, follow Conventional Commits.

3. **Describe delivery workflow**  
   - Sequential loop: Specify → Plan → Tasks → Implement → Verify → Log → Release.  
   - Expectation for ADRs, docs, and changelog updates.  
   - Testing and accessibility requirements.

4. **Call out manual sections**  
   - Keep a clearly marked `Manual additions` area for team-specific norms.  
   - Encourage updates whenever new lessons are learned.

5. **Validate agent compatibility**  
   - Markdown should stay simple, no agent-specific formatting.  
   - Mention that context scripts can sync `.roo/`, `.codex/`, `.claude/`, etc., when the constitution changes.

---

## Output Expectations

```
# Project Constitution

## Stack Guardrails
- ...

## Delivery Workflow
- ...

## Manual additions
<!-- leave placeholders for teams -->
```
