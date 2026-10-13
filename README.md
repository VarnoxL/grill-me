# grill-me

A Claude Code skill that relentlessly interviews you about a plan or design,
one question at a time, until every open decision is resolved and you both
share the same understanding.

- Walks the whole decision tree, not just the first few questions.
- Checks the codebase for an answer before asking you.
- Every question comes with a recommended answer.
- Never assumes — asks instead of guessing.
- Doubles as an ambient trigger: Claude is meant to invoke it on itself
  whenever it's about to make an unstated design assumption, not just when
  you type "grill me."

## Install

Clone (or copy `SKILL.md`) into your personal skills directory:

```
git clone https://github.com/VarnoxL/grill-me.git ~/.claude/skills/grill-me
```

Or drop `SKILL.md` into any existing `~/.claude/skills/grill-me/` folder.

## Use

Say "grill me," "stress-test this plan," or similar once you have a plan or
design you want pressure-tested. Claude will also reach for it on its own
when it hits an ambiguous design decision instead of guessing.
