---
name: mlt-pool-build
description: Architecture decisions and grammar patterns for the most_likely_to_traits pool build (voting migration part 1)
metadata:
  type: project
---

# MLT Pool Build — Architecture and Grammar Notes

## Pool structure
- Composite: `most_likely_to_traits` (no tags, no entries, subpools only)
- Leaves: `most_likely_to_traits_party` ["Party"], `most_likely_to_traits_spicy` ["Spicy"], `most_likely_to_traits_degen` ["Degen"], `most_likely_to_traits_spicy_degen` ["Spicy","Degen"]
- Location: `pools/shared/` — cross-category per M0

## NHIE precedent for spicy_degen leaf
Mirrors how nhie handled it (nhie uses nhie_party/nhie_silly/nhie_spicy/nhie_degen — no spicy_degen leaf there). MLT diverges: voting source had ~51 prompts tagged both Spicy+Degen, enough mass for its own leaf pool.

## Grammar discipline for MLT entries
Shell renders: "...who's most likely to [entry]?"
- All entries must be infinitive phrases (to ___): "drunk text their ex", "join a cult", "have lied about their body count"
- Past-tense "have [done X]" form is valid: "have tried anal", "have gotten caught having sex"
- Present/future form also valid: "join the mile high club", "get married in Vegas drunk"
- AVOID "have the most/worst/best X" — creates double-superlative: "most likely to have the most embarrassing X"
  - Fix: rephrase to drop the superlative: "have a search history they'd never show anyone"
- AVOID em-dashes in any entry (voice_principles.md V9)
- AVOID trailing punctuation on entries

## Pool structure: most_likely_positive (added voting valence restructure)
- Composite: `most_likely_positive` (no tags, no entries, subpools only)
- Leaves: `most_likely_positive_party` ["Party"], `most_likely_positive_spicy` ["Spicy"], `most_likely_positive_degen` ["Degen"]
- Location: `pools/shared/` (parallel to most_likely_to_traits)
- most_likely_to_traits is now the NEGATIVE pool; most_likely_positive is the POSITIVE pool
- Entry counts post-restructure: most_likely_positive_party 23, most_likely_positive_spicy 13, most_likely_positive_degen 13 = 49 total
- most_likely_to_traits_party was 73 entries; reduced by 2 ("become a millionaire", "become famous" moved → de-duped to authored variants in most_likely_positive_party), now 71 entries

## Source exclusion rules (voting_prompts.json)
These prompt types were NOT extracted into mlt traits:
1. "Who would survive/win/be best at [scenario]?" — hypothetical performance, not observable trait
2. "Who has the best [physical feature]?" — superlative physical characteristic, not a behavior
3. "[Player A] or [Player B]?" — direct duel format
4. "[Player A], rate yourself..." — self-rating prompt (part 2)
5. "Who would be the [superlative role]?" — scenario-role hypotheticals

## Accusation-form normalization applied
Source prompts like "Point at someone who's definitely [past tense]" or "Point at someone who's probably [adjective]" were normalized to infinitive form:
- "Point at someone who's definitely faked an orgasm" → "have faked an orgasm"
- "Point at someone who's probably into bondage" → "be into bondage"
- "Point at someone who's probably the kinkiest" → context-specific phrasing
~67 accusation-form entries normalized this way.

**Why:** The pool agent's instruction was "How to apply: accusation_form → NORMALIZE to infinitive so it reads after 'most likely to ___'."
