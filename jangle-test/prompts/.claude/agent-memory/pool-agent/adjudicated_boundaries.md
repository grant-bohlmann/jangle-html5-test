---
name: adjudicated-boundaries
description: Canonical source for all content-routing and dedup adjudication precedents — which pool does X belong in, and why. Voice/tone/authoring rules live in voice_principles.md instead.
metadata:
  type: project
---

# Adjudicated Boundary Precedents

## superlative_questions vs most_likely_to_traits (voting migration)

**Ruling:** Entries that take the form "Who's the most likely to [infinitive]?" are EXCLUDED from sq_* if the infinitive already exists as an MLT trait in mlt_* — rendered output via voting.most_likely.v1 shell would be near-identical.

Dropped from SQ due to MLT overlap (apply consistently going forward):
- "Who's the most likely to slide into someone's DMs tonight?" → most_likely_to_traits_spicy already has "slide into someone's DMs tonight"
- "Who's the most likely to be secretly broke?" → most_likely_to_traits_degen has "be secretly broke"
- "Who's the most likely to become an influencer?" → most_likely_to_traits_party has "become an influencer"
- "Who's the most likely to have a secret love child?" → most_likely_to_traits_spicy_degen has "have a secret love child"
- "Who's the most likely to ghost all their friends and move to another country?" → most_likely_to_traits_degen has "ghost all their friends and move to another country"
- "Who's the most likely to lie about their body count?" → most_likely_to_traits_spicy has "have lied about their body count"
- "Who gives off the most bisexual energy?" → most_likely_to_traits_spicy has "give off the most bisexual energy"
- "Who's the most likely to be a cam girl or cam guy?" → most_likely_to_traits_spicy_degen has "be a cam girl or cam guy"

**Principle:** Semantic overlap between SQ and MLT is acceptable ONLY when the question form adds a genuinely different framing. "Who's the most dramatic?" (SQ) vs "be the most dramatic" (MLT) → KEEP BOTH (SQ stands alone as a direct superlative question). "Who's the most likely to become an influencer?" (SQ) vs "become an influencer" (MLT) → DROP SQ (shells render identically).

## superlative_questions_spicy vs superlative_questions_degen (stripper boundary)

- "Who would be the best stripper?" → superlative_questions_spicy (sexual performance, inherently Spicy)
- "Who can come up with the best stripper name?" → superlative_questions_degen (creative party activity, fun without explicit sexual content)

**Principle:** Stripper-as-performance → Spicy. Stripper-adjacent activities (naming, talking about, watching) → Degen.

## superlative_questions_spicy_degen handling

Only created if 3+ entries genuinely fit BOTH Spicy AND Degen simultaneously. In the voting migration:
- "Who has the most embarrassing search history?" + "Who has the dirtiest search history?" were near-dupes; kept only "dirtiest" (more pointed) and assigned to superlative_questions_spicy.
- "Who can come up with the best stripper name?" reassigned to superlative_questions_degen.
- No superlative_questions_spicy_degen leaf created (too few entries after adjudication).

## voice clusters / near-dupe resolution (voting migration)

Voice/laugh cluster — kept:
- "Who has the most annoying laugh?" (superlative_questions_party)
- "Who has the best laugh?" (superlative_questions_party)
- "Who has the best voice?" (superlative_questions_party)

Dropped as weaker/redundant:
- "Who has the most unique voice?" → vaguest of the cluster
- "Who has the most infectious laugh?" → near-dupe of "best laugh"
- "Who has the most attractive voice?" → near-dupe of "best voice"

Horror movie pair — KEPT BOTH (different angles):
- "Who would be the first to die in a horror movie?" (active/funny)
- "Who would be the last person you'd want in a horror movie with you?" (accusatory/funnier)

Vacation/stranded cluster — kept 2, dropped 1:
- "Who would be the most fun to go on vacation with?" → KEEP (fun-seeking framing)
- "Who would be the best person to be stranded with?" → KEEP (survival framing, different angle)
- "Who would be the best travel buddy?" → DROP (generic, subsumed by the other two)

Lying cluster — kept 1, dropped 1:
- "Who would be the best at lying to the police?" → KEEP (more specific/funnier)
- "Who would be the best at lying to get out of trouble?" → DROP (near-dupe, less specific)

## superlative_positive vs superlative_questions (valence split, voting restructure)

**Ruling:** Entries where being voted is clearly a compliment/win go to superlative_positive (sqp_*). Entries that are negative, accusatory, or neutral/ambiguous stay in superlative_questions (sq_*).

