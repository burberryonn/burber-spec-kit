# Feature Plan: [FEATURE NAME]

**Slug**: `[###-feature-name]` | **Date**: [DATE] | **Ticket**: [link]  
**Spec**: `/specs/[###-feature-name]/spec.md`  
**Agent Workflow**: Compatible with Specify CLI integrations for Claude, Gemini, Copilot, Cursor, Qwen, opencode, Codex, Roo Code, Windsurf, Kilocode, Auggie, and Amazon Q. After saving updates run the agent context script for your assistant if it caches guidance.

---

## Overview

[Summarise the user problem, the desired outcome, and how this feature fits the roadmap. Keep the scope tight and reference the core stack: Vite + React + TypeScript + Mantine + Zustand + i18next.]

---

## Stack Expectations

- **Tooling & Build**: Vite + SWC, TypeScript `"strict": true`, `"noUncheckedIndexedAccess": true`.
- **UI**: Mantine 7+ (`@mantine/core`, `@mantine/hooks`, `@mantine/form`, `@mantine/modals`) using Emotion styling.
- **State**: Zustand as the default choice; add Redux Toolkit only if orchestration across slices is required.
- **Routing**: React Router v6.30+.
- **Forms**: `@mantine/form`.
- **i18n**: `i18next` + `react-i18next`.
- **Quality Gates**: ESLint, Prettier, Vitest + Testing Library, CI jobs (lint/typecheck/build).
- **Agent Notes**: Keep Markdown plain so that CLI and IDE agents (including Codex and Roo Code) can parse links, code fences, and checklists consistently.

---

## Discovery Checklist

- Do we understand the user journey and the FSD slice impact?
- Are Mantine theme requirements, component variants, and accessibility needs documented?
- Are TypeScript strictness, ESLint, Prettier, and Conventional Commits affirmed?
- Do we need new ADRs or updates to architecture docs?
- Any integration risks (APIs, data migrations, third-party services)?

Capture open questions in the backlog or mark them `NEEDS CLARIFICATION`.

---

## Deliverables

### Spec Directory Layout

```
specs/[###-feature-name]/
├─ plan.md
├─ research.md
├─ data-model.md
├─ quickstart.md
├─ contracts/
└─ tasks.md
```

### Source Layout (FSD)

```
src/
├─ app/             # providers, routing, MantineProvider, ErrorBoundary
├─ shared/          # ui, lib, api, config, types, assets
├─ entities/        # domain primitives (User, Session, ...)
├─ features/        # user-facing capabilities (auth/login, theme/toggle, ...)
├─ widgets/         # compositions of entities + features
├─ pages/           # routed views
└─ processes/       # cross-cutting flows (optional)
```

**Notes**: Call out deviations from the standard layout or shared utilities that must be reused.

---

## Phases

1. **Phase 0 – Research**
   - Capture blockers as `NEEDS CLARIFICATION`, expand `research.md`.
   - Sync with context agents as needed (Roo Code, Codex, etc.).
   - Draft ADRs for architectural or tooling decisions.

2. **Phase 1 – Design**
   - Finalise Vite config, TypeScript settings, ESLint, Prettier, Vitest, GitHub Actions.
   - Define Mantine theme tokens, shared UI primitives, and app providers.
   - Record assumptions in `quickstart.md`, ADRs, and roadmap.

3. **Phase 2 – Tasks**
   - Break down work in `tasks.md` with priorities (`[P]`), owners, and DoD.
   - Ensure CI, docs, and verification steps are part of every deliverable.

4. **Phase 3 – Implementation**
   - Implement user stories per priority; keep commits scoped and traceable.
   - Update docs, ADRs, changelog, and mark checklists.
   - Run verification commands after every meaningful chunk.

---

## Acceptance Matrix

| Deliverable / Owner | Status | Notes | Verification |
|---------------------|--------|-------|--------------|
| :                   | :      | :     | :            |

---

## Verification

- `npm run lint`
- `npm run typecheck`
- `npm run build`
- `npm run preview`
- `npm run test`
- Accessibility and visual checks where Mantine components are extended.

---

## Reference IDs & Context

- context7 library lookups:
  - Vite – [ID / notes]
  - React – [ID / notes]
  - TypeScript – [ID / notes]
  - Mantine – [ID / notes]
  - React Router – [ID / notes]
  - Zustand / Redux Toolkit – [ID / notes]
- Related ADRs or decision records: [:]
- Additional documentation pointers: [:]
