# pm-skills

A [Claude Code](https://claude.com/claude-code) plugin marketplace for product management
work — real methodologies packaged so Claude follows them consistently, instead of relying on
me remembering to ask for the rigor every time.

## Plugins

- **[`north-star`](north-star/)** — choose, define, and pressure-test a product's North Star
  Metric before building anything on top of it. Based on "The North Star Playbook" by
  Amplitude (John Cutler, Ted Clark, Abbie Kouzmanoff, Ibrahim Bashir). Validated with evals
  in [`north-star/evals/`](north-star/evals/evals.json) — 100% pass rate across 3 test cases
  vs. a baseline without the skill (77% average, with much higher variance: skips the vision
  statement, doesn't define inputs, doesn't set a revisit trigger).

- **[`kpi-tree`](kpi-tree/)** — builds a KPI tree (metric tree) from a North Star or goal down
  to the inputs that drive it, with a MECE check at every level. Based on the method by Petra
  Wille & Shaun Russell.

The two are meant to be used in sequence: `north-star` decides the top, `kpi-tree`
decomposes what's underneath it.

## Installation

### Claude Cowork (recommended for non-developers)

1. Open **Customize** (bottom-left)
2. Go to **Browse plugins → Personal → +**
3. Select **Add marketplace from GitHub**
4. Enter: `EstherSalinas/pm-skills`
5. Install `north-star` and/or `kpi-tree` from the list

### Claude Code (CLI)

From inside a Claude Code session:

```
/plugin marketplace add EstherSalinas/pm-skills
/plugin install north-star@pm-skills
/plugin install kpi-tree@pm-skills
```

### Manual (personal skill, no plugin system)

Copy the skill folder straight into your personal skills directory:

```bash
cp -r north-star ~/.claude/skills/north-star
cp -r kpi-tree ~/.claude/skills/kpi-tree
```

Either way, skills trigger automatically when the conversation matches their description, or
you can invoke them explicitly (`/north-star:north-star`, `/kpi-tree:kpi-tree` as plugins, or
`/north-star`, `/kpi-tree` as personal skills).

## Why this exists

I write about AI applied to product management. These skills came out of needing them for my
own work (defining KPIs for my newsletter) and catching myself building a KPI tree without
having questioned the North Star first — the exact failure `north-star` exists to prevent.
