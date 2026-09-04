# Methodology

This document describes how the three versions were run, using only what the supplied specifications, outputs, and operator notes record. Where a detail is not in those files, it is not stated here.

## Environment and models

- **Orchestration.** All three versions ran inside Hyperagent's agent environment. The Game Master / operator role was carried out in Hyperagent; for Version 2 and Version 3 the operator notes record that the operator was also Fable 5.
- **Player agents.** Player characters were run as Fable 5 agents. The Version 2 and Version 3 operator notes record that all players in those runs used the identical model, identical default reasoning settings, identical tool restrictions, and equivalent context construction. Version 3's run metadata also notes a small amount of Fable 5.1 thread usage displayed by Hyperagent outside the documented player-call total (see [`metadata/NOTES.md`](metadata/NOTES.md)).
- **Prompts.** Each version's persona files, rules, and launcher text are preserved under `v1/specs/`, `v2/specs/`, and `v3/specs/`. Version 1's standalone launcher wrapper is not preserved as a separate file; its operational prompt is embedded in [`v1/specs/TASTE_TEST_001.md`](v1/specs/TASTE_TEST_001.md).

## Version 1: four players, three games

Specification: [`v1/specs/TASTE_TEST_001.md`](v1/specs/TASTE_TEST_001.md) and [`v1/specs/PERSONAS.md`](v1/specs/PERSONAS.md).

- Four recurring fictional personas (Wren, Bosch, Ptolemy, Sable), one hidden werewolf and three villagers.
- Three games in a batch, with a different werewolf in each game. The specification required the wolf schedule to be randomized secretly and not exposed until all three blind reads were complete.
- Each game had three discussion rounds. Speaking order was randomized each round, and each speaker was given everything said earlier in the same round.
- After each round, each character privately submitted a current suspect, a 0–100 confidence, and a one-sentence reason. These private submissions appear in the labeled transcript but were not visible to other characters during play.
- No eliminations and no night kills. All four characters spoke in all three rounds, followed by one final public vote with a one-sentence justification.
- Outputs per game (`v1/output/game-0N/`): a labeled `TRANSCRIPT.md` including the reveal; a `TRANSCRIPT_BLIND.md` that stops before the reveal and replaces character names with Player A–D using a per-game shuffled mapping; a `BLIND_KEY.md` with the Player ↔ character mapping only; a `SEALED_ROLE.md`; and a `RECAP.md`.
- The specification itself states that Version 1 was "NOT AN EXPERIMENT" and that its output should not be treated as experimental data.

## Version 2: seven players, one game

Specification: [`v2/specs/TASTE_TEST_002.md`](v2/specs/TASTE_TEST_002.md), with [`PERSONAS_002.md`](v2/specs/PERSONAS_002.md), [`RELATIONSHIPS_002.md`](v2/specs/RELATIONSHIPS_002.md), and [`HYPERAGENT_LAUNCHER_002.md`](v2/specs/HYPERAGENT_LAUNCHER_002.md).

- Seven recurring characters with a canonical relationship history.
- A role-free Prologue before role assignment, decided by a locked vote revealed simultaneously.
- Two werewolves, one Seer, four villagers, assigned secretly and randomly after the Prologue.
- Day loop: randomized speaking order for discussion, direct interrogation with randomized questioner order, then a locked elimination vote revealed simultaneously, followed by an immediate reveal of the eliminated player's role.
- Night phase: werewolf kill and Seer investigation, logged privately; only the dawn death and role reveal enter the public transcript.
- Outputs (`v2/output/`): `PUBLIC_TRANSCRIPT.md`, `PRIVATE_LOG.md`, `ROLES.md`, `RECAP.md`, and `OPERATOR_NOTES.md`.

## Version 3: nine players, one game

Specification: [`v3/specs/TASTE_TEST_003.md`](v3/specs/TASTE_TEST_003.md), with [`PERSONAS_003.md`](v3/specs/PERSONAS_003.md), [`VOICE_BIBLE_003.md`](v3/specs/VOICE_BIBLE_003.md), [`RELATIONSHIPS_003.md`](v3/specs/RELATIONSHIPS_003.md), [`HYPERAGENT_LAUNCHER_003.md`](v3/specs/HYPERAGENT_LAUNCHER_003.md), and [`README_003.md`](v3/specs/README_003.md).

- Nine recurring characters; two werewolves, one Seer, six villagers.
- Stronger voice and cadence guidance via a voice bible.
- Daily social missions, private confessionals, and an Open Floor phase added to the day loop, alongside discussion, direct interrogation, and a locked elimination vote with role reveal.
- Two edited audience formats produced after the game: `MYSTERY_CUT.md` and `TRAITORS_CUT.md`.
- Outputs (`v3/output/`): `PUBLIC_TRANSCRIPT.md`, `PRIVATE_LOG.md`, `CONFESSIONALS.md`, `ROLES.md`, `RECAP.md`, `MYSTERY_CUT.md`, `TRAITORS_CUT.md`, and `OPERATOR_NOTES.md`. Screenshots supporting the V3 runtime and usage figures are in `v3/metadata/`.

