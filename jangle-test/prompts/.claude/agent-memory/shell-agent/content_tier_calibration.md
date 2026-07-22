---
name: content-tier-calibration
description: Tier calibration decisions from Grant -- Spicy and Degen were both too soft; these notes define where the real bars sit
metadata:
  type: feedback
---

Grant's ruling (2026-06-13): the existing Spicy and Degen pool entries were not calibrated high enough. Both tiers needed substantial upward movement.

**Spicy bar:** Must be overtly sexual or intimacy-focused, not just "warm romantic." A sync entry like "a romantic first-date spot" is Party, not Spicy. The test: would the prompt make players visibly react with a knowing laugh or raised eyebrow specifically because it is about sex/desire? If not, it is probably still Party.

**Degen bar:** Must be genuinely chaotic, not just party-culture-adjacent. A coop task like "name unwritten rules of a house party" is Party. Degen means the story went sideways -- the consequence happened, the decision was bad, the memory is fuzzy. The framing should feel like a dare to be honest, not an invitation to describe abstract party behavior.

**Party bar (the floor):** Embarrassing but not humiliating. Adult but not explicitly sexual. Minor rule-breaking and social awkwardness. Think: coworkers-who-are-friends at a birthday. NOT sanitized; definitely adult.

**Key distinction (from voice_principles T1):** Spicy = sexual. Degen = non-sexual debauchery. Content that is both (blackout hookup) gets ["Spicy", "Degen"].

**Tier principles docs created:** `PreGame Docs/Documentation/Prompt Architecture/` -- party_principles.md, spicy_principles.md, degen_principles.md. These are the authoritative reference for all future tier-gated content decisions.

**Why:** Pool-agent and shell-agent were both under-calibrating tiers because no explicit bar existed. These docs set the bar for future content authoring.

**How to apply:** Before tagging any pool entry as Spicy or Degen, reference the relevant principles doc. The "too tame" examples in each doc are the most useful calibration anchors.
