---
name: create-prd
description: >-
  Create or edit a PRD (Product Requirement Document) for a single feature or product using
  Figma's public PRD format: Problem Alignment (The Problem, High-Level Approach, Goals &
  Success), Solution Alignment (prioritized Key Features, Key Flows with mocks, Open Issues &
  Key Decisions), and Launch Readiness (Key Milestones, a cross-functional Launch Checklist
  covering Support, Growth & Data, Marketing, Enterprise, Platform, Security & Privacy). Use
  this skill any time someone asks to write, draft, or review a PRD for ONE feature or launch,
  even if they don't use those exact terms (e.g. "document this feature before we ship it,"
  "prep the PRD to hand off to engineering," or attaching mocks/a Figma link for a flow). If
  they instead want a strategic-vision document spanning several initiatives prioritized with
  MoSCoW (not a single feature), ask before applying this structure.
---

# Create PRD (Figma format)

Create and edit single-feature PRDs using the format Figma made public for its own teams
([source](https://coda.io/@yuhki/figmas-approach-to-product-requirement-docs)). Its value over
a generic template is that it disciplines the separation of **why** (Problem Alignment) from
**what** (Solution Alignment) from **how it ships** (Launch Readiness) — so engineering,
design, and the support/marketing/legal teams can align at each phase without mixing product
debate with execution debate.

## When to use this skill

Trigger this skill to create or edit a PRD for **a single feature or launch**. It's the right
skill when the user:
- Explicitly asks for Figma's format, or mentions Problem/Solution Alignment, Launch
  Readiness, key flows, or a launch checklist.
- Needs to document a feature to hand off to engineering/design and wants to be explicit
  about what's shipping, what isn't, and who needs to sign off before it goes live.
- Attaches mocks, a Figma link, or describes a user flow/interaction that needs documenting
  as part of the PRD.

This is **not** the right skill if the user wants a strategic-vision document with several
initiatives organized by pillar and prioritized with MoSCoW (Context → Strategic Pillars →
Initiatives → Phases) — in that case, ask whether they already have a template for that
instead of applying this single-feature structure. If it's unclear which one fits (e.g. they
just say "write me a PRD" with no further context), ask whether it's one feature or a
multi-initiative vision before picking a template.

## Before writing: interview the user

Don't invent the problem, the metrics, or the flows — this format is only as good as the
content being real. If the user already pasted or attached information (a brief, notes, a
prior doc, a Figma link), pull from that instead of asking again. If key information is
missing, ask targeted questions — don't fire off all 9 at once if some are already answered:

1. **Feature/product**: name and a one-line description.
2. **The Problem**: what opportunity is being addressed, why it matters now for the user and
   the business, what insight backs it up (data, feedback, research) — and explicitly **what
   this is NOT going to solve** (to keep scope from creeping on its own).
3. **High-Level Approach**: the direction of the solution in broad strokes, without falling
   into implementation detail — just enough for someone to picture possible directions and
   the rough size of the effort.
4. **Goals & Success**: what metrics are expected to move and why those and not others.
5. **Key Features**: what capabilities are included, with priority, and what's explicitly
   deferred to a future phase (don't omit this — naming it makes clear it was considered and
   deliberately dropped for now).
6. **Key Flows**: the user journeys that need documenting. If the user gives a Figma link, see
   "If there are Figma mocks" below. If there are no mocks, ask for a step-by-step description
   detailed enough for someone to understand the flow without seeing it.
7. **Open Issues & Key Decisions**: what's still unresolved and what decisions were debated
   (and why they were decided that way) — this is what tends to get skipped most, and it's
   what adds the most value by keeping the document from hiding trade-offs.
8. **Key Milestones**: relevant phases (dogfooding, beta, launch...) with an approximate date,
   audience, and what's being validated at each one.
9. **Launch Checklist**: who needs to review before shipping (Support, Growth & Data,
   Marketing, Enterprise, Platform, Security & Privacy) and what specific question applies to
   each. If the user doesn't have some answers yet, say so explicitly with
   `[PENDING: confirm with {team}]` instead of inventing them — the value of this block is
   forcing the question, not filling it with a guess.

If the user wants to move fast, offer a first draft with what you already know and mark gaps
with `[PENDING: ...]` instead of blocking progress waiting on answers to everything.

### If there are Figma mocks

If the user shares a `figma.com` link for the Key Flows, use the Figma MCP server's tools
(`get_design_context`, `get_screenshot`, `get_metadata`) to pull in the screens or a summary
of the flow instead of asking them to describe it from scratch. If the server isn't
authorized in this session, say so and ask the user for a screenshot or description of the
flow instead — don't block the rest of the document on this.

## Required document structure

Always follow this skeleton (see `assets/template.md` for the full fill-in-ready template).
Don't rename or reorder the three blocks — they're what makes the document recognizable
against any other PRD and comparable across features.

**Header**: feature/project name, and a short metadata table (Author, Status — Draft/In
Review/Approved —, Team, Created date, Target launch date, Stakeholders/reviewers). If the
user doesn't give a piece of data, use `[PENDING: ...]` instead of dropping the row.

### BLOCK I — Problem Alignment
1. **The Problem** — the opportunity, why it matters for the user and the business, the
   insights backing it up, and an explicit **"What we are NOT solving"** subsection.
2. **High-Level Approach** — enough context to picture possible directions and the rough size
   of the effort, without solution detail yet.
3. **Goals & Success** — table `Metric | Target | Why it matters`.

### BLOCK II — Solution Alignment
4. **Key Features** — organized by priority (now vs. future), clearly marking what's
   explicitly deferred to a later release.
5. **Key Flows** — one per relevant user journey, with embedded or linked mocks/screenshots
   and enough clickthrough detail to follow the flow without ambiguity.
6. **Open Issues & Key Decisions** — table or list of
   `Question/Decision | Status | Trade-offs considered | Resolution (if any)`.

### BLOCK III — Launch Readiness
7. **Key Milestones** — table `Milestone | Date | Audience | What's being validated`.
8. **Launch Checklist** — cross-functional table
   `Area | Question to answer | Owner | Status`, with one (or more) row for each of: Support,
   Growth & Data, Marketing, Enterprise, Platform, Security & Privacy. Don't drop an area even
   if it doesn't apply — mark it `N/A` with the reason, so there's a record it was considered.

## Editing an existing PRD

**Read the whole document first**, then work out which of two situations you're in — they
pull in opposite directions, and getting this wrong is the main way an edit goes bad:

### Case A — the document is already in this format: patch it, don't rewrite it

1. Identify which blocks and sections already exist, and which rows the tables (Goals,
   Launch Checklist, etc.) already have, so you don't duplicate or renumber what's there.
2. **Fit the change into the existing structure**: a new feature goes under "Key Features"
   with its priority; a new flow gets added to "Key Flows" without touching the others; a
   decision that gets resolved is updated in the "Open Issues" table by moving its status to
   resolved rather than deleting the row (so there's a trail of what was debated); a milestone
   or checklist row is updated in place.
3. **Keep the tone and level of detail of the rest of the document** — follow its existing
   conventions (e.g. how it marks pending items) instead of imposing your own.
4. Leave everything the user didn't ask about exactly as it was.

### Case B — the document is in a different or older format and they want it migrated

Signals you're here: the document has its own unrelated section layout, or the user says
something like "pass it to our format", "update this old PRD", or "bring this in line before
I hand it off". Here, following the original's conventions would defeat the purpose — the
point is to impose this structure on content that doesn't have it yet.

1. **Restructure into the three blocks**, building all 8 sections.
2. **Map the original's real content across** rather than paraphrasing it away. Look
   especially for things the old format buried: a metric sitting inside a paragraph belongs in
   the Goals & Success table; an item flagged "if there's time" or "nice to have" belongs in
   the deferred bucket, not alongside committed features; anything the original listed as a
   doubt or open question belongs in Open Issues, still open.
3. **Don't fill the new sections just because they're now empty.** A migrated document will
   have real gaps — the old format never asked for milestones, owners, or a launch checklist.
   Mark those `[PENDING: ...]`; don't infer a team, a date, or an owner that the original
   never stated. A migration that invents metadata is worse than the document it replaced,
   because the invented parts look as sourced as the real ones.
4. **Say where it came from.** A short migration note at the top — which document this came
   from, and what was added that wasn't in it — lets a reviewer tell your work from the
   original author's.

In both cases: save the edited file, and if the original was `.docx`, apply the same change
there too using the `docx` skill.

## Tone, language, and writing

- Write in whatever language the user uses in chat — don't default to English or Spanish;
  follow what they use in their message (and if they attach a doc in another language,
  respect that doc's language unless told otherwise).
- Be concrete and actionable: every row in "Key Features" and "Key Flows" should be
  understandable without re-reading the rest of the document.
- Don't invent numbers or dates — use `[PENDING: ...]` if the user hasn't given them.
- Keep tables in standard Markdown format (`| column | column |`).
- "High-Level Approach" should not turn into a technical spec — if the user starts detailing
  architecture or implementation, acknowledge the detail but summarize the general direction
  here and suggest the technical detail live elsewhere (an engineering issue, a tech doc) so
  the block's level of abstraction doesn't break.

## Generating the file

1. Write the document in Markdown (`.md`) using `assets/template.md` as a starting point,
   replacing each placeholder with real content (or `[PENDING: ...]` if information is
   missing).
2. Save the file to the user's output folder.
3. If the user explicitly asks for a Word version, use the `docx` skill to convert the
   content to `.docx`, preserving headings, tables, and bold — build on the Markdown already
   generated instead of reconstructing the structure from scratch.
4. Share the final file with the user (don't just show the text in chat).
