# pm-skills

A [Claude Code](https://claude.com/claude-code) plugin marketplace for product management
work — real methodologies packaged so Claude follows them consistently, instead of relying on
me remembering to ask for the rigor every time.

## Plugins

- **[`pm-metrics`](pm-metrics/)** — define a product's North Star Metric and decompose it
  into a full KPI tree:
  - **`north-star`** — choose, define, and pressure-test a product's North Star Metric before
    building anything on top of it. Based on "The North Star Playbook" by Amplitude (John
    Cutler, Ted Clark, Abbie Kouzmanoff, Ibrahim Bashir). Validated with evals in
    [`pm-metrics/skills/north-star/evals/`](pm-metrics/skills/north-star/evals/evals.json) —
    100% pass rate across 3 test cases vs. a baseline without the skill (77% average, with
    much higher variance: skips the vision statement, doesn't define inputs, doesn't set a
    revisit trigger).
  - **`kpi-tree`** — builds a KPI tree (metric tree) from a North Star or goal down to the
    inputs that drive it, with a MECE check at every level. Based on the method by Petra Wille
    & Shaun Russell.

  The two are meant to be used in sequence: `north-star` decides the top, `kpi-tree`
  decomposes what's underneath it — bundled as one plugin because one isn't very useful
  without the other.

- **[`pm-docs`](pm-docs/)** — structured product documentation, starting with PRDs:
  - **`create-prd`** — write or edit a single-feature PRD in the format Figma made public for
    its own teams: Problem Alignment, Solution Alignment, Launch Readiness, including a
    cross-functional Launch Checklist (Support, Growth & Data, Marketing, Enterprise,
    Platform, Security & Privacy). Validated with evals in
    [`pm-docs/skills/create-prd/evals/`](pm-docs/skills/create-prd/evals/evals.json) — 100%
    pass rate across 3 test cases vs. a baseline without the skill (82% average: a baseline
    PRD reads fine, but never reproduces the three-block structure or the launch checklist on
    its own).

  More documentation formats (specs, roadmap docs) may join this plugin later — it's grouped
  by "structured product docs," not by this one template.

## Installation

### Claude Cowork (recommended for non-developers)

1. Open **Customize** (bottom-left)
2. Go to **Browse plugins → Personal → +**
3. Select **Add marketplace from GitHub**
4. Enter: `EstherSalinas/pm-skills`
5. Install `pm-metrics` and/or `pm-docs` from the list

### Claude Code (CLI)

From inside a Claude Code session:

```
/plugin marketplace add EstherSalinas/pm-skills
/plugin install pm-metrics@pm-skills
/plugin install pm-docs@pm-skills
```

Once installed, the skills trigger automatically when the conversation matches their
description, or you can invoke them explicitly: `/pm-metrics:north-star`,
`/pm-metrics:kpi-tree`, `/pm-docs:create-prd`.

## Why this exists

I write about AI applied to product management. These skills came out of needing them for my
own work (defining KPIs for my newsletter) and catching myself building a KPI tree without
having questioned the North Star first — the exact failure `north-star` exists to prevent.