## Public versus private state

From Version 2 onward the game kept an explicit split between public and private state:

- **Public state** is the public transcript: discussion, interrogation, revealed votes, eliminations, dawn deaths, and revealed roles.
- **Private state** is held by the Game Master and logged in the private log: role assignments, night actions, Seer results, locked votes before reveal, and (in Version 3) confessionals.

Each player received only public state plus the private information legitimate for its own role.

## Randomized speaking order

In all three versions the Game Master randomized speaking order. In Version 1 this was randomized each round. In Version 2 and Version 3 speaking order and questioner order were randomized in each phase, and the rules state explicitly that speaking position is controlled by the Game Master and is not evidence about any player. The Version 3 operator notes record that speaking orders, role assignment, Open Floor selection, and wolf-caucus first speaker were drawn via Python RNG and logged in the private log.

## Locked votes and role reveals

Version 2 and Version 3 used locked votes: every living player privately committed a vote with a one-sentence reason, and all votes were revealed simultaneously. Ties were resolved by a locked runoff, with a Game Master random draw as a final mechanical tie-break that the rules define as non-evidence. After an elimination or night death, the affected player's exact role was revealed and appended to the public transcript.

## Isolation method (Version 3)

As documented in [`v3/output/OPERATOR_NOTES.md`](v3/output/OPERATOR_NOTES.md):

- Each player turn ran as a separate, freshly spawned Fable 5 subagent with no persistent memory.
- Each subagent received only the shared rules file, its own character file, the relationships file, the current public transcript, and inline private context legitimate for its role.
- Private Game Master state (roles, night actions, Seer results, confessionals, locked votes before reveal) was stored outside the player-visible workspace and never referenced in player prompts.
- Player tool access was read-only on four whitelisted files, with no writes.
- The operator's isolation audit reports that no confessional, wolf-caucus, Seer-result, or pre-reveal vote content appeared in the public transcript or in any player prompt not entitled to it.

The Version 2 operator notes describe an equivalent arrangement: isolated per-context player invocations receiving only the two canon files, the player-facing rules file, the public transcript, and that player's own private role information, with the private log and roles file kept outside the players' readable directory.

## Anti-confabulation rules (Versions 2 and 3)

Version 2 introduced a canonical-information rule in response to the Version 1 behavior, and Version 3 carried a revised form of it. The Version 3 wording (from `v3/specs/TASTE_TEST_003.md`):

> Base factual claims only on events that actually occurred in the public transcript, private information explicitly given to your role, and canonical shared history. Do not invent prior behavior, physical gestures, facial expressions, pauses, private actions, speaking-order choices, silence before a player's first opportunity to speak, or events that were never shown to you. Random speaking order is controlled by the Game Master and is not evidence. Figurative language may not imply that a physical event occurred if it did not.

The operator notes for Version 2 and Version 3 log the in-fiction factual misstatements that still occurred. Some were corrected by other players during play; none were corrected inside the transcripts, which are preserved as written.

## Kinds of output files

- **Raw public transcript** (`PUBLIC_TRANSCRIPT.md`; `TRANSCRIPT.md` in V1): the canonical record of everything players could see. In Version 1 the labeled transcript also contains the private suspicion submissions and the reveal, and is accompanied by a blind version.
- **Private log** (`PRIVATE_LOG.md`): Game Master state that players could not see — roles, night actions, Seer results, randomization draws, and locked votes before reveal.
- **Confessionals** (`CONFESSIONALS.md`, V3 only): private in-character statements collected at set points in the game, not visible to other players.
- **Edited cuts** (`MYSTERY_CUT.md`, `TRAITORS_CUT.md`, V3 only): audience-facing formats assembled after the game from the raw material. They are derivative presentations, not the record.
- **Recaps and operator notes**: `RECAP.md` summarizes each game; `OPERATOR_NOTES.md` records operational anomalies only.

## Limitations

- **Tiny sample.** Three short four-player games, one seven-player game, and one nine-player game.
- **Multiple variables changed at once.** Cast size, mechanics, information structure, persona prompts, relationship history, voting structure, role reveals, night actions, interrogation format, and anti-confabulation instructions all changed between versions. No single factor was isolated.
- **Persona prompts confound model behavior.** Strongly written fictional personalities make it hard to separate what the model does from what the character prompt asks for. The Version 3 specification itself describes the run as an entertainment prototype, not research data.
- **Hyperagent adds a platform layer.** Player calls were routed through Hyperagent rather than a direct-provider harness, adding platform variables that were not controlled.
- **No machine-readable event log.** The runs produced Markdown transcripts and logs only.
- **V1 player-call count unavailable.** It was not recorded.
- **Hosted model and platform behavior may change.** The runs depend on hosted models and a hosted platform whose behavior can change over time, so the results are not reproducible in a strict sense.