Boundary principles applied:
- "Who gives off innocent vibes?" → superlative_questions_party NEGATIVE. "Innocent" reads as mocking (naive/sheltered), not complimentary at a party table.
- "Who's the most mysterious?" → superlative_questions_party NEGATIVE. Could imply suspicious/untrustworthy; not a clear compliment.
- "Who would survive the longest without their phone?" → superlative_questions_party NEGATIVE. Ambiguous — could be mocking the most boring person, not a clear win.
- "Who would survive the longest on a reality dating show?" → superlative_questions_party NEGATIVE. Survival = social manipulation skill, not obviously positive.
- Physical compliments (best eyes, best body, best ass, best at flirting, best at giving massages) → superlative_positive_spicy. Being voted = explicit compliment.
- Drinking wins (win a drinking contest, best drinking game partner) → superlative_positive_degen. Winner framing = compliment in Degen context.

## superlative_positive/superlative_positive_degen vs most_likely_positive/most_likely_positive_degen (drinking-win overlap)

- "Who would win in a drinking contest?" (superlative_positive_degen) vs "win a drinking contest" (most_likely_positive_degen) → KEEP BOTH. SQ shell = group vote with penalty mechanic; MLT shell = social prediction. Different mechanics and rendering justify keeping both despite semantic overlap. Precedent: same reasoning as SQ "most dramatic" vs MLT "be the most dramatic" — question form adds a different framing.

## most_likely_positive vs most_likely_to_traits (valence split)

**Ruling:** Entries where being voted "most likely to [trait]" is clearly a compliment go to mlp_*. Entries that are negative, embarrassing, or neutral remain in mlt_*.

Moved from most_likely_to_traits_party to most_likely_positive_party: "become a millionaire", "become famous" (then de-duped against stronger authored variants "be a millionaire by 35" and "be famous one day" respectively — moved versions dropped, stronger versions kept).

Retained in most_likely_to_traits_party despite positive-adjacent surface reading: all "become a [profession]" entries (nurse, chef, etc.) — these are neutral career observations, not clear compliments. "become a professional athlete", "become an entrepreneur" — same reasoning; career aspirations without clear winner/loser dynamic.

Near-dupe resolution within most_likely_positive_party: "become a millionaire" + "be a millionaire by 35" → kept "be a millionaire by 35" (more specific). "become famous" + "be famous one day" → kept "be famous one day" (softer, more natural MLT phrasing).

Near-dupe resolution within most_likely_positive_spicy: "age like fine wine" + "still be hot at 50" → kept "still be hot at 50" (more concrete/funnier).

## self_rating_dimensions_party vs self_rating_dimensions_spicy

- "at flirting" → self_rating_dimensions_spicy (flirting is romantic/sexual)
- "at handling your alcohol" → self_rating_dimensions_party (social skill, not explicitly Degen-only; alcohol-adjacent is fine at Party tier)
- No Degen leaf needed for self_rating_dimensions: none of the authored dimensions are purely degenerate without being sexual.

## topic pool routing (AA3 Task 2 + Duel migration — 2026-06-05/06)

