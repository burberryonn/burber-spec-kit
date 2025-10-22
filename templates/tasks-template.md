---
description: "Task board for a feature built with FSD + Vite + React + TypeScript + Mantine."
---

# Tasks: [FEATURE NAME]

**Reference documents**: `/specs/[###-feature-name]/plan.md`, `spec.md`, `research.md`, `data-model.md`, `contracts/`  
**Clarifications**: Track unresolved topics as `NEEDS CLARIFICATION` until they are answered.

> Follow the Analyze → Plan → Do → Verify → Log loop. Keep plain Markdown so any agent (Claude, Codex, Roo Code, etc.) can read and update state.

---

## Task Card Format

`[ID] [P?] [Story] summary`

- `[ID]` – stable identifier (`T001`, `T002`, ...).
- `[P?]` – optional priority, e.g. `[P1]`, `[P0]`.
- `[Story]` – related user story or epic (`US1`, `US2`, ...).
- Provide enough context in the summary so the engineer knows what to do without reopening multiple files.

---

## Stage 1. Foundations

- [ ] T001 Scaffold FSD directories (`app`, `shared`, `entities`, `features`, `widgets`, `pages`, `processes`)
- [ ] T002 Configure toolchain (`package.json`, `tsconfig.*`, `vite.config.ts`, ESLint, Prettier, Vitest)
- [ ] T003 [P] Install baseline plugins (`vite-tsconfig-paths`), `.editorconfig`, Husky/Conventional Commits (if enabled)
- [ ] T004 [P] Wire GitHub Actions (lint, typecheck, build)

---

## Stage 2. Composition Layer

- [ ] T010 Set up app providers (`MantineProvider`, router, i18n, Zustand store)
- [ ] T011 Define Mantine theme (`shared/config/theme.ts`) and shared UI primitives (`shared/ui`)
- [ ] T012 Establish layout shell (`src/pages/_layout.tsx`), error boundaries, navigation
- [ ] T013 [P] Model entities (`src/entities/...`) and mock API/data layer
- [ ] T014 [P] Document architecture (`docs/architecture.md`, `docs/roadmap.md`), add relevant ADRs

**Reminder**: Keep tasks aligned with plan milestones and update DoD when scope shifts.

---

## Stage 3. Release Slice – [Description] (P1)

- [ ] T020 [P1][US1] Prepare domain logic in `src/entities/...`
- [ ] T021 [US1] Implement feature models/services in `src/features/.../model.ts`
- [ ] T022 [US1] Build Mantine UI components in `src/features/.../ui`
- [ ] T023 [US1] Compose widgets/pages (`src/widgets/...`, `src/pages/...`)
- [ ] T024 [US1] Configure routing/navigation (`src/app/router.tsx`)

---

## Stage 4. Release Slice – [Description] (P2)

[Add tasks for the second slice here.]

---

## Stage 5. Release Slice – [Description] (P3)

[Add tasks for later slices or optional work.]

---

## Verification & Documentation

- [ ] T090 Update docs (`docs/architecture.md`, `docs/roadmap.md`, ADRs, changelog)
- [ ] T091 Refresh feature checklists (`specs/[...]/checklists/`)
- [ ] T092 Run `npm run lint`, `npm run typecheck`, `npm run build`, `npm run preview`
- [ ] T093 Add or update Vitest + Testing Library coverage
- [ ] T094 [P] Perform accessibility review for Mantine components, ensure ARIA usage
- [ ] T095 Close the loop in `tasks.md` by marking `[x]` and writing handover notes

---

## Workflow Guidance

- Keep tasks in the same order as they should be executed; re-sequence when priorities shift.
- Use `[P]` to flag follow-ups that are required but not blocking delivery.
- Reference links, tickets, and ADR IDs inline.
- When work completes, update linked plans/specs and close open questions.
