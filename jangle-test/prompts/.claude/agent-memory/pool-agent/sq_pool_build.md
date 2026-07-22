---
name: sq-pool-build
description: Architecture decisions and grammar patterns for superlative_questions and self_rating_dimensions pool builds (voting migration part 2)
metadata:
  type: project
---

# superlative_questions and self_rating_dimensions Pool Build

## Pool structure: superlative_questions
- Composite: `superlative_questions` (no tags, no entries, subpools only)
- Leaves: `superlative_questions_party` ["Party"], `superlative_questions_spicy` ["Spicy"], `superlative_questions_degen` ["Degen"]
- NO spicy_degen leaf (too few entries after adjudication — 2 entries reassigned to spicy/degen)
- Location: `pools/voting/` — voting-specific, not shared

## Pool structure: self_rating_dimensions
- Composite: `self_rating_dimensions` (no tags, no entries, subpools only)
- Leaves: `self_rating_dimensions_party` ["Party"], `self_rating_dimensions_spicy` ["Spicy"]
- NO degen leaf (no dimensions authored that are purely degenerate without being sexual)
- Location: `pools/voting/` — voting-specific

## Grammar discipline: superlative_questions
Shell renders: "Vote: [superlative_questions] Most votes takes [Penalty]."
- ALL entries must be self-contained questions ending in "?"
- Forms: "Who would...?", "Who has...?", "Who's the...?", "Who gives off...?"
- NO penalty tokens in entries — shell provides them
- NO voting wrapper text ("Vote:", "Everyone votes", "Most votes") — shell provides the wrapper

## Grammar discipline: self_rating_dimensions
Shell renders: "[Player A], rate yourself out of 10 [self_rating_dimensions]."
- ALL entries must be prepositional or noun phrases: "in bed", "as a driver", "at karaoke"
- Opens with "in" (location/context), "as a" (role), or "at" (skill)
- NO "rate yourself" or "out of 10" in entries — shell provides those
- NO trailing punctuation

## Source extraction exclusions (voting_prompts.json)
1. MLT traits (already migrated): any "most likely to [infinitive]" forms → mlt_* pools
2. Accusation forms ("Point at someone who's definitely/probably X") → mlt_* pools  
3. Duel prompts [Player A] vs [Player B] → IDs 16, 185, 289, 323, 353, 369, 384, 389
4. Self-rating prompt (id 501) → self_rating_dimensions pool (this pool)
5. SQ entries dropped if MLT shell would render near-identically (see adjudicated_boundaries.md)

## Pool structure: superlative_positive (added voting valence restructure)
- Composite: `superlative_positive` (no tags, no entries, subpools only)
- Leaves: `superlative_positive_party` ["Party"], `superlative_positive_spicy` ["Spicy"], `superlative_positive_degen` ["Degen"]
- Location: `pools/voting/`
- superlative_questions is now the NEGATIVE pool; superlative_positive is the POSITIVE pool

## Final entry counts (post-valence restructure)
- superlative_questions_party: 61 entries (was 104; 43 moved to superlative_positive_party)
- superlative_questions_spicy: 11 entries (was 16; 5 moved to superlative_positive_spicy)
- superlative_questions_degen: 18 entries (was 20; 2 moved to superlative_positive_degen)
- Total superlative_questions (negative): 90

- superlative_positive_party: 43 entries
- superlative_positive_spicy: 5 entries (NOTE: actual pool currently has 6 entries — count updated from source)
- superlative_positive_degen: 2 entries
- Total superlative_positive: 51

- self_rating_dimensions_party: 18 entries
- self_rating_dimensions_spicy: 7 entries
- Total self_rating_dimensions: 25 entries
