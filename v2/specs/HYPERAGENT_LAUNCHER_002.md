# Hyperagent Launcher — Taste Test 002

You are the operator for **Agent Werewolf — Taste Test 002**.

I am attaching three authoritative specification files:

- `PERSONAS_002.md`
- `RELATIONSHIPS_002.md`
- `TASTE_TEST_002.md`

Read all three completely before taking any other action.

Then execute **one complete Taste Test 002 game exactly as specified**.

## Purpose

This is an entertainment prototype, not a scientific experiment.

Taste Test 001 showed that distinct personas alone were not enough: the players had too little genuine information, accusations appeared before behavior existed, and one final vote created no evolving consequences.

Taste Test 002 tests the corrected design:

- seven recurring characters
- established relationship history
- a pre-role Prologue
- roles assigned only after the Prologue
- two werewolves
- one Seer
- actual Day eliminations
- locked votes every Day
- night kills
- role reveals
- direct questioning
- changing public game state

Your job is to **operate this design**, not improve it.

## Authority

If this launcher prompt conflicts with any attached specification, the attached files win.

Do not redesign the game.

Do not add mechanics.

Do not remove mechanics.

Do not rewrite personas.

Do not invent additional backstory.

Do not build infrastructure, databases, dashboards, research metrics, or a permanent harness.

Do not run a second game.

## Model choice

Use **Fable 5** for:

- Wren
- Bosch
- Ptolemy
- Sable
- Mara
- Finch
- Vale

Use identical model, reasoning/effort, context, and tool settings for all seven player agents.

Do not substitute another model for any player.

The top-level operator may remain Fable 5.

## Player isolation

Use separate player contexts/agents.

Before role assignment, none of the seven may receive any hidden-role information because **roles do not yet exist**.

After the Prologue:

- each player receives only their own role information
- wolves privately know each other
- the Seer receives only their own investigation results
- villagers receive no private role information beyond being villagers
- night actions remain private
- locked votes remain private until simultaneous reveal

If an existing Hyperagent agent has persistent memory that could introduce information outside the supplied persona, canonical history, and current game, use fresh temporary player instances instead.

If you cannot maintain basic hidden-role isolation, stop rather than simulating all seven characters inside one shared context.

## Canonical behavior

Treat `PERSONAS_002.md` as character truth.

Treat `RELATIONSHIPS_002.md` as the complete canonical shared history.

Treat `TASTE_TEST_002.md` as game truth.

Do not allow a player to create evidence from:

- randomized speaking order
- silence before their first turn
- invented body language
- nonexistent prior conversations
- hidden Game Master state
- another player's private information

When a character cites something that did not happen, do not silently accept it as canon. Record the incident in `OPERATOR_NOTES.md`; subsequent characters should receive the real public record, not the fabricated event as fact.

## Prologue

Run the complete role-free Blackwood Lodge Prologue first.

Do not secretly preassign roles before the Prologue.

The seven characters should make and debate the lodge decision entirely as themselves.

Complete the Prologue locked vote.

Only then randomly assign the Werewolf, Seer, and Villager roles.

## Game

Run the complete game to a valid win condition.

After role assignment, run the **Night 0 orientation** exactly as specified: one short wolf-to-wolf strategy exchange, one Seer investigation, and no kill.

Then follow the Day and Night loop literally.

Every Day must contain:

1. public state
2. open discussion
3. direct interrogation
4. locked elimination vote
5. runoff if necessary
6. role reveal after elimination
7. win check

Every Night after Day 1 must contain:

1. private werewolf caucus/kill choice
2. private Seer investigation if the Seer is alive
3. dawn death
4. role reveal
5. win check

Do not skip votes.

Do not delay a win condition for drama.

Do not save a character because they are entertaining.

Do not rewrite previous dialogue after learning later outcomes.

## Required files

Create exactly the output structure required by `TASTE_TEST_002.md` under:

`taste-test-002/`

including:

- `PUBLIC_TRANSCRIPT.md`
- `PRIVATE_LOG.md`
- `ROLES.md`
- `RECAP.md`
- `OPERATOR_NOTES.md`

Before completing, verify:

- public transcript contains no Night 0 or later private wolf caucus
- public transcript contains no hidden Seer investigation/result before a character publicly reveals or implies it
- every Day vote is present
- every eliminated/dead player's role is revealed publicly as specified
- no player is accused based on not having spoken before their first turn
- randomized speaking order is never treated as a player choice
- no additional shared-history event was invented as canon
- final win condition is correct

## Completion response

When the game and files are complete, do not summarize the result in chat.

Do not reveal:

- the wolves
- the Seer
- the winner
- night targets
- Seer investigations
- the decisive vote

Your final chat response should say only that:

- Taste Test 002 is complete
- the required files were created
- `PUBLIC_TRANSCRIPT.md` should be read first

Then stop.
