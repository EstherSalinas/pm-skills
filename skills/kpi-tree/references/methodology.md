# KPI Tree — methodology reference

Read this when you want the full treatment: a worked example, the MECE deep-dive, the advanced visual
conventions, the maintenance playbook, and further reading. The core mechanics live in `SKILL.md`;
this file is the "why" and the "how, in more depth".

## Table of contents

1. Worked example (building a tree from scratch)
2. The two ways to grow a branch
3. MECE deep-dive
4. Advanced: colour-coding and line weight
5. Maintenance playbook
6. Pitfalls
7. Further reading

---

## 1. Worked example (building a tree from scratch)

A head of product at a news app wants to grow a younger audience. The team already has a dashboard,
but it's a mess: they track nearly every event with no deliberate KPIs. They call a meeting with
product, marketing, and business intelligence to build a tree.

- **First instinct was wrong.** They'd been optimising *new users*. In discussion they realised the
  real goal was **Monthly Active Users (MAU)**. MAU goes to the top; new users becomes one input.
- **Top decomposition (math):** `MAU = new users + returning users + reactivated users`. When stuck,
  write the parent as an equation and ask what sums or multiplies into it.
- **New users (math, from marketing):** `New users = leads × conversion rate`, and
  `leads = paid leads + organic leads`. Marketing supplied these — outside input is what unlocks the
  equations.
- **Returning users (hypothesis):** retention wouldn't reduce to an equation. The team did user
  research (interviews, a journey map, activation-moment analysis) and proposed driver hypotheses,
  drawn with dotted lines because the relationships are unproven.
- They declared the first iteration "good enough to use" — not complete, just useful. The tree then
  becomes the shared reference that forces cross-team conversations onto the same terms and lets the
  dashboard be pruned to what's actually in the tree.

Lessons: the top metric is often not your first guess; include other teams; a tree is allowed to be
incomplete; growth comes via equations *or* hypotheses.

## 2. The two ways to grow a branch

- **Mathematical relationships.** Funnels, segmentations, and business-case formulas are all
  equations. Put the operator on the connection (`+`, `×`). These are reliable and should be solid
  lines. Pirate Metrics (AARRR) is a familiar funnel-as-equation example.
- **Hypotheses.** "We think X drives Y." Draw dotted. Over time you either validate (promote to solid)
  or replace. Sources for good hypotheses: user interviews, customer-journey maps, product-usage data
  to find activation/"aha" moments.

Mastering both — spotting where an equation exists, and being honest where only a hypothesis does — is
the whole craft.

## 3. MECE deep-dive

MECE (Mutually Exclusive, Collectively Exhaustive) comes from Barbara Minto at McKinsey and underlies
the Minto Pyramid Principle. For a KPI tree it is the test that each parent's children form a clean
breakdown.

- **Mutually Exclusive:** the children don't overlap; nothing is counted twice. Good partition:
  people by year of birth. Bad partition: people by nationality — dual nationals are counted twice
  (not ME) and stateless people are missed (not CE). In a tree, an ME violation usually means two
  branches both claim the same conversions/revenue — fatal under last-click attribution.
- **Collectively Exhaustive:** the children cover the whole parent. If the pieces don't add up to the
  parent, something is missing. The pragmatic fix is an explicit **"other / residual"** child so the
  level closes honestly.

### Formal grounding (and why it matters for the math)

The two halves have precise definitions in probability/logic, and they translate directly into when a
branch is allowed to *add up*:

- **Mutually exclusive = disjoint:** two events can't both occur; `P(A ∩ B) = 0`. The consequence is
  the addition rule: **`P(A ∪ B) = P(A) + P(B)` only when A and B are mutually exclusive.** If they
  overlap, the real formula is `P(A ∪ B) = P(A) + P(B) − P(A ∩ B)`. This is the exact reason a
  `parent = a + b + c` branch is only valid when the children don't overlap — otherwise the sum
  double-counts the intersection and the parent is overstated. So before you write a "+" on a
  connection, confirm the children are disjoint; if they aren't, either redefine them to be disjoint
  or subtract the overlap.
