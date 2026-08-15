---
name: kpi-tree
description: >-
  Build, define, or review a KPI tree (a.k.a. metric tree / árbol de métricas) that connects an
  overarching goal or North Star metric down through the metrics that drive it. Use this whenever the
  user wants to structure their metrics, map KPIs to company goals, turn a messy "track everything"
  dashboard into a focused metric hierarchy, decompose a North Star into input metrics, build a tree
  from a strategy doc / metrics glossary / OKR or goals document, or sanity-check whether their tree
  is MECE (no gaps or overlaps). Trigger on phrases like "KPI tree", "metric tree", "árbol de
  métricas", "how do my metrics ladder up to the goal", "what should we actually measure", "connect
  our metrics to strategy" — and also when someone shares a metrics or strategy document and asks how
  the numbers relate, even if they never say the words "KPI tree".
---

# KPI Tree

A KPI tree shows the relationship between the metrics in a business, from one overarching goal at the
top down to every metric that influences it. Its job is **alignment, transparency, and focus**: it
lets everyone see which metric they can move to advance the goal, and how those metrics connect. This
skill builds one from whatever the user gives you (a strategy doc, a goals list, a dashboard export, a
metrics glossary, or just a conversation) and keeps it honest about what's known versus assumed.

Method credit: Petra Wille & Shaun Russell, "KPI Trees". The mechanics below are the reusable core.

## The one rule that makes a tree a tree

Every connection points **upward** and means "this metric contributes to the one above it." A tree is
only useful if those connections are real, so each one must be one of exactly two types:

1. **Mathematical relationship** — the child metrics combine into the parent by a known equation.
   Mark the operator (`+`, `×`) on the connection. Examples:
   `MAU = new users + returning users + reactivated users`,
   `New users = leads × conversion rate`.
   These are airtight: funnels, segmentations, and business-case formulas all qualify. Wherever there
   is an equation, there is a valid branch.

2. **Hypothesis** — you *believe* the child drives the parent but haven't proven the link (e.g. "users
   who finish onboarding are more likely to return"). These are real and belong in the tree, but they
   must be visibly flagged as unproven (dotted line / "[hypothesis]" tag) so nobody treats a guess as
   a fact. Hypotheses get validated (then promoted to solid) or replaced as you learn.

If you can't say which of the two a connection is, that's a signal the branch isn't ready — say so
rather than drawing a confident line.

## Workflow

Build the tree in this order. Narrate your reasoning briefly as you go so the user can correct course.

1. **Find the top.** Pick the single overarching goal. Prefer a customer-centric North Star (a leading
   indicator of value delivered) over a pure revenue/financial figure — revenue is something you
   *watch*, not the customer behaviour you *drive*. If the top metric isn't already settled, use the
   `north-star` skill first — it interrogates strategy/vision, surfaces beliefs, generates and scores
   multiple candidates, and pressure-tests the winner before anything gets decomposed under it. Don't
   assert a top metric unilaterally and build the tree on top of it; that skips the checkpoint where
   the user can correct course. One metric at the top — not three.

2. **Decompose, layer by layer.** From each metric, ask "what combines or contributes to this?" Use a
   math equation when one exists; use a labelled hypothesis when it doesn't. Keep going down only
   where detail is useful (see step 4).

3. **Check MECE at every level.** This is non-negotiable, not a nicety — a tree that isn't MECE
   silently lies about the business. For each parent, test its children on both halves
   (MECE = Mutually Exclusive, Collectively Exhaustive; Barbara Minto / McKinsey):
   - **Mutually Exclusive — no overlap, no double-counting.** Each child captures a distinct slice;
     no two children count the same thing. This matters most under last-click attribution, where one
     euro must land in exactly one bucket. The classic non-MECE trap is overlapping categories (like
     classifying people by nationality — dual nationals get counted twice). Concrete test before you
     put a "+" on a connection: you may only write `parent = a + b + c` when the children are disjoint,
     because `P(A∪B) = P(A) + P(B)` holds *only* when they don't overlap (otherwise you must subtract
     the overlap). If you can't assign each unit to exactly one child, the "+" is wrong.
   - **Collectively Exhaustive — no gaps.** The children together account for the *whole* parent. If
     they don't sum (for a math relationship) or plausibly cover (for hypotheses) the parent, a driver
     is missing. A common fix is an explicit "other / residual" bucket so the level still closes.
   For math branches, MECE is exact: the children must be a true partition of the parent (they add or
   multiply up with nothing left over and nothing counted twice). For hypothesis branches, aim for
   MECE but accept it's approximate — flag where overlaps or gaps are suspected. State plainly for each
   parent whether it's clean, or name the specific overlap/gap; never paper over it.

4. **Resist over-growth.** Don't expand branches that aren't a current focus — name them and leave
   them shallow (e.g. "reactivated users — not a focus this quarter, not broken down"). A tree that
   tries to be complete becomes unreadable. A top-level tree plus drill-downs per branch beats one
   giant tree.

5. **Annotate confidence.** For each metric note whether it's trusted and self-serve, verified but
   manual, or not tracked / unreliable. This turns the tree into an instrumentation to-do list, not
   just a diagram. (See `references/methodology.md` for the colour/line-weight conventions.)

6. **Flag what to validate and when to revisit.** List the open hypotheses to test, and note the
   review triggers: strategy change, goal change, a big discovery, finding something wrong, or a
   standing quarterly checkpoint.

A tree is never "done" — it grows as you learn. Treat the first pass as a draft to socialise with
other teams (marketing, data/BI, etc.), because their input is usually what unlocks the equations and
the hypotheses.

## Output format

Default to a **markdown document** (it's portable and easy to publish). Match the user's language.
Use this structure:

```
# KPI Tree — [product / team / goal]

## Top goal
[The single overarching metric, one line on why it's the right top.]

## The tree
[ASCII/indented hierarchy, root at top, children below. Mark each connection:
 "+" or "×" for math relationships, "····" or "[H]" for hypotheses.]

## Legend
solid / "+×"  = known relationship (math or verified driver)
dotted / [H]  = hypothesis, not yet verified
confidence    = ✅ trusted & self-serve · 🟡 verified, manual · ⚪ not tracked / unreliable

## Metric definitions
| Metric | Definition | Connection to parent (math / hypothesis) | Confidence | Source |

## MECE check
[Overlaps or gaps found, per parent. State "clean" if none.]

## Open hypotheses to validate
[Each dotted connection + the cheapest way to test it.]

## Maintenance
[Review triggers + cadence.]
```

Represent the tree in text like this (root at top, operators on the connections):

```
                 MAU                      ← top goal
        ┌─────────┼──────────┐
   new users  +  returning  +  reactivated
   (leads × CR)   ····> ?        (not a focus)
```

Keep dotted/`[H]` connections visually distinct from solid ones — that distinction is the single most
important thing the diagram communicates.

## Common pitfalls to avoid

- **Unmarked hypotheses.** A guess drawn as a solid line is the most dangerous output here. Always
  flag unproven links.
- **No feedback loop.** A tree built solo misses equations and drivers other teams know. Recommend the
  user socialise the draft.
- **Too big.** Detail only where it earns its place; collapse the rest.
- **Revenue as the top.** It's a lagging financial outcome, not the customer behaviour you steer; keep
  it as something watched above or beside the North Star, not the North Star itself.

## When you need more

Read `references/methodology.md` for: a full worked example (building a tree from scratch), the
advanced colour-coding and line-weight conventions, the maintenance playbook, and further reading. Load
it when the user wants a richer treatment or asks about the advanced visual conventions.
