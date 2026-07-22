---
name: feedback-voice-decisions
description: Grant-adjudicated voice and phrasing decisions per category, plus recurring patterns
metadata:
  type: feedback
---

## Confessions category

**Refusal clause variety is intentional.** Shells in this category use different refusal verbs on purpose:
- "Refuse and take" — confess.v1
- "Stay quiet and take" — tell_group.v1 (Grant specified this exact phrasing in 2026-06-07 variety pass)
- "Confess or take" — question.v1, have_you_ever.v1
- "No story and take" — spill.v1 (matches describe.v1 "No answer and take" pattern — imperative negation)

**Why:** Grant explicitly requested variety in refusal clauses across shells in the 2026-06-07 pass. Don't normalize them back to a single verb.

**How to apply:** When adding new confessions shells, check the existing refusal clauses and pick one that isn't already used, or propose a new one. Don't default to "Refuse and take" just because it's first.

---

## confession_prompts pool — person-referent entries

A minority of cp_party entries are person-referent ("the last person you talked trash about behind your back"). These read awkwardly after "what's" in confessions.question.v1. Grant accepted this trade-off — "what's" works cleanly for 90%+ of entries. Do not redesign the question shell to accommodate the minority.

**How to apply:** If adding new confession_prompts entries, prefer "[superlative] [thing]" or "a [thing]" shapes over "the [person] you..." shapes, to keep question.v1 rendering clean.

---

## General refusal-clause patterns (penalty verb rule)

Verbs (take, give, share, split) must always appear in shell text near [Penalty, X] — the token never stands alone. Patterns observed in confessions:
- "[action]. [Negative condition] and take [Penalty, 2-3]." — imperative-then-consequence
- "[action] or take [Penalty, 2-3]." — alternative framing
- "[action]? [Verb] or take [Penalty, 2-3]." — question-delivery
