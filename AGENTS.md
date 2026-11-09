# AGENTS.md — Study repo conventions

Guidance for **any AI agent** (or human) that edits this repo. Keep this file
current when structure changes.

## What this repo is
A personal **lifelong-learning** system. `Q1/` holds the current quarter's
study plan: 7 specific sub-fields, each one folder. Each quarter rotates to a
new set of 7 fields; quarters are built "foundational → unlocks next."

```
Study/
├── AGENTS.md          ← this file
├── roadmap.md         ← original broad roadmap (history / superseded by Q1)
└── Q1/
    ├── README.md      ← quarter index + Mon–Sun rotation + Q2 unlock map
    └── <field>/
        ├── field.md                       ← entry point: why, resources, 2-h template, exit test
        ├── <NN>_<slug>.md                 ← topic doc: resource material + task checklist
        └── WEEK01..WEEK12/plan.md        ← week fields: one folder per week
```

## Layout convention (topic files)
Each field keeps its topic docs under its own folder as `resource/<NN>_<snake>.md`
(learning material) and optionally `task/<NN>_<snake>.md` (checklist).
Topic docs keep their number and descriptive slug, snake_cased for filenames.

- `01-linear-algebra/` is resource-only: one `resource/<NN>_<snake>.md` per
  section, no `task/` checklists.
- `02-basic-statistics/` still uses per-topic folders: `<NN>-<slug>/README.md`.
- Fields 03–07 use `field.md` + `WEEK01..WEEK12/plan.md`.

## The 2-hour daily template
Every session is the same 3-part block, per the field's `field.md`:
1. Input: learn the content for the day's section (read, watch, work examples).
2. Solve problems on that topic until you can reproduce the method from memory.
3. Write an essay on what you learned.

## Hard rules
- **No context switching:** one field per day, one section at a time. Never
  open a second field the same day.
- **In-order study:** sections are learned in the order listed in the field
  doc. Do not skip ahead.
- **Exit test gates completion:** a section/field is "done" only when its
  exit test (in `field.md`) passes, not when the checklist looks full.

## Editing conventions
- **Checklists:** each `task/<NN>_<snake>.md` uses `- [ ]` task items.
  Agents may add `- [x]` as the user checks off concepts; do **not** delete
  unchecked items.
- **Notes/Gap boxes:** each checklist ends with free-text notes/gap
  sections. Fill as the user learns; keep them.
- **Don't rename slugs or reorder section folders** unless the user asks —
  the field doc table and links depend on the folder names.
- **Links are relative:** task docs live at `task/<NN>_<snake>.md` or
  `resource/<NN>_<snake>.md`; keep that shape when adding sections.
- Keep markdown **flat, no nested tables**; one `##` per major block.

## When adding a new quarter
1. Make `Qn/` mirroring `Q1/` (README + one folder per field).
2. Each new field folder = `field.md` + topic folders from its source tree.
3. Update the quarter `README.md` rotation table and "what Qn-1 unlocks" map.
4. Leave prior quarters untouched (they're archives, not live).

## Writing style

Applies to **all prose in this repo**: `field.md` intros, `plan.md` text,
task/resource docs, and any new docs or release notes. Do not apply it to
checklist items, code identifiers, commands, or config keys.

Preserve the writer's voice. Make the minimum effective edit.

Lead with the point. Keep concrete facts: names, dates, numbers, mechanisms.

Use plain verbs and active voice. Use "is" and "has" when they're clearer.

Apply the portability test: if a sentence would fit any product, replace it
with a specific fact.

Do not invent claims, sources, stats, or examples.

Em dashes are not the default rhythm. Use one or two in long drafts only when
they beat a comma or period.

Ban binary contrasts. Cut "This is not X, it's Y" and "Not a X. Not a Y. A
Z." State the preferred option directly.

Cut throat-clearing openers, faux-insight setups, and rhetorical setups.

Ban dramatic colon reveals. Reserve colons for lists, labels, and quotes.

Cut superficial analysis. Drop trailing "-ing" clauses that fake meaning.
State the cause and effect.

Cut importance puffery. State the fact.

Cut interpretive metadiscourse and dramatic mic-drop endings. End on the
clearest concrete sentence.

Ban weasel attribution. Name the source or cut the claim.

Stop synonym cycling. Repeat the clear word.

Ban dramatic fragmentation. Use complete sentences.

Cut summary-recap endings. End on the last concrete point or the next action.

Avoid formatting slop. No mid-sentence bolding, no bullets where prose works,
no headers over short sections. Use code formatting for commands and
variables.

Ban emoji by default. Use one only for UI status markers, diff glyphs, or
test results.

Vary sentence shape only when it helps, not on a rhythm.

## Writing style — personal preferences

These are non-negotiable. Enforce on every edit, and fix existing files when
touched.

- **No trailing parentheticals in headers.** `## Gap (what I still don't
  get)` is banned. Write `## Gap`. The base title carries the meaning; if a
  clarification is needed, put it in the first sentence of the section, not in
  the header.
- **No em-dash as a rhythm crutch.** One or two per draft, only when they
  beat a comma or period.
- **No binary-contrast sentences.** Cut "This is not X, it's Y."
- **No throat-clearing openers or rhetorical setups.** Lead with the point.
- **No mic-drop or summary-recap endings.** End on the last concrete fact or
  next action.
- **No mid-sentence bolding, no headers over short sections, no bullets
  where prose works.**
- **No emoji by default.**
- **No weasel attribution.** Name the source or cut the claim.
- **No synonym cycling.** Repeat the clear word.
- **Complete sentences.** No dramatic fragmentation.

Full style rules: see the "Writing style" section above.

## Validation / how to check your edits
- Grep each topic folder's `task/<NN>_<snake>.md` or `plan.md` for `- [ ]` to
  confirm checklists survived.
- Confirm the field doc's section table row-count matches the actual section
  folders (`ls -d */ | wc -l` from the field dir, excluding `reference/`).
- Markdown lint is not enforced; just keep tables well-formed.

## Do NOT
- Don't introduce build tools, code, or dependencies into this repo — it's
  markdown-only, no runtime.
- Don't change the 3-part daily template or the no-context-switching rule;
  those are the system's core invariants.
