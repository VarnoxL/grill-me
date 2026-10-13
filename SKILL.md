---
name: grill-me
description: |
  Relentlessly interviews the user about a plan or design, one question at a
  time, until every open decision is resolved and both sides share the same
  understanding. Use whenever the user explicitly says "grill me," asks to
  stress-test a plan, wants to be grilled on a design, or wants a plan
  pressure-tested before building it.
  Also use this skill on yourself, proactively, any time you are about to make
  an assumption about a design or implementation choice instead of asking —
  ambiguous requirements, an unstated architecture decision, a fork in the
  design with no clearly-correct answer, or general confusion about what the
  user actually wants. Don't silently guess and move on: invoke this skill's
  procedure instead. This applies even mid-task, not just at the start of
  planning.
allowed-tools:
  - AskUserQuestion
  - Read
  - Grep
  - Glob
  - Bash
---

# Grill Me

Interview the user until the plan has no unresolved branches left — not
until the first few questions feel answered.

## Procedure

1. **Map the decision tree first.** Before asking anything, read the plan
   or design and list every open decision and the dependencies between
   them (which answers unlock or change which other questions). Don't
   start interviewing from a half-formed list.

2. **Check the codebase before checking with the user.** For each open
   decision, ask: can this be answered by reading the code instead of
   asking? (existing conventions, naming, config, prior art for the same
   pattern elsewhere in the repo). Use Read/Grep/Glob/Bash to resolve what
   the codebase already answers. Only decisions the codebase can't settle
   go to the user.

3. **Ask one question at a time.** Never batch questions. Use
   AskUserQuestion for a single decision, with your recommended answer as
   the first option, clearly marked "(Recommended)", and your reasoning in
   its description. Offer the realistic alternatives alongside it.

4. **Never assume.** If a decision matters to the design and isn't settled
   by the codebase, ask — don't pick a default silently and move on. A
   recommendation is not a substitute for an answer; it's a starting point
   the user can accept or override.

5. **Update the tree after every answer.** Each answer may resolve
   dependent branches automatically (no need to re-ask something the
   answer already settles) or open up new branches that weren't visible
   before. Re-evaluate what's left before asking the next question.

6. **Don't stop early.** Keep walking the tree until every branch is
   resolved — not until the conversation feels like it's covered the
   obvious ground. If you reach the end of your list and realize the
   answers imply new open questions, keep going.

7. **Close with a shared summary.** Once every branch is resolved, restate
   the final decisions as a short list so the user can confirm you both
   landed in the same place before anything gets built.

## When invoked on yourself mid-task

The same procedure applies even when there's no explicit "grill me" — if
you notice you're about to fill a gap with an assumption, stop and run
steps 1-4 on that specific decision before proceeding. This doesn't
require restarting a whole interview; it means treating that one decision
with the same rigor: check the codebase first, then ask one targeted
question with your recommendation rather than guessing.
