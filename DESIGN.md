# Git Workbench Design System

Git Workbench should feel like a calm repository tool built by someone who reads commit graphs every day. The graph and command state carry the identity; decoration stays quiet.

## Principles

1. Put the repository graph before supporting explanation.
2. Use Git orange for identity and primary actions, not for every active state.
3. Reserve teal, blue, amber, and red for branch and status semantics.
4. Use sans-serif for teaching and monospace only for commands, refs, hashes, terminal output, and compact metadata.
5. Prefer crisp borders and layered graphite surfaces to rounded cards and heavy shadows.
6. Keep every interactive target visible, keyboard-accessible, and at least 40px high on desktop or 44px on touch layouts.

## Typography

- Interface and teaching: `IBM Plex Sans`, weights 400, 500, and 600.
- Commands and repository state: `JetBrains Mono`, weights 400, 500, 600, and 700.
- Page title: 36px desktop, 24px phone; 1.25–1.35 line height.
- Body: 16px / 1.625.
- Code and terminal: 13px / 1.65.
- Metadata and panel labels: 10–11px with restrained tracking.

## Color

| Token | Value | Use |
| --- | --- | --- |
| Canvas | `#0a0d10` | Page background |
| Rail | `#0e1217` | Navigation |
| Surface 1 | `#12171d` | Panels and rows |
| Surface 2 | `#171d24` | Raised headers and hover |
| Surface 3 | `#1d242c` | Strong raised state |
| Border | `#29323c` | Default separators |
| Border strong | `#3b4652` | Hover and emphasis |
| Text | `#f0f3f6` | Primary content |
| Text muted | `#aeb8c3` | Supporting content |
| Text subtle | `#77838f` | Metadata |
| Git orange | `#f05133` | Brand and primary actions |
| Feature teal | `#2dd4bf` | Success and feature branches |
| Remote blue | `#58a6ff` | Remote state |
| Warning amber | `#d9a21b` | Caution and HEAD markers |
| Danger red | `#f85149` | Invalid and destructive state |

## Spacing and shape

- Base spacing scale: 4, 8, 12, 16, 20, 24, 28, 32, 40, 48, 64, 80px.
- Radii: 4px controls, 7px rows, 10px panels, 12px only for rare large surfaces.
- Desktop navigation rail: 292px; compact rail: 248px.
- Main workspace: 1244px maximum including internal gutters.
- Use shadows only for the mobile drawer and overlays.

## Layout

- Desktop: persistent rail, sticky repository bar, graph-first workspace.
- Command view: command header, scenario and mental model, graph, terminal pair, hands-on repository, related commands.
- Arena: progress summary, level tabs, compact drill rows with text status.
- Playground: graph workspace with a separate mental model and command queue.
- At 840px and below: off-canvas navigation, 16px page gutters, stacked panels, and full-width primary command actions.

## Motion and accessibility

- Interaction feedback: 120–180ms.
- Graph movement: up to 320ms when it explains state.
- The mobile rail animates only after a user action, not when a viewport breakpoint changes.
- Respect `prefers-reduced-motion`; stop cursor blinking and collapse animation durations.
- Preserve visible focus, semantic headings, live result announcements, text completion status, and the `git-arena-done` localStorage key.
