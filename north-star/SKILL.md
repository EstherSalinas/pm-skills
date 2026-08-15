---
name: north-star
description: >-
  Choose, define, or pressure-test a product's North Star Metric — the single metric that best
  captures the value customers get from a product and leads (doesn't lag) sustainable business
  results. Use this BEFORE building a KPI tree (see the kpi-tree skill) whenever the top-level
  metric isn't already settled, whenever the user asks "what should our North Star be," "what's
  our top metric," "métrica estrella," "qué debería ser mi métrica principal," or wants to
  validate/replace an existing North Star. Also trigger when someone shares a strategy doc,
  vision statement, OKRs, or positioning notes and asks what metric should guide decisions —
  even if they never say "North Star." Applies just as much to a content strategy, a solo
  project, or a team as to a software product — consult this skill any time a top-level metric
  is being picked, not only for classic SaaS use cases.
---

# North Star Metric

A North Star Metric is the single metric that best captures the value customers derive from a
product — a leading indicator of sustainable business results, not a description of what
already happened. Its job is to give everyone one thing to watch that ties day-to-day work to
strategy, so decisions stop being argued case-by-case. This skill picks one, defines it
precisely, and pressure-tests it before anything gets built on top of it (like a
[[kpi-tree]] below it).

Method credit: Amplitude's "The North Star Playbook" (John Cutler, Ted Clark, Abbie
Kouzmanoff, Ibrahim Bashir). The mechanics below are the reusable core.

## Step 0 — context first, always (non-negotiable)

Never propose a North Star candidate before you have the strategic context to judge it
against. A metric that "sounds right" in isolation is exactly how teams end up chasing the
wrong number for a quarter. Before generating a single candidate:

1. **Find or build the strategy/vision context.** Look for an existing strategy doc, vision
   statement, positioning notes, or goals document (ask the user, or check the project for
   one). If nothing exists, build a lightweight vision statement first using Geoffrey Moore's
   template: *"For [target customer] who [need], the [product] is a [category] that [key
   benefit]. Unlike [competitive alternative], it [differentiation]."* Don't skip this by
   improvising a plausible-sounding vision — a real document the user actually wrote counts for
   more than whatever you infer from the product's name.
2. **Identify the "game" being played.** This one framing question routinely changes which
   candidates even make sense: is the user absorbed in the product for its own sake
   (**attention game** — more time/use signals more satisfaction), looking to complete the
   right transaction (**transaction game**), or using the product because they have a job to
   do (**productivity game**)? Name it explicitly and say why it's the right frame.
3. **Surface beliefs.** Name 2-3 assumptions the user is carrying about what customers value,
   why people convert or churn, or where the competition is heading. Unstated beliefs are the
   most common reason candidates get compared unfairly — get them on the table before scoring
   anything.

Only once you have this should you move to generating and judging candidates. If the user
pushes to skip straight to "just pick one," it's fine to move faster, but say out loud what
you're assuming instead of silently inventing context.

## The one thing to hold onto

**A North Star Metric is an outcome, not a lever.** Inputs are the variables a team can move
directly; the North Star is the dependent variable that responds to them. John Cutler's test:
*"If you can move your North Star directly, it's probably not a good North Star — the goal is
for it to be one level out of reach, so people ask why it's going up or down."* If a candidate
is something you could just... do (send more emails, ship more features), it's an input, not
a North Star.

## Workflow

1. **Do Step 0 above.** Not optional.
2. **Write the North Star statement, qualitatively, before naming any metric.** Fill in:
   *"Our path to sustainable growth is a function of our ability to: ___."* Keep it in plain
   language — no numbers yet. If this won't fill in cleanly, that's a signal to revisit the
   vision/beliefs, not to force a metric. (Full statement exercise — inputs, opportunities,
   interventions — in `references/playbook.md`.)
3. **Generate 2-4 real candidates**, not one. Include at least one you expect to reject — the
   rejected candidates and *why* they lost are as informative as the winner, and belong in the
   final output.
4. **Score every candidate against the 7-question checklist** (below), not just the one you
   like. State the verdict per question per candidate — don't only justify the winner in prose.
5. **Define the winner precisely**: *"Our North Star Metric is called X, which we define as
   Y."* Vague: "subscribers who share our content." Specific: "Frequent Content Sharers (FCS):
   unique subscribers who share an average of 2+ articles per week over the trailing 12
   weeks." Give it a name worth repeating, not just a formula.
