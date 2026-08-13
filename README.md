# Reports — Dev Handoff

Everything a developer needs to build the Reports & Favorites feature, as static files.
No build step, no dependencies — open `index.html` (or publish this folder with GitHub Pages)
and every link works offline.

## Contents

| File | What it is |
| --- | --- |
| `index.html` | Landing page linking to everything below |
| `reports-prototype.html` | Clickable prototype — favorites, dashboard cards, generate flow, report viewer |
| `handoff-doc.html` | Developer handoff: state model, rules, entry points, screens, known stubs |
| `clarifying-questions.html` | 37 behavior questions, filterable by status — 16 unresolved |
| `docs/reports-ux-handoff.docx` | Word version of the handoff doc |
| `docs/clarifying-questions.docx` | Word version of the questions doc |

Each HTML file is fully self-contained (styles, scripts, fonts and images inlined), so
individual files can be shared on their own.

## Publishing with GitHub Pages

1. Commit this folder to a repository.
2. Settings → Pages → Source: *Deploy from a branch*, folder `/handoff-package` (or move
   the contents to the repo root and choose `/`).
3. The landing page is served at `https://<user>.github.io/<repo>/`.

## Before development starts

`clarifying-questions.html` tags every question **Built**, **Decided**, **Proposed**,
**Dev to resolve** or **Needs clarification**, and can be filtered by tag. Settled since the
first draft: favorites and run history are per-user (**Q1**, **Q24**), and a report's
parameters are saved on generate and pre-applied on every later run, date range excluded
(**Q18**, **Q25**, **Q32**).

Still blocking, and worth reading before the first sprint:

- **Q29** — do all reports share one parameter form, or does each have its own schema?
- **Q34 / Q36** — the Copy Link report URL, its access scope and expiry, and what Email sends.
- Whatever remains tagged **Needs clarification** in the doc.

Error and failure states (generation timeout, empty result, permission loss mid-run) are
not yet designed and are open on the design side.

## Design source

Figma: [DEV Handoff v2](https://www.figma.com/design/lqZkGkt2eqXfq2gJ45z0NK/DEV-Handoff-v2?node-id=1033-50945)

Built on the Repair 360 design system — Roboto, Material Symbols (MD3), and the R360 color
and spacing tokens.
