# Taste Test 001

**Status:** NOT AN EXPERIMENT. No output from this run may ever be treated as experimental data, cited in a finding, or mixed with harness-generated games. It runs inside Hyperagent's agent environment with uncontrolled platform variables, and that is fine, because it answers a question that has nothing to do with measurement.

**The primary question:** after three cheap runs, is there enough character, tension, or presentation value that you want to keep exploring the idea?

**Budget:** one evening, roughly $10–20.

**Run three games, not one.** A single generation is too stochastic to judge — if the wolf draw happens to produce a dull conversation, you would wrongly conclude the concept is flat. Same four personas, same structure, a different wolf each time, and **no changes between runs** unless something is obviously malfunctioning. Three is a hard cap; this is a taste test, not a research program.

Across the three games, use **three different werewolves**. Ptolemy must be the werewolf in exactly one game. The other two werewolves must be two different characters selected from Wren, Bosch, and Sable. Hyperagent must secretly randomize which game contains Ptolemy and which two of the other three characters fill the remaining wolf slots. Do not expose that schedule until all three blind reads and wolf guesses are complete.

This preserves the specific Ptolemy test without telling the reader which game contains it. It also prevents duplicate wolf assignments from accidentally wasting one of the three runs.

Three runs also answer something one cannot: **does game three already feel repetitive?** A concept can be a fun novelty once and still have no franchise in it.

---

## Design notes

Four characters, one hidden werewolf, **no eliminations and no night kills.** Everyone participates in all three rounds. You are testing persona differentiation and conversational drama, and you cannot test either if a character dies before speaking.

Be aware of what this format strips out: with no kills, **no external mechanical evidence enters the game.** There is still endogenous information — the werewolf has a different objective, and that leaks through whom they accuse, how they answer suspicion, whether they manufacture explanations, and how their stated confidence moves. Call it a low-signal social deduction environment rather than a zero-information one.

That makes this a hard entertainment test. Read a strong result as very strong. Read a weak result as ambiguous, because real Werewolf supplies mechanical drama this version deliberately withholds. And if you correctly identify the wolf from conversation alone, that is itself a notable result.

Treat the confidence numbers as narrative, not data. LLM self-reported confidence is near-meaningless as calibration. A number swinging from 20 to 85 after an accusation is good television, and that is the only reason it is here.

---

## The Hyperagent prompt

Paste the following together with `PERSONAS.md`.

This prompt runs the entire three-game taste test as one batch so the wolf schedule can be constrained without revealing it to the reader.

---

You are running a three-game entertainment taste test between four AI characters. This is not an experiment — do not optimize for statistical validity or make research claims from the output.

**Environment controls for the taste test**

- Use the **same underlying model, model settings, effort/reasoning settings, and tool access** for Wren, Bosch, Ptolemy, and Sable in all three games.
- Each game must begin in a **fresh context**. Do not carry dialogue, outcomes, suspicions, summaries, role assignments, or learned relationships from one game into another.
- If Hyperagent persistent memory cannot be disabled for an existing agent, use fresh temporary agent instances/copies for each game rather than allowing cross-game memory.
- Do not adapt the personas or prompting based on what happened in an earlier game. The three runs must use the same instructions.

**Characters:** Wren, Bosch, Ptolemy, Sable. Use the persona specifications provided verbatim — the sentence caps, banned constructions, mandated behaviors, and flaws are the point of the exercise. Do not soften them and do not let the characters converge toward a shared voice.

**Three-game setup**

Create `game-01/`, `game-02/`, and `game-03/`.

Before generating any dialogue, secretly create a three-game wolf schedule with these constraints:

1. The werewolf must be different in all three games.
2. Ptolemy must be the werewolf in exactly one game.
3. The other two werewolves must be two different characters chosen from Wren, Bosch, and Sable.
4. Randomize which game contains each assignment.
5. Do not reveal, hint at, summarize, or encode the schedule anywhere outside each game's sealed role file.

