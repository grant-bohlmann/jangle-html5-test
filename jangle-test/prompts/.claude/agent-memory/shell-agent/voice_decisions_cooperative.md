---
name: voice-decisions-cooperative
description: Grant-adjudicated voice, mechanic, and scoping decisions for the Cooperative category
metadata:
  type: feedback
---

# Cooperative category decisions

Source: Grant's 2026-06-08 prune+revise pass over the 36-shell brainstorm (cut to 18).

## Scoping / what gets cut

- **Word-Games adjacency is a kill reason.** Shells whose mechanic is "name things in a category / chain words / spell a word around the circle" got cut even when framed cooperatively (alternate_chain, group_chain, relay, build_word, **group_beat** — beat-paced category-naming, confirmed cut 2026-06-08). If a coop shell's core action is word-listing or category-naming, it belongs in Word Games. Flag it and expect it to be cut.
- **Partner-knowledge shells are reserved for a future Couples shell**, not Cooperative (guess_partner, guess_partner_both, how_well removed for this). Don't re-pitch "how well do you know your partner" mechanics here.
- Niche/redundant physical bits (group_wave, pair_pose, keep_alive) and agree-on-X shells (agree_fast, group_agree) were cut as confusing/redundant.

## Mechanic / framing rulings

- **Sabotage framing replaces "hand out penalties" for coop-vs-others shells.** Grant killed the "succeed = you hand out a penalty" reward pattern. Preferred pattern: pair attempts a task while everyone else tries to break their focus (no touching); success = **everyone else takes [Penalty]**, failure = the pair both take it. This is the `coop_sabotage.v1` template; also applied to `password.v1`.
- **Sync win bars should be achievable.** Requiring the WHOLE table to match is too hard. Group sync success = at least **two** people match. Floated-but-not-built future tweak: scale required-match count to player count.
- **"Same Wavelength" is the working name for the mind-meld converge mechanic** (pending Grant's final pick among Same Wavelength / Hive Mind / Great Minds / Same Page). The label is optional in the shell opener; mechanic reads fine without it.
- **Team sync = whole team, not a 2-person pair.** For sync_match's team key, each team shouts together as one; the team that doesn't land on a single answer takes the penalty.

## Pool structure (per Grant)

- `coop_tasks` splits into 3: `coop_tasks` (basic), `coop_tasks_timed`, `coop_tasks_sabotage`.
- `blind_lead_tasks` is its own pool (goal-state guidance: "stack three cups", "draw a star") — distinct from coop_tasks.
- `password_words` is a dedicated guessable-word pool, NOT sync_prompts.
- **sync_prompts is ONE shared, curated pool** for match/don't-match/group shells. Curate to a small common-knowledge answer space ("a number 1-10", "a color", "a fast food chain") so every entry gives a real match chance. Avoid wide-open prompts ("a celebrity").

## Open placement questions (Grant to decide)

- `password.v1` — keep in Cooperative or move to Word Games?
- `group_freeze.v1` — true shared-fate coop, or Physical/reaction category? (it has a single "last person loud" loser).
