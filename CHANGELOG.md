# Changelog

This file summarizes what changed between the three versions, based on [`VERSION_SUMMARY.md`](VERSION_SUMMARY.md). It is a record of the build, not an ablation. Each step changed many variables at once, so no single change can be credited with any difference observed between versions.

## Version 1 → Version 2

Version 1 was a four-player, three-game batch: four recurring fictional personas, one werewolf and three villagers, three discussion rounds, no elimination during play, no night kills, and one final vote per game. Its main observed failure was that agents repeatedly treated nonexistent behavior or randomized speaking order as player evidence.

Version 2 changed the following together:

- Cast grew from four to seven recurring characters.
- A canonical relationship history was added.
- A role-free Prologue was added before role assignment.
- Role distribution changed from one werewolf / three villagers to two werewolves, one Seer, and four villagers.
- Daily elimination votes were added (Version 1 had none during play).
- Night kills were added.
- Role reveals were added.
- Direct interrogation was added.
- Batch size changed from three games to one complete game.

## Version 2 → Version 3

Version 3 changed the following together:

- Cast grew from seven to nine recurring characters.
- Role distribution changed to two werewolves, one Seer, and six villagers.
- Stronger voice/cadence guidance was added.
- Social missions were added.
- Private confessionals were added.
- An Open Floor phase was added.
- Two edited audience formats were added: a Mystery Cut and a Traitors Cut.
- One complete game was run.

The stated tradeoff for Version 3 was stronger entertainment value against a much larger runtime and output volume, and greater confounding between persona prompts and model behavior.

## What this changelog does not show

Because the cast size, mechanics, information structure, persona prompts, and instructions changed simultaneously at each step, the project did not isolate any one factor. Differences between versions should be read as observations about the build as a whole. See [`METHODOLOGY.md`](METHODOLOGY.md) for limitations.