- **"sports movies" → topic_entertainment**, not topic_sports. It's a film genre, not a sports topic. Sports teams/athletes/events/equipment/activities stay in topic_sports. *(AA3 Task 2 cleanup — swapped, topic_sports backfilled with "famous sports chants".)*
- **"cocktails and mixed drinks" (topic_food) vs "cocktails with ridiculous names" (topic_degen):** Keep both. Food = general beverage/mixology category; Degen = bar-culture humor (weirdly-named drinks). Different vibes and answer spaces.
- **"cocktails and mixed drinks" (topic_food) vs "types of alcohol" (topic_degen):** Keep both. Food = mixology/beverage category; Degen = vice-framing ("what's your poison"). Different social energy.
- **"reality TV shows" (topic_entertainment) vs "reality TV stars who became famous" (topic_pop_culture):** Keep both. Entertainment = media titles (shows); Pop culture = the people (celebrities who rose to fame). Non-overlapping answer spaces.
- **"famous movie soundtracks" (topic_entertainment) vs "songs from movie soundtracks everyone knows" (topic_pop_culture):** Keep both. Entertainment = soundtrack albums/films; Pop culture = specific recognizable songs (entertainment answers = "Titanic"; pop culture answers = "My Heart Will Go On").
- **"music videos everyone has seen" (topic_entertainment) vs "songs that were inescapable for a summer" (topic_pop_culture):** Keep both. Entertainment = the visual format/artifact; Pop culture = the cultural saturation moment.
- **"world capitals" vs "capital cities" (duel migration):** Same concept, keep "world capitals" in topic_general. Dropped "capital cities."
- **"Olympic events" (duel source) vs "Olympic sports" and "winter Olympic events" (topic_sports):** "Olympic events" is a near-duplicate of existing entries. Dropped the incoming entry.
- **"Disney movies" (duel source) vs "animated Disney movies" (topic_entertainment):** "animated Disney movies" is the preferred specific form; the broad "Disney movies" duplicates its answer space. Dropped "Disney movies."
- **"video games" (duel source) vs "video game franchises" (topic_entertainment):** Near-duplicate answer space. Kept "video game franchises" (more specific). Dropped bare "video games."
- **"cartoon characters" (duel source) vs "famous cartoon characters" (topic_entertainment):** Exact near-dupe. Dropped incoming; "famous cartoon characters" already present.
- **"breakfast foods" and "snacks" (duel source) vs topic_food entries:** "breakfast foods" is an exact dupe. "snacks" is a near-dupe of "snacks you'd find at a party." Both dropped.
- **"books" → topic_entertainment:** Books are media products (like film/TV/music). "books everyone claims to have read" chosen over bare "books."
- **"superheroes" (characters) vs "superhero movies" (topic_entertainment):** Different answer spaces — characters (Spider-Man, Batman) vs films (The Dark Knight, Avengers). Kept both in topic_entertainment.
- **"historical figures" → topic_general, not topic_pop_culture:** Historical figures predate the pop-culture era; knowledge/trivia territory.
- **"world leaders past or present" → topic_general, not topic_pop_culture:** Specifically political leadership roles; general-knowledge territory.
- **"brands" → topic_general:** Spans many industries (tech, fashion, automotive, food) with no dominant category fit.
- **"car models" → topic_general, not topic_pop_culture:** Knowledge category rather than cultural-saturation territory.
- **"love songs" → topic_pop_culture:** Music is pop culture's domain. Genre-mood slice of musical culture distinct from existing decade/artist entries.
- **"bands or artists" → topic_pop_culture:** Broad catch-all musical category distinct from existing decade/genre-specific entries.
- **"celebrities" → topic_pop_culture:** Existing entries are subcategories (feuds, scandals, one-name celebrities). Bare "celebrities" fills the general-round slot.
- **"sports teams" → topic_sports:** topic_sports has "NFL teams" and "NBA teams" as league-specific entries; "sports teams" is the broad cross-sport entry alongside them.
- **"drinks" → topic_food:** Beverages broadly (juice, soda, water, cocktails, tea) are food-category territory; not vice-framed. Distinct from "cocktails and mixed drinks" (mixology) and "cocktails with ridiculous names" (degen humor).
- **"desserts" → topic_food:** "baked goods" covers a subset; "desserts" is broader (ice cream, pie, pudding, candy). Non-overlapping enough to keep both.
- **"sandwich ingredients" → topic_food:** "sandwiches" already in topic_food; "sandwich ingredients" is a meaningfully different answer space (what's inside vs. the sandwich itself). Kept both.
- **"fairy tale characters" → topic_general:** Fairy tales predate media; knowledge-based category, not entertainment-media product.
- **"musical instruments" → topic_general:** No strong entertainment/sports/pop-culture lean. Note: broad_topics has "musical instrument" (singular, letter-game context); topic_general has "musical instruments" (plural, categories-game context) — different pools, no conflict.
- **"types of dances" → topic_general:** Knowledge-based; not pop-culture (trend) or entertainment-product framing.
- **"holidays" → topic_general:** General-knowledge category.
- **"things in a kitchen" → topic_general (not a dupe of broad_topics):** broad_topics has "thing in a kitchen" (singular, letter-game shell); topic_general has "things in a kitchen" (plural, categories-game shell). Different pools, different consuming shells.
- **"authors" → topic_general:** Literary/knowledge territory distinct from topic_entertainment (media products) and topic_pop_culture (celebrity-era figures).

## most_likely_to_traits_party reality TV swap (2026-06-07)

- **"have a reality TV show about their life" → REMOVED from most_likely_to_traits_party.** Replaced with "end up on a reality TV show" (same pool). The new phrasing is more grounded (it's a fate that happens to you rather than a career you pursue) and avoids the near-dupe risk with a potential future "become an influencer"-class entry. Precedent from commands migration: "end up on a reality TV show" was previously dropped as near-dupe of the old entry; now the old entry is gone, so the new entry is the canonical form.

## filter_conditions determinism sweep (2026-06-07)

**Rule:** filter_conditions entries must be deterministic and verifiable at the table without group judgment. Subjective opinions, appearance judgments, and race-requiring comparisons are excluded.

Entries pulled and routed:

From filter_conditions_silly:
- "has the loudest laugh" → DROPPED (laugh superlatives already covered in voting: "most annoying laugh" in superlative_questions_party, "best laugh" in superlative_positive_party)
- "has the worst posture right now" → ROUTED to superlative_questions_party as "Who has the worst posture right now?"
- "is dressed the most formally" → DROPPED (near-dupe of superlative_positive_party "Who has the best style?")
- "walks the fastest" → DROPPED (requires a race; no natural voting equivalent)
- "walks the slowest" → DROPPED (same)
- "is sitting in the most uncomfortable position" → DROPPED (subjective; no natural voting equivalent)
- "has the most embarrassing nickname from their past" → ROUTED to superlative_questions_party as "Who has the most embarrassing nickname from their past?"
- "is the most freshly showered" → DROPPED (no natural voting equivalent; too odd as a superlative)
- "is the most directionally challenged" → ROUTED to superlative_questions_party as "Who is the most directionally challenged?"
- "eats the fastest" → ROUTED to superlative_questions_party as "Who eats the fastest?"
- "eats the slowest" → ROUTED to superlative_questions_party as "Who eats the slowest?"

From filter_conditions_degen:
- "looks the most sober right now" → ROUTED to superlative_questions_degen as "Who looks the most sober right now?"

**Kept as borderline-but-deterministic (self-reported habits, not opinions about others):**
- "naps the most" / "never naps" — binary self-report, settleable by show of hands
- "works out the most" / "works out the least" — personal habit, self-reported
- "has gone the longest without changing their hairstyle" — factual personal history, self-reported

## rhyme_starters (Duel migration — 2026-06-06)

- **"play" (rhyme_starters candidate) → dropped:** Same -ay rhyme family as "day" (already in pool). Family already covered.
- **"love" → rhyme_starters:** -ov/-uv family (love, dove, shove, above, glove). Not previously covered. Added.
- **"fire" → rhyme_starters:** -ire family (hire, wire, tire, desire). Distinct from -ine family ("shine"). Added.
- **"time" → rhyme_starters:** -ime family (crime, dime, lime, mime, prime). Added.

## WYR pool routing (WYR pilot + expansion — 2026-06-05)

- **"texts read aloud by boss/parents" (wyr_everyday) vs "romantic texts read aloud" (wyr_spicy):** Keep both. Everyday = workplace/family embarrassment; Spicy = romantic/sexual exposure. Same mechanic, different content registers.
- **"tell when someone likes you" (wyr_everyday b-side) vs "know exactly when someone is attracted to you" (wyr_spicy a-side):** Keep both. Everyday = general social awareness ("likes you" reads platonic or otherwise); Spicy = explicitly romantic attraction.
- **"give up coffee forever / give up alcohol forever" (wyr_everyday) vs "never drink again / never smoke weed again" (wyr_degen):** Keep both. Everyday = coffee vs alcohol (one non-vice substance, balanced dilemma); Degen = alcohol vs weed (pure vice-comparison).
- **"find out your partner has been reading your journal / venting to their ex" (wyr_spicy) vs "know every thought your partner has had about you" (wyr_couples):** Keep both. Spicy = specific betrayal acts (breach of trust with romantic/sexual tension); Couples = philosophical thought-transparency trade-off about intimacy dynamics.
- **"always be the one who loves more / loved more" (wyr_spicy) vs relationship-dynamics pairs in wyr_couples:** Keep in wyr_spicy. Asymmetric love is a general romantic-life question with romantic tension energy, not specific to an established partnership. Couples pool reserves relationship-specific mechanics (planning, arguments, family approval, cohabitation).
- **"show your most recent camera roll to this room" (wyr_spicy) vs "have your camera roll from last Saturday shown to this room" (wyr_degen):** Keep both. Spicy = general current camera roll (intimate/romantic content implied); Degen = specifically Saturday night (party/degenerate-behavior photos). Same mechanic, different content registers.
- **"know every person who has ever had a crush on you" (wyr_spicy) vs "know every person who has fantasized about you" (wyr_spicy):** Keep both within spicy. Crush = romantic/emotional interest disclosure; fantasy = specifically sexual disclosure. Different in what's being revealed.
- **"always have the last word in any argument" (wyr_everyday) vs "never argue but also never fully resolve anything / argue constantly but always reach a real resolution" (wyr_couples):** Keep in respective pools. Everyday = personal character trait (stubbornness) that applies in any conflict with anyone; Couples = relationship-pattern dynamics with a partner. Character trait vs. partnership pattern.

## NHIE pool routing (NHIE pilot — 2026-06-05)

- **"been in handcuffs" (nhie_degen) vs "been handcuffed to a bed" (nhie_spicy):** Keep both. Degen = arrested/detained by police (reckless-behavior consequence); Spicy = consensual bedroom restraint. Same object, entirely different contexts.
- **"had a walk of shame" (nhie_spicy) vs "woken up still wearing last night's outfit" (nhie_degen):** Keep both. Spicy = post-hookup morning-after walk (sexual implication); Degen = passed out too drunk to undress (blackout/party implication). Adjacent imagery, different root causes.
- **"gotten a tattoo I regret" (nhie_party) vs "gotten a tattoo while under the influence" (nhie_degen):** Keep both. Party = generic tattoo regret (any cause); Degen = specifically impulsive drunk/high tattoo decision. Partial overlap acceptable — Party version is broad enough to cover non-degen regret tattoos.
- **"snuck out of the house at night" (nhie_party) vs "had to climb out of a window to avoid being caught" (nhie_degen):** Keep both. Party = adolescent sneaking out (standard growing-up behavior); Degen = adult escape from a compromising situation. Different life stages and contexts.
- **"been the reason someone cheated" (nhie_spicy) vs "helped a friend cover up their cheating" (nhie_degen):** Keep both. Spicy = you were the other person in the affair (sexual involvement); Degen = you were the social accomplice (no sexual act by you). Different roles in the same scenario.

## MLT pool routing (MLT migration — 2026-06-06)

- **"be a secret furry" (most_likely_to_traits_party) vs "be into furry stuff" (most_likely_to_traits_spicy_degen):** Keep both. Party = identity-framing (secret personal identity, social embarrassment); Spicy+Degen = sexual kink framing. Same subject, completely different registers.
- **"have stalked someone on social media this week" → most_likely_to_traits_degen, not most_likely_to_traits_spicy_degen:** Source tagged ["Party","Degen"]. No sexual component — social media surveillance is degenerate behavior, not sexual.
- **"have a secret Tinder while in a relationship" → most_likely_to_traits_spicy_degen, not most_likely_to_traits_spicy:** Source tagged ["Spicy","Degen"]. Tinder-while-partnered is both sexual (hookup app) and degenerate (secret, cheating behavior). Both tags earned.
- **"have stalked their partner's ex on social media" → most_likely_to_traits_party:** Relationship jealousy/creeping without sexual content. Dominant vibe is social embarrassment, not sexual. Party wins over spicy even when originally tagged ["Party","Spicy"].
- **"drunk text their ex tonight" → most_likely_to_traits_degen (not most_likely_to_traits_spicy_degen):** Source tagged ["Party","Degen"]. Text to an ex is degenerate behavior but has no inherent sexual act. Compare to "drunk dial their ex tonight" (also most_likely_to_traits_degen). Kept both as distinct acts (text vs call).

## commands pool routing (commands migration — 2026-06-07)

- **judgment_clauses (judgment_clauses_*) vs superlative_questions (sq_*) — same question, different mechanics:** Semantic overlap is acceptable. judgment_clauses_* renders "[Player A], give [Penalty] to whoever you think ___" (one player decides). sq_* renders "[question] Everyone votes. Most votes takes penalty" (group vote). Same content, different social dynamics. Precedent: SQ "most dramatic" vs MLT "be the most dramatic." Boundary case examples: "worst roommate", "messiest room right now", "worst spending habits", "most competitive" — all kept in both pools.

- **"most likely to [X]" form in command prompts → excluded from judgment_clauses:** Command prompts of this exact form belong in most_likely_to_traits (most_likely_to_traits_*) not judgment_clauses. Judgment predicates read after "whoever you think ___" — if that rendering produces "whoever you think is most likely to [X]", exclude it from judgment_clauses_* entirely and route to most_likely_to_traits_* instead.

- **filter_conditions_spicy entries (relationship/dating conditions) vs nhie_spicy:** No overlap found. nhie_spicy = first-person past experiences ("had a threesome"); filter_conditions_spicy = observable current facts about a person ("has the most ex-partners"). Different entry shapes and shells.

- **"sent a message to the wrong person this week" [Party, Spicy source] → filter_conditions_party, not filter_conditions_spicy:** Despite Party+Spicy source tag, this condition isn't inherently sexual (could be any message). T1 applies — Spicy = sexual/romantic. Reassigned to filter_conditions_party.

- **"has ended the most friendships" [Party, Spicy source] → filter_conditions_party, not filter_conditions_spicy:** Social fallout without sexual content. Source tag Spicy was likely editorial/social-drama tagging, not T1-compliant. Reassigned to filter_conditions_party.

- **MLT command additions — SKIPPED entries (near-dupes or A5 violations):**
  - "black out tonight" → exact dupe of existing most_likely_to_traits_degen entry. Dropped.
  - "text their ex tonight" → near-dupe of "drunk text their ex tonight" (most_likely_to_traits_degen). Dropped.
  - "start the next drama in this group" → near-dupe of "start drama before the night ends" (most_likely_to_traits_degen). Dropped.
  - "end up on a reality TV show" → near-dupe of "have a reality TV show about their life" (most_likely_to_traits_party). Dropped.
  - "accidentally burn dinner" → near-dupe of "accidentally set off a fire alarm while cooking" (most_likely_to_traits_party). Dropped (alarm version is funnier).
  - "make a terrible first impression at a job interview" → A5 violation (scenario hypothetical). Dropped.
  - "move to another country in the next five years" → A5 violation (scenario hypothetical). Dropped.
  - "have a meltdown over something minor" → near-dupe of "have a mental breakdown over something small" (most_likely_to_traits_party). Dropped.

## confessions salvage additions (2026-06-07)

**Grant-approved salvages from un-normalized list — routing rulings:**

- **6009 "the juiciest thing you've cheated on, whether a test, a partner, or a diet" → confession_prompts_spicy:** Multi-part comma-fork form is acceptable in confession_prompts_spicy. No colon — the comma handles the branching. Retained exactly as authored.
- **6175 "someone you would have dated but never admitted it to" → confession_prompts_spicy:** Person-referent entry. Renders awkwardly in "what's [entry]?" shell but cleanly in "confess [entry]" and "tell the group [entry]" shells. Accepted.
- **6220 "someone from a past relationship you still quietly check up on" → confession_prompts_spicy:** Person-referent. Same shell-coverage reasoning as 6175. Accepted.
- **6135 "the person you had the hardest time getting over" → confession_prompts_spicy:** Person-referent. Confirmed distinct from "the person from your past you still secretly compare new people to" (compare vs. get over — different angle). Accepted.
- **6145 "the most embarrassing nickname you've ever had" → confession_prompts_party:** Two-part form stripped to single topic (nickname only, origin dropped). Clean noun-phrase read. Distinct from "most embarrassing phase" in confession_prompts_party. Accepted.
- **6150 "the most uncomfortable compliment you've ever received" → confession_prompts_party:** Two-part form stripped (who-it-was-from dropped). Clean noun-phrase. Distinct from "most awkward compliment you've ever given" (that is giving; this is receiving). Accepted.
- **6246 "something you've done with someone in this room that no one else here knows about" → confession_prompts_spicy:** In-room tension preserved. Confirmed distinct from "a secret you've been keeping from someone in this room" (done WITH someone vs. keeping FROM someone — different social structure). Accepted.
- **6086 "had a secret finsta or alt account" → nhie_party:** Distinct from "made a burner account to stalk someone" (nhie_party) — burner = anonymous stalking; finsta/alt = curated second identity for personal reasons. Different behaviors, kept both.
- **6127 "had a secret crush on someone in this room" → nhie_spicy:** Confirmed distinct from "had a dream about someone in this room", "kissed someone in this room", "had a secret hookup with someone in this room". Crush = unexpressed feeling; those are acts. Accepted.
- **6258 "Who in this room is probably the best in bed?" → superlative_positive_spicy:** Positive-valence, winner framing. Confirmed distinct from superlative_questions_spicy "in bed" entries (loudest/most submissive/most dominant — all ambiguous-to-negative). Being voted = explicit compliment. Consistent with superlative_positive_spicy physical-compliment pattern.

## tally_confessions pool routing (Task B — 2026-06-07)

**"three exes / you'd get back with after two drinks" → tally_confessions_spicy (not tally_confessions_degen):** Grant approved this as "spicy or degen." Ruled Spicy: the content is romantic (getting back with an ex); "after two drinks" is flavor/mechanism, not the substance. Dominant theme is relationship/romantic. T1 governs.

**tally_confessions_party vs tally_confessions_spicy for social-embarrassment pairs:** Pairs where no sexual or drinking content is present (apologies owed, fights you started, people's opinions that keep you up) → tally_confessions_party. Pairs naming hookup partners, exes, or attracted-to people → tally_confessions_spicy. Clear T1 line.

## confession_prompts rewording rulings (Task A — 2026-06-07)

**Person-referent cp entries reworded for "what's [entry]?" shell compatibility:** Five cp entries were person-referents ("the last person you...", "someone you..."). Reworded to thing/story/moment noun phrases. Rulings:
- "the last person you talked trash about behind your back" → "the last time you talked trash about someone behind their back" (moment-referent)
- "the person from your past you still secretly compare new people to" → "the standard from your past you still secretly hold new people to" (thing-referent)
- "someone you would have dated but never admitted it to" → "the attraction you never admitted, even when you had the chance to act on it" (feeling/thing-referent)
- "someone from a past relationship you still quietly check up on" → "the ex you still quietly check up on" ("the ex" reads as a type/role, not a named person; natural party-game phrasing)
- "the person you had the hardest time getting over" → "the breakup you had the hardest time getting over" (event-referent; distinct from "the lowest point you reached after a breakup" which is aftermath state, not the breakup itself)

## confessions pool routing (confessions migration — 2026-06-07)

**Confession source multi-tag adjudication — T1 governs, not source tags:**

- **[Spicy, Degen] source + non-sexual non-degenerate content → confession_prompts_party:** Source tags on confessions_prompts.json were editorial, not T1-compliant. Entries like "worst fight over something trivial", "something said in anger", "worst decision from stubbornness" were tagged Spicy+Degen in source but have no sexual or degenerate content. Routed to confession_prompts_party. T1 rule (Spicy = sexual; Degen = non-sexual debauchery) governs, not source attribution.

- **[Party, Spicy, Degen] source + generic embarrassment content → confession_prompts_party:** Three-tag source entries where content is generic (embarrassing thing caught doing; most embarrassing search; most embarrassing group chat message) → confession_prompts_party. Tag inflation in source is not a reason to include in Spicy or Degen leaves.

- **"the most reckless thing you've ever done to keep the attention of someone you were seeing" → confession_prompts_spicy (not confession_prompts_degen):** Tagged [Spicy, Degen] in source. Dominant context is romantic/relationship pursuit. Spicy wins over Degen.

- **"the most scandalous thing you've done that only one other person knows about" → confession_prompts_spicy:** Tagged [Spicy, Degen] source. Scandalous secret implies sexual register more than degenerate. Routed to confession_prompts_spicy. (No confession_prompts_spicy_degen leaf created — insufficient qualifying entries after adjudication.)

- **confession_prompts_party entry "get someone's number romantically" vs "get someone's attention romantically":** Same concept. "Get someone's number" is funnier/more specific. Dropped the broader "attention" phrasing.

- **"something you only do when completely alone" (confession_prompts_party) vs "most embarrassing thing you do at home":** Near-dupe. Kept "alone" phrasing (broader), dropped "at home" version.

**NHIE additions from confessions migration — dedup rulings:**

- **6119 "been kicked out of a bar" → DROPPED:** nhie_degen already has "been escorted out of a bar or club." Same event, different phrasing. Dropped incoming.
- **6121 "used a fake ID or lied about your age" → DROPPED:** nhie_degen already has "used a fake ID." Exact dupe.
- **6124 "driven or operated something after a night out" → DROPPED:** nhie_degen has "driven after one too many." Same concept, drop the broader version.
- **6129 "flirted my way out of trouble, a ticket, or a fee" → DROPPED:** nhie_party has "flirted my way out of a speeding ticket" — the specific is funnier. Drop the broader incoming version.
- **6173 "developed a real interest in someone and found out they were with someone else" → DROPPED:** Near-dupe of 6050 "developed feelings for someone who was already in a relationship." Same concept, drop 6173.
- **6253 "slept with someone knowing I absolutely shouldn't have" → DROPPED:** nhie_spicy has "hooked up with someone I knew was bad for me." Same concept, existing phrasing cleaner.
- **6254 "faked it in bed" → DROPPED:** nhie_spicy has "faked an orgasm." Same concept.
- **6026 "kissed someone in this room" → ADDED to nhie_spicy:** Not present in nhie_spicy despite in-room social tension being distinct from "had a secret hookup with someone in this room." The kiss is lighter/funnier. Kept.
- **6041 "ghosted someone I actually liked" → ADDED to nhie_party:** Not present in nhie_party (which has "stalked an ex at 2am" but not regret-ghosting). Kept.

**Confession source entries NOT normalized (surface for Grant):**

- 6009 [Party, Spicy]: Multi-part — "cheated on a test, partner, or diet? Fess up to whichever's juiciest." Can't normalize to single topic without losing the multi-part humor.
- 6019 [Party, Couples]: Two-player mechanic — "[Player A] and [Player B], confess one thing about the other you've never said." Not a single-speaker topic.
- 6052 [Spicy]: Two-player mechanic — "[Player A] and [Player B], each confess one thing you've judged the other for." Not a single-speaker topic.
- 6086 [Party]: Yes/no form — "do you have a secret social media account/finsta?" Doesn't normalize as a noun-phrase topic.
- 6127 [Spicy]: Yes/no form — "do you have a secret attraction to anyone in this room?" Same issue.
- 6135 [Spicy]: Compound question — "who is the hardest person you've ever had to get over, and what made it so bad?" Two-part; loses meaning stripped to one.
- 6145 [Party, Silly]: Compound question — "what is the most embarrassing nickname you've ever had and how did you get it?" Two-part.
- 6150 [Party, Spicy]: Compound question — "the most uncomfortable compliment you've received and who it was from." Two-part.
- 6175 [Spicy]: Yes/no + describe form — "is there someone you would have dated but never admitted it to? Tell the group who or describe them."
- 6220 [Spicy]: Yes/no form — "is there someone from a past relationship you still quietly check up on?"
- 6243 [Party, Couples]: Two-player mechanic — "[Player A] and [Player B], each confess one thing you genuinely appreciate about the other." Not a single-speaker topic.
- 6246 [Spicy]: "something you've done with someone in this room that no one else here knows about" — the "in this room" specificity is the entire social tension. Stripping it to "something you've done with someone no one knows about" loses the charge. Could strip and add to confession_prompts_spicy, but might lose what makes it work. Surfaced for Grant.
- 6251 [Spicy]: Has a built-in penalty mechanic — "name the first three people you've slept with and [Penalty,1] for each you regret." The penalty logic is baked into the prompt text, not delegable to the shell system.
- 6258 [Spicy]: "who in this room do you think is the best in bed?" — "in this room" specificity is the full mechanic. Same dynamic as 6246.

## chain_framings multi-consumer grammar conflict (Big Commands build, 2026-07-09)

**Finding:** `chain_framings` gained two new consumers beyond `point_chain.v1` (sequential "point at someone, they take X, then point at someone else" framing): `repeat_point.v1` (same sequential framing) and `group_blast.v1` ("Everyone takes [Penalty, 1]. No reason." -- a whole-group, no-targeting framing). These are structurally incompatible entry requirements: sequential-chain entries can safely imply a moving target ("Somebody had to be next"), but group_blast entries must read as true for the ENTIRE group simultaneously, not a single link in a chain.

**Ruling:** New `chain_framings` entries must pass BOTH grammars: (1) trailing tag after a sequential point-chain resolution, AND (2) trailing tag after "Everyone takes [Penalty, 1]. No reason." Entries that imply a single target or a moving/sequential mechanic ("Somebody had to be next", "What goes around finds a new target") are excluded going forward -- replaced with genuinely universal inevitability lines ("Nobody gets to opt out of this one.", "Fair is a strong word.") that read true whether one person or the whole group is affected.

**Flag for Grant:** two PRE-EXISTING entries were not touched under this ruling (out of scope for a same-day expansion pass) but likely fail the group_blast grammar test: "One bad decision, two victims." (explicitly implies exactly 2 people, contradicts "everyone") and possibly "The chain does not forget." (implies a chain mechanic group_blast doesn't have). Recommend Grant/shell-agent review these two against the group_blast render before they ship to players.

**Precedent for future multi-consumer pool expansions:** before authoring new entries into a pool, check ALL current shell consumers (not just the one named in a brief), and test new content against the most restrictive grammar among them.