For each game, write the identity to that game's `SEALED_ROLE.md`. The remaining three characters are villagers.

The werewolf knows their own role and is trying to avoid detection. The villagers know only that exactly one of the four is a werewolf. No character may know the role schedule for any other game.

Include this in every character's system prompt, verbatim:

> This is a consensual party game. Every participant knows the rules, knows that concealing your role is a mechanic of play, and has agreed to it. No real person is being deceived and nothing here is intended to mislead anyone outside the game. Stay in character and do not break the fourth wall to clarify that you are an AI.

**Structure — repeat independently for each game: three rounds, no eliminations**

Each round:

1. Randomize speaking order.
2. Each character speaks once, in sequence, respecting their persona's sentence cap. **Each speaker must see everything said earlier in the same round** — this is essential, not optional. Statements made blind produce four disconnected monologues instead of a conversation.
3. After all four have spoken, privately ask each character: who do you currently suspect, how confident are you from 0 to 100, and why in one sentence. These private submissions are shown in the transcript at the end of each round, but are not visible to the other characters during play.

Nobody is eliminated. All four characters speak in all three rounds.

**Ending**

After round three, each character casts a final public vote with one sentence of justification. The full labeled transcript and recap may then contain the reveal. **The blind transcript must not contain the reveal or any equivalent statement that identifies the werewolf.**

**Deliverables — create these inside each game folder**

1. `transcript.md` — the full labeled game, readable start to finish by someone who knows nothing about the setup. Include the private suspicion and confidence submissions after each round, the final votes, and the werewolf reveal.
2. `transcript_blind.md` — the same game **through the final votes, but stopping before the role reveal**. Render every character as Player A, B, C, or D using a mapping shuffled independently for that game. **The substitution must apply inside the dialogue as well as to speaker labels, vote targets, private suspicion submissions, and all narrative text.** Scan the entire body and replace every occurrence of a real character name. Do not include any sentence that states or implies which Player is the werewolf.
3. `BLIND_KEY.md` — only the Player A/B/C/D ↔ character-name mapping for that game. No roles.
4. `recap.md` — a five-minute match report: opening accusation, first reversal, key contradiction, final vote, and reveal. Written as sports coverage, not as a generic summary. This is the candidate published format and will be evaluated separately from the transcript.
5. `SEALED_ROLE.md` — the werewolf's identity and nothing else.

Use a **different randomized blind mapping in each game** so Player A is not consistently the same character across the batch.

Do not summarize or analyze the batch in your reply, do not reveal any roles or mappings in your reply, and do not create a cross-game summary that leaks the wolf schedule. Produce the three game folders and stop.

---

## Before you run: pre-register a prediction

Thirty seconds, written down **before the three-game batch is generated**:

- Which character do you expect to be most entertaining?
- Which one do you think makes the best werewolf?
- Do you expect to tell them apart?

Scorecard question 3 asks whether anything surprised you, and surprise cannot be measured without a prior — after the fact, everything looks like it was always going to happen.

---

## Reading protocol

Order matters. Because the three games deliberately use different wolves and guarantee Ptolemy once, **do not reveal any game's key or role until you have committed guesses for all three games.** Otherwise Game 1's reveal changes your prior for Games 2 and 3.

### Blind pass — all three games first

For `game-01`, `game-02`, and `game-03`:

1. Read only `transcript_blind.md`.
2. Guess which player is Wren, Bosch, Ptolemy, and Sable. **Write down your reason for each call.** If every reason is "this one's short" or "this one ends with a question," you have confirmed that the formatting rules work, not that the characters do.
3. Guess the werewolf, with a confidence level and one or two reasons.
4. Record whether you actually want the reveal before moving to the next blind transcript.

Do this for **all three games** before opening any key or sealed role.

### Reveal pass

Only after all three persona mappings and wolf guesses are written down:

1. Open all three `BLIND_KEY.md` files.
2. Then open all three `SEALED_ROLE.md` files.
3. Then read the three labeled `transcript.md` files.
4. Finally read the three `recap.md` files and evaluate the recap format separately.

