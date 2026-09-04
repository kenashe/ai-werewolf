# AI Werewolf

## What this is

An iterative multi-agent Werewolf prototype built through Hyperagent. Player agents ran on Fable 5. This repository preserves three versions of the project: the prompts and rules for each version, the raw game transcripts, the hidden-state logs (roles, night actions, Seer results, private votes, confessionals), the operator notes, and the run metadata.

This is an artifact repository, not a standalone game engine. It preserves the prompts, rules, transcripts, hidden state, and run metadata from games orchestrated through Hyperagent.

Nothing under `v1/`, `v2/`, or `v3/` has been edited. Factual errors made by agents during play are preserved as written.

## Main observation

In Version 1, all three games contained at least one case where an agent treated nonexistent behavior, or the Game Master's randomized speaking order, as evidence about another player — for example, accusing a player of suspicious silence before that player had been given a turn to speak.

In the later versions, more of the agents' reasoning attached to observable game state, and factual errors could be challenged against a canonical public transcript by other players. Errors still occurred; the difference is that they could be contested.

This is an observation from a small build, not a causal or scientific claim.

## What this is not

- Not a controlled benchmark.
- Not proof that any one intervention caused the change in behavior.
- Multiple variables changed between versions at the same time (cast size, mechanics, information structure, persona prompts, instructions). See [`CHANGELOG.md`](CHANGELOG.md) and the limitations in [`METHODOLOGY.md`](METHODOLOGY.md).

## Version summary

Based on [`VERSION_SUMMARY.md`](VERSION_SUMMARY.md).

| | Version 1 | Version 2 | Version 3 |
|---|---|---|---|
| Characters | 4 recurring personas | 7 recurring characters | 9 recurring characters |
| Roles | 1 werewolf, 3 villagers | 2 werewolves, 1 Seer, 4 villagers | 2 werewolves, 1 Seer, 6 villagers |
| Structure | 3 discussion rounds, one final vote | Role-free Prologue, daily elimination votes, night kills, role reveals, direct interrogation | As V2 plus social missions, private confessionals, Open Floor |
| Eliminations during play | None | Yes | Yes |
| Additional material | — | Canonical relationship history | Stronger voice/cadence guidance; Mystery Cut and Traitors Cut |
| Games | 3 | 1 complete game | 1 complete game |
| Noted result | Agents repeatedly treated nonexistent behavior or randomized speaking order as evidence | — | Stronger entertainment value; much larger runtime/output; greater persona/model confounding |

## Start here

- [`evidence/01-v1-silence-before-turn.md`](evidence/01-v1-silence-before-turn.md) — V1 agents accusing players of silence before those players had a turn.
- [`evidence/04-v3-transcript-correction.md`](evidence/04-v3-transcript-correction.md) — a V3 factual claim checked and corrected against the public transcript.
- [`evidence/05-v3-grounded-wolf-strategy.md`](evidence/05-v3-grounded-wolf-strategy.md) — V3 wolves choosing a night target based on observable public behavior.
- [`v3/output/OPERATOR_NOTES.md`](v3/output/OPERATOR_NOTES.md) — V3 isolation method, model parity, and logged anomalies.
- [`docs/ESSAY_DRAFT.md`](docs/ESSAY_DRAFT.md) — draft essay about the project.

## Usage note

Dollar figures in this repository are Hyperagent-reported metered usage and were covered by existing Hyperagent credits. They are not out-of-pocket cost, and they should not be used to infer per-token prices. See [`RUNS.md`](RUNS.md).

## Repository map

| Path | Contents |
|---|---|
| [`README.md`](README.md) | This file. |
| [`METHODOLOGY.md`](METHODOLOGY.md) | How each version was set up and run, and the limitations. |
| [`RUNS.md`](RUNS.md) | Run table: games, runtime, player calls, tokens, metered usage. |
| [`CHANGELOG.md`](CHANGELOG.md) | What changed from V1 to V2 to V3. |
| [`SOURCE_MANIFEST.md`](SOURCE_MANIFEST.md) | Description of the source bundle and its known gaps. |
| [`VERSION_SUMMARY.md`](VERSION_SUMMARY.md) | Compact per-version facts. |
| [`MANIFEST.sha256`](MANIFEST.sha256) | SHA-256 hashes of every file under `v1/`, `v2/`, `v3/`, `metadata/`, and `evidence/`. |
| `docs/` | The essay draft. |
| `evidence/` | Five short, source-linked excerpts from the raw transcripts and private logs. |
| `metadata/` | Structured run summary (`run-summary.csv`) and owner notes on how the figures were recorded. |
| `v1/` | Version 1 specs (personas, Taste Test 001) and complete output for three games: labeled and blind transcripts, blind keys, sealed roles, recaps. |
| `v2/` | Version 2 specs (personas, relationships, rules, launcher) and output: public transcript, private log, roles, recap, operator notes. |
| `v3/` | Version 3 specs (personas, voice bible, relationships, rules, launcher, instructions), output (public transcript, private log, confessionals, roles, recap, Mystery Cut, Traitors Cut, operator notes), and usage/runtime screenshots. |

## Known gaps

- Version 1's standalone launcher wrapper is not preserved as a separate file; the operational prompt is embedded in `v1/specs/TASTE_TEST_001.md`.
- No machine-readable event log was produced.
- The V1 player-call count was not recorded.
- V1 and V2 usage figures are approximate owner records; only V3 has screenshots.
