# pm-skills

[Claude Code](https://claude.com/claude-code) skills for product management work —
real methodologies packaged so Claude follows them consistently, instead of relying on me
remembering to ask for the rigor every time.

## Skills

- **[`north-star`](skills/north-star/)** — choose, define, and pressure-test a product's
  North Star Metric before building anything on top of it. Based on "The North Star Playbook"
  by Amplitude (John Cutler, Ted Clark, Abbie Kouzmanoff, Ibrahim Bashir). Validated with evals
  in [`skills/north-star/evals/`](skills/north-star/evals/evals.json) — 100% pass rate across
  3 test cases vs. a baseline without the skill (77% average, with much higher variance: skips
  the vision statement, doesn't define inputs, doesn't set a revisit trigger).

- **[`kpi-tree`](skills/kpi-tree/)** — builds a KPI tree (metric tree) from a North Star or
  goal down to the inputs that drive it, with a MECE check at every level. Based on the method
  by Petra Wille & Shaun Russell.

The two are meant to be used in sequence: `north-star` decides the top, `kpi-tree`
decomposes what's underneath it.

## Installation

Copy the skill folder you want into your Claude Code personal skills directory:

```bash
cp -r skills/north-star ~/.claude/skills/north-star
cp -r skills/kpi-tree ~/.claude/skills/kpi-tree
```

They trigger automatically when the conversation matches their description, or you can invoke
them explicitly (`/north-star`, `/kpi-tree`).

## Why this exists

I write about AI applied to product management. These skills came out of needing them for my
own work (defining KPIs for my newsletter) and catching myself building a KPI tree without
having questioned the North Star first — the exact failure `north-star` exists to prevent.
