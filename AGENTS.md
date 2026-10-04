# AGENTS.md — Study repo conventions

Guidance for **any AI agent** (or human) that edits this repo. Keep this file
current when structure changes.

## What this repo is
A personal **lifelong-learning** system. `Q1/` holds the current quarter's
study plan: 7 specific sub-fields, each one folder with a `field.md` entry
point and a set of section folders (`Sxx-.../plan.md`). Each quarter rotates
to a new set of 7 fields; quarters are built "foundational → unlocks next."

```
Study/
├── AGENTS.md          ← this file
├── roadmap.md         ← original broad roadmap (history / superseded by Q1)
└── Q1/
    ├── README.md      ← quarter index + Mon–Sun rotation + Q2 unlock map
    └── <field>/
        ├── field.md                       ← entry point: why, resources, 2-h template, order
        ├── roadmap-sh-*.md                ← optional external reference tree
        └── Sxx-<slug>/plan.md             ← one folder per roadmap section, full checklist
```

## The 2-hour daily template (non-negotiable shape)
Every session is the same 4-part block, per the field's `field.md`:
1. `0:00–0:05` state the one goal ("by end I can explain X")
2. `0:05–1:00` input (1–2 videos + read, **this field only**)
3. `1:00–1:50` practice (solve problems / active task, this field only)
4. `1:50–2:00` write 2–3 English sentences + 1 gap

## Hard rules (enforce, don't bend)
- **No context switching:** one field per day, one section at a time. Never
  open a second field the same day.
- **In-order study:** sections are learned `S01 → S12`. Do not skip ahead.
- **Core vs stretch:** `S01–S08` is the quarter core (unlocks next quarter);
  `S09–S12` is the stretch/backlog tier.
- **Exit test gates completion:** a section/field is "done" only when its
  exit test (in `field.md`) passes, not when the checklist looks full.

## Editing conventions
- **Checklists:** each `plan.md` uses `- [ ]` task items. Agents may add
  `- [x]` as the user checks off concepts; do **not** delete unchecked items.
- **Notes/Gap boxes:** each `plan.md` ends with `## Notes / log` and
  `## Gap (...)` free-text sections. Fill as the user learns; keep them.
- **Don't rename slugs or reorder S-folders** unless the user asks — the
  `field.md` table and links depend on the `Sxx-<slug>` names.
- **Links are relative:** `field.md` links to `Sxx-<slug>/plan.md`; keep that
  shape when adding sections.
- Keep markdown **flat, no nested tables**; one `##` per major block.

## When adding a new quarter (Q2, Q3, …)
1. Make `Qn/` mirroring `Q1/` (README + one folder per field).
2. Each new field folder = `field.md` + section folders from its source tree.
3. Update the quarter `README.md` rotation table and "what Qn-1 unlocks" map.
4. Leave prior quarters untouched (they're archives, not live).

## Validation / how to check your edits
- Grep each `Sxx-*/plan.md` for `- [ ]` to confirm checklists survived.
- Confirm `field.md` section table row-count matches the actual `Sxx` folders
  (`ls -d S* | wc -l`).
- Markdown lint is not enforced; just keep tables well-formed.

## Do NOT
- Don't introduce build tools, code, or dependencies into this repo — it's
  markdown-only, no runtime.
- Don't "clean up" by removing the external reference trees
  (`roadmap-sh-*.md`) — they're the source of truth for the checklists.
- Don't change the 2-h template timing or the no-context-switching rule;
  those are the system's core invariants.
