---
name: shell-catalog
description: All shell IDs authored or modified by shell-agent, with change type and date
metadata:
  type: project
---

## cooperative.shells.json — 2026-06-08 (Grant prune + revise pass + Round-3 cut)

Started as 36 candidates; pruned to 15 (final, pending review). No subcategories (category has none).

| shell_id | change |
|----------|--------|
| cooperative.sync_match.v1 | KEPT default; team key rewritten to whole-team sync (team that doesn't match takes penalty) |
| cooperative.sync_dont_match.v1 | unchanged |
| cooperative.sync_group.v1 | REVISED: win bar lowered to "no two match" (was whole-table match). Future tweak floated: scale required-match count to player count |
| cooperative.mind_meld.v1 | REVISED: tighter cadence; mechanic renamed to "Same Wavelength" framing (label removable) |
| cooperative.mind_meld_quick.v1 | REVISED: tighter; reward framing dropped to safe/miss; uses wavelength_seeds |
| cooperative.coop_task.v1 | unchanged |
| cooperative.coop_task_timed.v1 | unchanged; pool token now coop_tasks_timed (split) |
| cooperative.coop_sabotage.v1 | RENAMED from coop_task_reward.v1; reworked to sabotage (pair vs everyone else; others take penalty on success); min 3; pool coop_tasks_sabotage |
| cooperative.group_count.v1 | unchanged (Grant loved) |
| cooperative.mirror.v1 | unchanged |
| cooperative.echo.v1 | unchanged (Grant loved) |
| cooperative.contraband.v1 | unchanged (Grant loved) |
| cooperative.synced_action.v1 | PENDING: rephrased for read-aloud; awaiting sample group_actions content |
| cooperative.blind_lead.v1 | PENDING: own pool blind_lead_tasks (goal-state guidance); awaiting sample content |
| cooperative.password.v1 | PENDING: polished + sabotage success framing; needs own password_words pool; placement question (coop vs Word Games) |

REMOVED 21: alternate_chain, group_chain, group_chant, guess_partner, guess_partner_both, how_well, relay, build_word, two_truths_match, sync_three_way, finish_sentence, handoff, trust_recall, group_wave, pair_pose, agree_fast, group_agree, keep_alive, mirror_action, group_freeze, group_beat (Word-Games-adjacent — confirmed kill reason).

## phone.shells.json — 2026-06-07

| shell_id | change |
|----------|--------|
| phone.condition.v1 | ADDED (players.min 3, tags []); pool: phone_conditions; group-condition frame; subcategory_id: condition |

## commands.shells.json — 2026-06-09 (Tier B singleton→pool upgrade + new shell)

Original 10 shells created 2026-06-07 (5 pool-backed + 5 singletons). Fable session 2026-06-09 upgraded all 5 singletons to pool-backed and added 1 new shell → 11 shells, all pool-backed.

| shell_id | change |
|----------|--------|
| commands.assign_trait.v1 | unchanged (pool-backed since creation) |
| commands.assign_judgment.v1 | unchanged (pool-backed since creation) |
| commands.condition_takes.v1 | unchanged (pool-backed since creation) |
| commands.condition_assigns.v1 | unchanged (pool-backed since creation) |
| commands.speed_last.v1 | unchanged (pool-backed since creation) |
| commands.group_condition.v1 | MODIFIED: singleton → pool-backed; new token [group_triggers]; "Everyone who [group_triggers] takes [Penalty, 2]." |
| commands.duo_gag.v1 | MODIFIED: static punchline → pool; new token [duo_punchlines]; standalone sentence appended after penalty |
| commands.directed_split.v1 | MODIFIED: added [split_flavors] closer sentence; token is plural (pool_id=split_flavors) |
| commands.directed_proxy.v1 | MODIFIED: added [proxy_framings] closer sentence; mechanic sentence unchanged |
| commands.point_chain.v1 | MODIFIED: added [chain_framings] closer sentence; mechanic sentence unchanged |
| commands.would_you_dare.v1 | ADDED (players.min 3, tags []); pool: wyd_actions; "[Player A], pick someone. They have to [wyd_actions] or take [Penalty, max]." |

New pools created for Tier B upgrade: group_triggers (30), duo_punchlines (20), split_flavors (15), proxy_framings (5), chain_framings (5), wyd_actions (40). Total commands entries: 585 across 10 pool files (take_conditions composite-only).

## active_effects.shells.json — 2026-06-13 (first-draft production from phase-five brainstorm)

77 shells across 30 families. WW-SHELL-1 dropped per Grant ("callback isn't its own shell"). No subcategories. All pool tokens reference actual pool_ids; 5 REUSE + 24 NEW pools documented in active_effects_pool_manifest.md. Key edits applied: slip_race winner-consequence text added; V-SHELL-1 "every prompt category" phrase removed; V-SHELL-3 min raised to [Penalty, 3]; DD-SHELL-1 first-to-break [Penalty, 5]; DD-SHELL-2 last-to-break gives [Penalty, max]; EE-SHELL-1 renamed coop_mirror, "fallen out of sync"; X-SHELL-2 shared-fate; X-SHELL-3 trailing line removed.

Note: brainstorm says "71 shells" but the roster table maps to 78 with WW-SHELL-1. After dropping WW-SHELL-1 per Grant = 77. The 71 figure in the brainstorm is a counting discrepancy in that doc, not in the JSON.

## confessions.shells.json — 2026-06-07

| shell_id | change |
|----------|--------|
| confessions.confess.v1 | unchanged |
| confessions.tell_table.v1 | RENAMED to confessions.tell_group.v1; "tell the table" → "tell the group"; refusal clause changed to "Stay quiet and take [Penalty, 2-3]." |
| confessions.tell_group.v1 | result of rename above |
| confessions.question.v1 | ADDED (players.min 2); pool: confession_prompts; question-delivery frame |
| confessions.spill.v1 | ADDED (players.min 2); pool: confession_prompts; spill-delivery frame |
| confessions.have_you_ever.v1 | unchanged |
| confessions.describe.v1 | unchanged |
| confessions.tally.v1 | ADDED (players.min 2, tags []); pair pool: tally_confessions (.a = list to name, .b = per-item condition); penalty verb "Take" |