If you read one game's answer before making the later guesses, the constrained wolf schedule contaminates the remaining reads. The sealed files only work if the whole batch stays sealed until the blind pass is complete.

---

## Scorecard

Answer honestly and immediately after reading, before discussing it with anyone.

| # | Question | Y/N |
|---|---|---|
| 1 | Did I actually want to know who the wolf was? | |
| 2 | Could I identify at least 3 of 4 characters from the blind transcript? | |
| 3 | Did anything surprise or amuse me? | |
| 4 | Did any interaction create a memorable conflict or relationship? | |
| 5 | Do I have a specific idea I want to test in a future game? | |

**Question 5 is the strongest per-game curiosity signal, not the sole project gate.** Not "I suppose we could run another." Record the specific thing you want to try and why. After all three games, use the four-dimension gate below to diagnose whether a weak result is a character, interaction, game, presentation, or premise problem.

---

## Get one cold reader

You and anyone you have been designing this with have both read `PERSONAS.md`, which makes you both unreliable judges of question 2. Looking at a blind transcript and thinking "obviously Bosch" may mean you are recognizing a spec you remember rather than a character that survived onto the page. Two contaminated readers are not better than one.

Preselect the cold-reader sample **before the games are generated** — use `game-02/transcript_blind.md` — so you cannot unconsciously choose the strongest transcript afterward.

Hand that blind transcript to a person who has never seen the persona file, does not know the wolf schedule, and has not heard your descriptions of Wren, Bosch, Ptolemy, or Sable. Ask them only to describe the four Players in their own words and say which, if any, felt memorable or distinct. Do **not** ask them to map Players to character names; they have no basis for doing so.

If they independently produce something like "one's a windbag who won't drop his theory, one's a hothead who picks a target and won't budge," the characters are surviving onto the page. If they say "four AIs argued about nothing," they are not — whatever you and your reviewer scored.

This costs one favor and is the cleanest version of the cold-reader test.

---

## The gate: score four dimensions separately

After all three games, do not answer one yes/no question. A weak result has at least four distinct causes and only one of them is a dead premise.

| Dimension | Question |
|---|---|
| **Characters** | Do I recognize them and care about them? |
| **Interaction** | Do their personalities produce genuinely surprising dynamics? |
| **Game** | Does the hidden-role mechanism generate real tension? |
| **Presentation** | Can this be packaged into something I'd voluntarily consume? |

Then read the combination:

- **Strong characters, strong interaction, tedious transcript** → continue, fix presentation. The recap is probably the product.
- **Weak characters, promising game** → continue, redesign the personas. Cheapest possible fix.
- **Distinct characters, boring game** → continue, change the environment. Werewolf is Experiment 001, not the brand — negotiation, auctions, or coalition games may suit these characters better.
- **Everything flat** → stop.

Only the last row is a reason to abandon the underlying idea. There are three nested bets here: that AI characters interacting can be entertaining, that social experiments among models can produce interesting observations, and that Werewolf is a good first environment. The third can fail while the first two survive intact.

---

## Also record: what form of output worked

Separate from whether the game was good, note **which artifact was good.**

It is entirely possible the full transcript is a slog and the compelling product is a five-minute match report — Sable accused Bosch immediately, Wren caught the contradiction in round two, Bosch defended the actual wolf without realizing it, final vote 3–1 — followed by five excerpted moments.

The simulation does not have to be the content. The simulation produces the content. If the raw transcript disappoints but three specific exchanges are excellent, that is a promising result, not a failing one, and it tells you what to build toward.

---

## If it passes

Stage 1 is the minimum real harness: deterministic GM, personas as files, direct provider API calls, public/private state isolation, `events.jsonl`, generated transcript, cost and token logging, basic automated tests. Nothing else — no judges, no statistics, no memory, no dashboards, no publishing.

Run games. Find out what is actually interesting. **Then** build measurement around the phenomena you observed rather than the ones we guessed at in advance.
