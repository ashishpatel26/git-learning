# Git Workbench — Next Implementation Roadmap

Phase-wise plan for what gets built next. Current state (shipped): 143 command pages with commit-graph scenes, full-simulation Playground (files/staging/stash/remote/teammate/detached HEAD/reflog/bisect), 112-drill Practice Arena, learn-by-doing drill per command, tweened graph engine with draw-in edges + pulse dots + confetti.

Each phase: goal, features, acceptance criteria, effort estimate. Phases are ordered by learning-value ÷ effort — do them in order unless something below unblocks a user request.

---

## Phase A — Merge Conflicts (the biggest missing concept)

**Goal:** The #1 real-world git pain is completely absent from the sim. Teach it hands-on.

- Conflict model: `edit <file>` on two branches touching the "same line" → `git merge` halts with `CONFLICT` state instead of auto-merging.
- Conflict UI: side-by-side panel showing `<<<<<<< HEAD / ======= / >>>>>>> feature` with clickable "keep ours / keep theirs / keep both" buttons.
- Commands: `git merge --abort`, `git rebase --continue/--abort`, resolution flow (`edit` → `git add` → `git commit` completes the merge).
- Graph: conflicted merge node pulses red until resolved.
- 8–10 new Arena drills: resolve a merge conflict, abort a merge, resolve mid-rebase, rerere replay.

**Done when:** a user can create, see, resolve, and abort a conflict entirely in the sandbox.
**Effort:** ~1 session. Highest priority — nothing else teaches this.

---

## Phase B — Guided Story Campaign ("Your First Job")

**Goal:** Convert the loose drills into a narrative course with progression.

- 5-chapter campaign: Day 1 (init/commit), Week 1 (branching), Month 1 (team remote flows with `teammate`), The Incident (bisect + revert under pressure), The Refactor (rebase mastery).
- Each chapter = 6–10 sequenced Arena drills with connecting story text and a chapter badge.
- Campaign map screen with locked/unlocked progression (localStorage).
- Completion certificate screen (canvas-rendered, downloadable PNG).

**Done when:** a beginner can go 0→confident by only following the campaign.
**Effort:** ~1 session (mostly content; engine already supports everything).

---

## Phase C — Real Command Syntax Strictness Mode

**Goal:** Sandbox currently accepts loose syntax; real git doesn't. Add optional realism.

- "Strict mode" toggle: require `-m` on commit, reject `git branch` with spaces, unknown flags error like real git (`error: unknown switch`).
- Real-git error messages copied verbatim for the 30 most common mistakes (detached HEAD warning text, non-ff push rejection text, etc).
- `git commit` without staged changes fails in strict mode ("nothing to commit") — teaches the add→commit rhythm properly.
- Arena drills gain a strict-mode bonus star per drill.

**Done when:** muscle memory built in the sandbox transfers 1:1 to a real terminal.
**Effort:** ~half session.

---

## Phase D — Shareable & Persistent State

**Goal:** Let users save, share, and resume.

- Serialize sim state to URL hash (`#state=base64...`) — share any graph situation as a link.
- "Challenge a friend": share an Arena drill link with your solve time.
- Playground autosave to localStorage (resume where you left off).
- Export graph as PNG/SVG button (for docs, slides, teaching).

**Done when:** a teacher can construct a scenario and send students a link to it.
**Effort:** ~half session.

---

## Phase E — Interview Prep Mode

**Goal:** Convert the content into interview-ready recall.

- Flashcard deck auto-generated from the 143 command scenarios (spaced repetition, localStorage scheduling — Leitner boxes, no backend).
- Quiz mode: show a graph before/after pair → "which command did this?" (multiple choice from similar commands).
- Reverse quiz: show a command → pick the resulting graph from 3 renders.
- 20 curated "explain the difference" questions (merge vs rebase, reset vs revert, fetch vs pull...) with model answers hidden behind reveal.

**Done when:** a user can drill for a git interview without leaving the site.
**Effort:** ~1 session.

---

## Phase F — Multi-remote & Team Simulation Depth

**Goal:** Deepen the remote model beyond one origin + one teammate.

- Named teammates (`teammate alice`, `teammate bob`) with distinct colors on the remote lane.
- Fork model: `upstream` + `origin` remotes, `git remote add upstream`, the full fork-sync flow (fetch upstream → rebase → push origin).
- Simulated PR flow: `pr create` / `pr merge` pseudo-commands showing branch → review → squash-merge lifecycle on the graph.
- Push rejection races: teammate pushes while you work → experience the fetch/rebase/push loop.

**Done when:** the open-source contribution workflow (fork → PR) is fully rehearsable.
**Effort:** ~1 session.

---

## Phase G — Polish & Reach

**Goal:** Widen the audience.

- Mobile-first pass on Playground/Arena (graph pinch-zoom, command chips as primary input).
- Keyboard palette (Cmd/Ctrl-K) for jumping to any command page.
- i18n scaffolding: extract UI strings, ship Hindi + Spanish first.
- Light theme (DESIGN.md tokens already define both surfaces).
- SEO: per-command static anchor pages/meta, sitemap, OpenGraph cards using the graph-export from Phase D.
- Optional analytics (privacy-friendly, e.g. plausible) to see which drills users abandon.

**Done when:** Lighthouse ≥95 across the board, shareable per-command URLs unfurl with graph previews.
**Effort:** ~1–2 sessions.

---

## Deliberately Not Planned

- Real git execution (wasm libgit2 / isomorphic-git): the simulation teaches concepts better than raw output, and stays 0-dependency.
- Backend/accounts: localStorage covers progress; no server to maintain.
- Video content: the animated graph IS the video.

## Suggested Order & Sizing Recap

| Phase | Theme | Effort | Impact |
|---|---|---|---|
| A | Merge conflicts | 1 session | ★★★★★ |
| B | Story campaign | 1 session | ★★★★ |
| C | Strict syntax mode | 0.5 session | ★★★★ |
| D | Share/persist state | 0.5 session | ★★★ |
| E | Interview prep | 1 session | ★★★ |
| F | Multi-remote depth | 1 session | ★★★ |
| G | Polish & reach | 1–2 sessions | ★★ |
