---
name: commands-pool-patterns
description: Grammar patterns, entry shapes, and routing rules for the commands pool family (judgment_clauses, filter_conditions, speed_actions, group_triggers, wyd_actions, duo_punchlines, split_flavors, chain_framings, proxy_framings).
metadata:
  type: project
---

# Commands Pool Grammar Patterns

## judgment_clauses (jc_*)

Shell context: "[Player A], give [Penalty, N] to whoever you think [jc_entry]."

Entry shape: present-tense predicate that completes "whoever you think ___"
- Third-person present tense: "has the worst taste in music", "would be the worst roommate"
- "would" + verb phrase for hypothetical judgments: "would bail on you at the worst possible moment"
- "you'd" contraction is fine: "you'd least want to be stuck in an elevator with"
- EXCLUDE "is most likely to [X]" form — those belong in mlt_* not jc_*

Tags: judgment_clauses_party [Party], judgment_clauses_degen [Party, Degen], judgment_clauses_spicy [Spicy, Party]

## filter_conditions (fc_*)

Shell context: "Whoever [fc_entry] takes [Penalty, N]."

Entry shape: present/past state that completes "Whoever ___"
- Present state: "is wearing socks", "is the tallest person here"
- Recent-past state: "slept the latest last night", "stayed out the latest this past weekend"
- Quantity/superlative: "has the most tattoos", "has been in the most relationships"
- Do NOT include entries that have a special mechanic baked in (e.g., "share the headline", "group decides who qualifies") — extract only the bare condition

Tags: filter_conditions_silly [Silly, Party], filter_conditions_party [Party], filter_conditions_degen [Party, Degen], filter_conditions_spicy [Spicy, Party]

Spicy vs Party boundary: T1 applies — Spicy = sexual/romantic content. "Most ex-partners", "most first dates", "wearing least clothing" = Spicy. "Ended the most friendships", "sent a message to the wrong person" = Party (social drama, not sexual).

## speed_actions (sa_*)

Shell context: "The last person to [sa_entry] takes [Penalty, N]."

Entry shape: infinitive phrase that completes "last person to ___"
- Always starts with "have": "have eaten fast food", "have ordered shots for a group"
- Past action, time-ordered (who did it most recently = last)
- NOT ongoing states (those are filter_conditions)

Tags: speed_actions_party [Party], speed_actions_degen [Degen], speed_actions_silly [Silly, Party], speed_actions_spicy [Spicy]

## group_triggers (gt_*)

Shell context: "Everyone who [gt_entry] takes [Penalty, 2]."

Entry shape: present-tense relative clause that completes "Everyone who ___"
- Binary observable condition — either true right now or not: "is wearing socks", "has their phone screen facing down right now"
- Must be verifiable by looking around the room (no self-report needed)
- Present state or recent-past state: "has texted someone in this room today", "went out last weekend"
- EXCLUDE superlatives (those are filter_conditions) — group_triggers fire at ALL qualifying players, not one winner

Tags: group_triggers_silly [Silly, Party], group_triggers_party [Party], group_triggers_degen [Degen], group_triggers_spicy [Spicy]

## wyd_actions (wyd_*)

Shell context: "[Player A], pick someone. They have to [wyd_entry] or take [Penalty, max]."

Entry shape: verb phrase that completes "They have to ___"
- Third-person possessives throughout: "their", "them", "they" — NOT "your"/"you" (shell subject is "They")
- Doable actions, not hypothetical preferences — things a player can actually perform right now
- Mix of phone-based ("show the group the last photo they took"), physical ("do 10 jumping jacks"), and social ("do their best impression of someone in this room")
- No em dashes (V9)

Tags: wyd_actions_party [Party], wyd_actions_silly [Silly, Party], wyd_actions_spicy [Spicy], wyd_actions_degen [Degen]

## duo_punchlines (dp_*)

Shell context: "Bad news, [Player A] and [Player B]. You both take [Penalty, 3]. [dp_entry]"

Entry shape: **standalone full sentence** — own capitalization, own terminal punctuation
- Appended after the penalty sentence as a comedic closer
- Pure text — no nested tokens, no player references
- Tone: dry humor, resigned acceptance, cosmic injustice: "The good news? There is none.", "Fate works in mysterious ways."
- Keep short (under 10 words preferred)

Tags: duo_punchlines_party [Party], duo_punchlines_silly [Silly, Party]

## split_flavors (sf_*)

Shell context: "[Player A], give [Penalty, 2] to the person on your left and [Penalty, 2] to the person on your right. [sf_entry]"

Entry shape: **standalone full sentence** — own capitalization, own terminal punctuation
- Appended after the mechanic as a flavor closer
- Pure text — no nested tokens
- Tone: dry commentary on the unfairness of proximity: "Location is destiny.", "Collateral damage."
- Short (2-6 words typical)

Tags: split_flavors_party [Party], split_flavors_silly [Silly, Party]

## chain_framings (cf_*)

Shell context: "[Player A], point at someone. They take [Penalty, 2], then point at someone else who takes [Penalty, 1]. [cf_entry]"

Entry shape: **standalone full sentence** — own capitalization, own terminal punctuation
- Appended after the cascade mechanic as a closer
- Pure text — no nested tokens
- Tone: inevitability, chain-reaction commentary: "Pay it forward.", "Consequences travel fast."

Tags: chain_framings_party [Party]

## proxy_framings (pf_*)

Shell context: "[Player A], pick someone to take [Penalty, 4] for you. If they refuse, you take [Penalty, max]. [pf_entry]"

Entry shape: **standalone full sentence** — own capitalization, own terminal punctuation
- Appended after the refusal clause as a closer
- Pure text — no nested tokens
- Tone: trust/loyalty stakes: "Choose wisely.", "Hope they like you."

Tags: proxy_framings_party [Party]

## Cross-pool boundary: jc_* vs sq_*

Judgment_clauses and superlative_questions will overlap semantically. This is acceptable — different mechanics (one-player decides vs group votes). Keep entries in both pools. See adjudicated_boundaries.md for the full ruling.

## MLT additions from commands source

When extracting "give [Penalty] to whoever is most likely to [X]" command prompts:
- Extract X, dedup against mlt_* entries
- Skip if near-dupe exists, if A5 (scenario hypothetical), or if A6 (double-superlative)
- Tag to correct mlt_* leaf by content (party/degen/spicy)
