---
name: cooperative-pool-build
description: Cooperative category pool architecture, the sync_prompts match-odds curation bar, and grammar/voice patterns for the cooperative shells.
metadata:
  type: project
---

# Cooperative Category Pool Build

Cooperative is a new alpha category. Shells live in `shells/cooperative.shells.json` (shell-agent owns). Pools live in `pools/cooperative/`.

## sync_prompts (built v1 — 2026-06-08, starter batch for Grant approval)

Feeds 3 shells, all consume the same composite token `[sync_prompts]`:
- `sync_match.v1` — "both name [sync_prompts]" / match = safe, mismatch = penalty
- `sync_dont_match.v1` — "both name [sync_prompts]" / match = jinx/lose
- `sync_group.v1` — "everyone shout [sync_prompts]" / nobody matches = table penalty

**THE curation bar (Grant's stated #1 judge):** small, common-knowledge SHARED answer space. Two people must have a meaningful-but-not-guaranteed chance of independently saying the same answer.
- GOOD: number 1-10, primary color, fast food chain, pizza topping, day of week, card suit, barnyard animal.
- BAD too-wide (match odds ~0): celebrity, movie, song, country, bare "animal".
- BAD too-narrow/binary/single-obvious-answer: avoid coin-flip-degenerate or one-obvious-answer prompts.
- ONE pool serves all 3 shells (do NOT split match vs dont-match) → answer space must stay moderate either way.

**Grammar fit:** each entry is a short noun phrase that reads clean in BOTH "both name ___" and "everyone shout ___". Lowercase, no terminal punctuation, no em dashes, no colons. (Same entry-format discipline as other text leaves.)

## sync system — CURRENT structure (2026-06-09, mode-aware via mixed pools)

The old single `sync_prompts`/`sync_prompts_party` is RETIRED. Current tree:

**Party difficulty leaves** (all `["Party"]`):
- `sync_small` — ≤5-option closed sets (17 entries)
- `sync_mid` — MIXED: ~6–15-option sets (22 Party entries) + `subpools: ["sync_spicy","sync_degen"]`
- `sync_large` — MIXED: clustered-open/large spaces (50 Party entries) + `subpools: ["sync_spicy","sync_degen"]`

**Mode leaves** (single-tag per A8, plain leaves, referenced by BOTH sync_mid + sync_large):
- `sync_spicy` `["Spicy"]` — sexual/romantic/flirty, App-Store-survivable (suggestive not explicit)
- `sync_degen` `["Degen"]` — NON-sexual debauchery (liquor brands, drinking games, hangover cures, drunk regrets). T1: do NOT put sexual content here.

**Composites** (untouched, shell-agent owns refs): `sync_match_prompts` → [sync_small, sync_mid]; `sync_dodge_prompts` → [sync_mid, sync_large]. Group shells point straight at sync_mid / sync_large.

**Why mixed pools make all 4 shells mode-aware with ZERO shell edits:** in Party sessions spicy/degen subpools get weight 0 and are pruned (only Party entries surface). In Spicy sessions sync_spicy surfaces at recipe weight, degen pruned (vice versa). Composites inherit spicy/degen transitively through sync_mid/sync_large; the `_seen` cycle guard prevents double-collection where sync_spicy is reachable via two paths. sync_small deliberately has NO spicy/degen subpools (it's reached for spicy via the sync_mid path).

**Curation bar for sync entries:** lowercase article-led noun phrase, no terminal punct / em dash / colon, reads clean in BOTH "both name ___" and "everyone shout ___", and a matchable mid-sized common-knowledge answer space (two people can plausibly land the same answer). Lean mid-sized to keep tension in large groups.

**Known limitation (acceptable for alpha, flagged to Grant):** sync_spicy/sync_degen are single (non-tiered) leaves, so for the 5+ player `sync_group_large` shell in a Spicy/Degen session a small-answer-space entry could make matching too easy. Mitigated by leaning entries mid-sized. Revisit if playtest shows it's too easy → may need tiered spicy/degen leaves.

**PreGame.yyp:** sync_spicy + sync_degen must be registered in IncludedFiles (main agent, post-approval) or they won't load at runtime.

## HOLD item (2026-06-09)
"a flavor of the five tastes" — Grant's move/cut instruction was ambiguous; left UNTOUCHED in sync_small pending separate confirmation. Do not move/cut it without an explicit ruling.