- **Collectively exhaustive = the union is the whole:** at least one child must occur; the children's
  union covers the entire parent (the "sample space"), so `P(at least one) = 1`. If the children don't
  cover the parent, the missing mass is a gap — add a residual child so the level sums to 100% of the
  parent.
- **MECE = a partition:** mutually exclusive *and* collectively exhaustive together. Canonical
  intuition from a six-sided die: `{1,2,3,4,5,6}` is MECE (a clean partition); `{even, odd}` is MECE;
  `{1, 6}` is ME but **not** CE (misses 2,3,4,5); `{even, not-6}` is CE but **not** ME (4 is in both).
  Use these four shapes as a checklist when auditing a level: which failure mode am I looking at —
  overlap (not ME), gap (not CE), both, or clean?

A useful tell from statistics: if you'd model the children as category dummies (e.g. age <18 / 18–64 /
65+), a correct MECE split means every observation lands in exactly one bucket — never zero (gap) and
never two (overlap). If you can't assign each unit to exactly one child, the level isn't MECE yet.

Practical notes:
- For **math** branches, demand a true partition — exact, no slop. If `parent = a + b + c` doesn't
  actually hold in the data, the branch is wrong.
- For **hypothesis** branches, treat MECE as a goal, not a guarantee; flag suspected overlaps/gaps
  rather than forcing artificial cleanliness. Over-forcing mutual exclusivity can be limiting, and
  occasional deliberate redundancy is acceptable as long as it's labelled and not double-counted in
  totals.
- MECE catches *gaps and overlaps* but not *superfluous* metrics — separately prune children that are
  technically valid but not worth tracking.

## 4. Advanced: colour-coding and line weight

Once the basic tree works, encode more information visually.

**Colour = data confidence of a metric.** Pick a simple scale, e.g.:
- trusted and self-serve (look it up on a dashboard any time),
- verified but manual (reliable, but someone has to pull it),
- not tracked / not available,
- unverified or unreliable.

This converts the tree into an instrumentation backlog: the weak-confidence metrics are your
tracking to-do list.

**Line weight = emphasis.**
- Box-outline thickness → which metrics are "next to be worked on" (e.g. needs tracking, or needs to
  move from manual to self-serve).
- Arrow thickness → strength of the relationship (thicker = contributes more to the parent).

In a markdown/text rendering you can't draw thickness, so substitute notation: a confidence column in
the metric table (✅ / 🟡 / ⚪), and a "focus" or "weight" tag on connections.

## 5. Maintenance playbook

A tree is a living document, not a one-off.

- **Review triggers:** strategy changes; goals/objectives change; a bigger discovery or revelation;
  you find something in the tree is wrong (especially a hypothesis that didn't hold).
- **Standing cadence:** revisit at least once a quarter even if nothing above fired.
- **Review method:** same as building — find a place to start, then walk the branches and relationships
  section by section. Promote validated hypotheses to solid; demote or replace broken ones.
- **Socialise drafts early** and keep asking other teams for feedback — that's where missing equations
  and drivers surface.

## 6. Pitfalls

- **Not asking for feedback** — solo trees miss cross-team knowledge.
- **Not flagging hypotheses** — unproven links drawn as facts mislead everyone.
- **Too big** — only detail branches in focus; hide or collapse the rest. Consider a top-level tree
  plus per-branch drill-downs instead of one giant diagram.
- **Revenue at the top** — keep a lagging financial figure as something watched, with a customer-centric
  North Star as the metric you actually steer.

## 7. Further reading

- Petra Wille & Shaun Russell — "KPI Trees" (source of this method).
- Barbara Minto — the Minto Pyramid Principle (origin of MECE).
- "The Definitive Guide to Issue Trees" (craftingcases.com) — the broader issue-tree technique.
- AARRR / Pirate Metrics — funnels as equations.
- Amplitude — "How to find your North Star".
- Leading vs. lagging indicators — why the top is customer behaviour, not the financial outcome.