6. **Define 3-6 inputs** — things the team can actually act on that combine to move the North
   Star. Use: *"I believe [North Star] is a function of [X, Y, Z]. I believe there's some
   independence between them (movement in one isn't immediately felt in the others)."* Push
   back if an input is really the North Star restated, or if two inputs are the same lever
   twice.
7. **Pressure-test before finalizing** (see checklist + Common pitfalls below). Don't skip
   this because the metric "feels obviously right" — that feeling is exactly what got vanity
   metrics chosen historically.
8. **State the confidence and the revisit trigger.** A first-pass North Star is a hypothesis,
   not a verdict — say so, and name what would make you revisit it (strategy shift, the metric
   stops directionally tracking outcomes, a bigger discovery).

Treat the whole thing as iterative, not linear — it's normal and healthy to go back and forth
between the statement, the metric, and the inputs a few times before it holds together.
(`references/playbook.md` has the "cycle of doubt" pattern if the user seems stuck redoing the
same loop, plus troubleshooting for teams — surfacing beliefs, connecting to a vision
statement, key value exchanges — for when convergence is genuinely hard.)

## The 7-question checklist

Score every candidate, not just the favorite:

1. **Expresses customer value?** "Daily Active Users" and "Registered Users" fail this — they
   say nothing about what the customer got out of it.
2. **Represents the vision/strategy?** Someone should be able to read it and infer the
   product's strategy at a glance.
3. **Leading, not lagging?** MRR and ARPU tell you what already happened. Find the behavior
   that *predicts* the lagging outcome instead (e.g. not "renewal revenue" but the usage
   pattern that correlates with renewing).
4. **Actionable?** The team should believe they can move it. A broad market trend that would
   be true whether or not the product existed is not a North Star.
5. **Understandable to non-technical people?** Explain it to someone who knows the business
   but not the internals — if they don't get it fast, simplify.
6. **Measurable?** But don't reject a strong idea just because it isn't measured *today* —
   light instrumentation often closes the gap. Don't let this criterion do the deciding too
   early either.
7. **Not a vanity metric?** Watch for DAU, ad impressions, download counts, page views,
   registered users, story points, time on page. Case in point: a delivery app almost picked
   "People Opening the App" — real research showed what customers actually valued was
   incident-free delivery, so "Happy Deliveries" became the North Star instead, because that's
   what actually correlated with retention and lifetime value.

## Common pitfalls (watch for these actively)

- **Jumping to "can we measure that?" too soon.** Kills good candidates before they're
  evaluated on merit. If you know almost nothing yet, almost any data point reduces
  uncertainty significantly — you don't need a perfect model to start.
- **Fixating on the North Star and ignoring inputs.** By design the North Star isn't directly
  actionable — the inputs are. If a conversation only talks about the top metric, pull it back
  to inputs.
- **Insisting on more than one North Star.** Almost always avoidable — look for the real
  shared boundary (do customers actually experience these as separate products, or as one
  relationship?). Multiple North Stars for one product/team just re-imports the prioritization
  fights the framework exists to resolve.
- **Choosing revenue, or any lagging financial figure, as the top.** Watch it, don't chase it
  directly — the North Star is the thing you steer that predicts it.
- **Letting current dysfunction block progress.** "Start where you are" (name the
  imperfections, don't let them stop you) beats waiting for a clean slate. "Start small" —
  scope the first North Star to a piece you can actually influence.
- **Chasing a perfect threshold.** A reasonable, imperfectly-measured North Star beats a
  perfectly-measured weak one. State the uncertainty and move on.

## Output format

Default to a markdown document, matching the user's language:

```
# North Star Metric — [product/team/goal]

## Starting context
[Strategy/vision consulted or built, and the "game" identified, with why.]

## Beliefs surfaced
[2-4 assumptions on the table before scoring candidates.]

## North Star statement
[The qualitative exercise: North Star → Inputs → Opportunities → Interventions.]

## Candidates considered
[Each candidate + why it was kept or rejected — rejections included, not hidden.]

## Chosen North Star Metric
**Name:** X
**Definition:** Y
**Checklist result:** [pass/fail + why, per question, for this candidate]

## Inputs
[3-6, each named + defined + why believed independent.]

## What this doesn't tell us / open uncertainty
[Named honestly.]

## Revisit trigger
[What would make this worth reopening — strategy shift, metric stops tracking outcomes, etc.]
```

## Handing off

Once the North Star and inputs are set, the [[kpi-tree]] skill decomposes each input further
into a full metric tree (math relationships and hypotheses, MECE-checked). Don't re-litigate
the top metric inside that skill — this is where that decision gets made.

## When you need more

Read `references/playbook.md` for: the full statement-exercise walkthrough with fill-in
templates, the mind-mapping technique for surfacing inputs (with a worked bank example), the
"levels of bets" model for connecting the North Star to a roadmap, input-testing techniques
(greenfield test, roadmap check), when/how to change an established North Star, and
OKR/roadmap/prioritization integration tips.
