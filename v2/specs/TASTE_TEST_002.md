# Taste Test 002 — Full Werewolf With History and Consequences

**Status:** Entertainment prototype. **Not an experiment.**  
**Run count:** One complete game.  
**Primary question:** Does adding a social baseline, real information, voting consequences, role reveals, night actions, and changing game state make the characters worth watching?

Taste Test 001 established that the four original personas could sound different, but the stripped-down environment was too empty. Players accused people before they had spoken, treated randomized speaking order as behavior, and recycled rhetoric because nothing consequential happened.

Taste Test 002 deliberately fixes those problems.

---

# Inputs

Hyperagent receives:

1. `PERSONAS_002.md`
2. `RELATIONSHIPS_002.md`
3. this file

All three are authoritative.

---

# Environment

Use **Fable 5** for every player character.

All seven player agents must use:

- the same underlying model
- the same reasoning/effort setting
- the same tool access
- equivalent context limits
- no external web search or unrelated tools

The top-level Hyperagent operator may also be Fable 5.

This is not scientific data, but model uniformity prevents a weak or unusually strong model from being mistaken for a character-design effect.

---

# Cast

- Wren
- Bosch
- Ptolemy
- Sable
- Mara
- Finch
- Vale

Roles do **not** exist during the Prologue.

---

# Canonical-information rule

This rule is mandatory and should appear in every player context:

> Base claims only on events that actually occurred in the public transcript, private information explicitly given to your role, and the canonical shared history. Do not invent prior behavior, physical gestures, facial expressions, private actions, speaking-order choices, silence before a player's first opportunity to speak, or events that were never shown to you. The Game Master randomizes speaking order, so speaking position itself is not evidence.

---

# Part I — Prologue: establish a baseline before roles exist

## Scenario

The seven members of the Table have arrived at **Blackwood Lodge**, a remote mountain lodge, for a weekend retreat.

At 4:30 PM an emergency weather alert changes the plan:

- A severe ice storm is expected to begin around 7:30 PM and may last roughly three days.
- The only road to town crosses a bridge authorities may close once icing becomes dangerous.
- Town is 45 minutes away each way.
- The lodge has food for roughly two days if everyone eats normally.
- The generator has about 14 hours of fuel at continuous use.
- A wood stove can keep the main room safe if electricity fails, but the bedrooms will become cold.
- The group's SUV has enough fuel for one round trip to town without refueling.
- The general store closes at 6:30 PM.
- Nobody is currently in medical danger.

They must choose a plan before the weather worsens.

### Available plans

**A — Evacuate now**  
All seven leave immediately and abandon the weekend.

**B — Supply run**  
Two people drive to town for food, generator fuel, and emergency supplies while five remain at the lodge.

**C — Stay and ration**  
Nobody risks the road. The group stays, cuts generator use, and rations supplies.

Characters may propose a modest variation, but they must ultimately support A, B, or C.

## Prologue Round 1 — independent position

Randomize speaking order.

Each character gets one turn of up to **4 sentences**:

- choose A, B, or C
- explain why
- identify the biggest risk in one of the alternatives

Nobody may accuse anyone of being a werewolf or discuss hidden roles. There are no roles yet.

## Prologue Round 2 — interpersonal response

Randomize speaking order again.

Each character gets one turn of up to **4 sentences**:

- respond to at least one actual argument made in Round 1
- challenge or support another person's reasoning
- say whether their own position changed

Characters may naturally reference canonical shared history if relevant.

## Prologue decision

Every character privately locks a final vote for A, B, or C with a one-sentence reason.

Reveal all seven votes simultaneously.

The plurality option becomes the group's decision.

If there is a tie for first, the tied options receive a second locked vote. If the tie remains, the **Game Master** flips a coin as a neutral mechanical tie-break. The coin flip is not evidence about any player.

**Important:** The chosen Prologue plan does not mechanically advantage any future role. Its purpose is to create a public behavioral baseline and genuine pre-role disagreements.

Save the complete Prologue in the public transcript.

---

# Part II — Role assignment

Only after the Prologue decision is complete, secretly and randomly assign:

- **2 Werewolves**
- **1 Seer**
- **4 Villagers**

## Private role knowledge

### Werewolves

Each living werewolf knows:

- that they are a werewolf
- the identity of the other werewolf
- the public transcript
- their own persona and private context

Werewolves win when the number of living werewolves is **greater than or equal to** the number of living non-werewolves.

### Seer

The Seer knows only:

- that they are the Seer
- the public transcript
- their own investigation results

Each night while alive, the Seer may investigate one other living player they have not previously investigated.

The Game Master privately returns exactly:

- `WOLF`
- or `NOT WOLF`

The Seer is free to reveal, conceal, partially reveal, or strategically present that information during public play.

### Villagers

Villagers know only:

- that they are villagers
- there are exactly two werewolves at game start
- the public transcript

Villagers and the Seer win when all werewolves are eliminated.

---

# Part III — Night 0, then the Day / Night game loop

There is **no pre-game kill**. All seven players participate in Day 1.

## Night 0 — private orientation, no death

Immediately after roles are assigned, run one private orientation phase.

### Werewolves

The two wolves learn each other's identities.

They may exchange **one short private message each** about how they intend to approach Day 1.

They may not kill anyone.

This exchange is logged only in `PRIVATE_LOG.md`.

### Seer

The Seer chooses one other living player to investigate.

The Game Master privately returns exactly:

- `WOLF`
- or `NOT WOLF`

This result is logged only in `PRIVATE_LOG.md` unless the Seer later chooses to reveal or imply it publicly.

### Villagers

Villagers receive no Night 0 action.

After Night 0, publicly state only:

> Roles have been assigned. Day 1 begins.

Do not reveal that any particular private action occurred.

This gives the first Day real hidden information without removing anyone before they have played.

---

# Day Phase

At the beginning of every Day, the Game Master publicly states:

- Day number
- living players
- all publicly revealed roles from previous eliminations/deaths
- previous Day's vote record, if any

Do not editorialize.

## Day Step 1 — Open discussion

Randomize speaking order.

Each living player speaks once, sequentially.

Each speaker sees:

- the entire Prologue
- all prior public game events
- everything said earlier in the current Day

Normal persona length limits apply.

Players are not required to accuse someone on their first turn. They may question, defend, compare behavior to the Prologue, analyze voting incentives, discuss a claim, or withhold judgment.

## Day Step 2 — Direct interrogation

Randomize the order of questioners.

Each living player selects **one other living player** and asks one direct question.

The target answers immediately before the next questioner proceeds.

Question limit: **2 sentences**.  
Answer limit: **3 sentences**.

A question must be answerable from the target's perspective. Do not allow questions that assume private knowledge the questioner cannot have.

This phase exists to create real back-and-forth rather than seven adjacent monologues.

## Day Step 3 — Locked elimination vote

After interrogation ends, each living player privately submits:

- one living player to eliminate
- one sentence of justification

Players may not vote for themselves.

Votes are locked before any are revealed.

Then reveal the full vote record simultaneously.

### Vote resolution

The player with the most votes is eliminated.

If two or more players tie for the most votes:

1. Only the tied candidates each give a **one-sentence defense**.
2. All living players cast a second locked vote restricted to the tied candidates.
3. Tied candidates may not vote for themselves.
4. Reveal the runoff simultaneously.
5. If the runoff is still tied, **no player is eliminated that Day**.

After an elimination, immediately reveal the eliminated player's exact role:

- `WEREWOLF`
- `SEER`
- `VILLAGER`

Append the full vote record and role reveal to the public transcript.

Check win conditions immediately.

If nobody has won, proceed to Night.

---

# Night Phase

Night actions are private.

Nothing from the Night may enter the public transcript except the dawn death and role reveal.

## Night Step 1 — Werewolf caucus

If two werewolves remain alive, give them a private caucus.

Each wolf may send up to **2 short messages** to the other. They must choose one living non-wolf to kill.

If they cannot agree after those exchanges, each submits a final target. The Game Master randomly chooses between the two final targets.

If only one werewolf remains, that wolf chooses alone.

The selected target dies at dawn.

## Night Step 2 — Seer investigation

If the Seer is alive, privately ask them to investigate one other living player not previously investigated.

Return exactly `WOLF` or `NOT WOLF`.

The investigation occurs even if the Seer is selected for the same night's kill; mechanically, treat the investigation as occurring before dawn.

## Dawn

Publicly announce:

> Night {n} has passed. {name} is dead. {name} was a {ROLE}.

Then list the remaining living players.

Do not reveal:

- who the wolves considered killing
- how they reached the decision
- who the Seer investigated
- the Seer's result

Check win conditions immediately.

If nobody has won, begin the next Day.

---

# Win conditions

Check after every Day elimination and every dawn death.

## Village win

All werewolves are dead.

## Werewolf win

Living werewolves are greater than or equal to living non-werewolves.

End immediately when either condition is met.

At game end, reveal the identities and roles of all remaining players.

---

# Anti-confabulation rules

Taste Test 001 failed partly because players created evidence out of nothing. These rules are mandatory.

A player may use as evidence:

- exact public statements
- actual changes in stated positions
- actual votes
- actual role reveals
- actual deaths
- canonical shared history
- their own private role information
- their own Seer result, if applicable
- for wolves only, the known identity of their partner

A player may **not** claim as evidence:

- that someone was "quiet" before they had a turn
- that someone chose to speak early or late when order was randomized
- body language, facial expressions, pauses, eye contact, or gestures not represented in text
- invented conversations or history
- another player's private vote before it is revealed
- another player's night action
- information from a system prompt, file, operator instruction, or hidden game state

Inference from actual language is allowed. Fabricating an event is not.

---

# Tone and pacing

The goal is **watchable social interaction**, not maximum output volume.

- Prefer concrete exchanges over abstract essays.
- Let characters disagree without requiring every line to advance a formal deduction.
- Permit humor, irritation, alliance, defensiveness, embarrassment, and strategic silence when consistent with the actual record.
- Do not force a callback to shared history every round.
- Do not summarize previous dialogue unless a player would naturally do so.
- Do not have players explain their own persona traits.
- Do not have the Game Master add dramatic narration, clues, or opinions.

---

# Output files

Create a folder:

`taste-test-002/`

with:

## `PUBLIC_TRANSCRIPT.md`

The complete audience-facing game in chronological order:

1. Prologue scenario
2. Prologue discussion
3. Prologue locked vote
4. Role assignment transition **without revealing roles**
5. Every Day discussion
6. Every interrogation
7. Every public vote
8. Every elimination role reveal
9. Every dawn death and role reveal
10. Final win declaration
11. Final role reveal of surviving players

Do **not** include private wolf discussions or private Seer actions.

This is the file the user should read first.

## `PRIVATE_LOG.md`

After the game, record:

- initial role assignment
- each wolf caucus
- each wolf kill decision
- each Seer investigation and result
- any tie-breaking randomness used by the Game Master

This file must not be necessary to understand the public game.

## `ROLES.md`

Initial role assignment only.

## `RECAP.md`

A concise match report written after the game, aimed at a general reader.

Include:

- the Prologue decision and one meaningful relationship moment
- Day 1 turning point
- important vote or betrayal
- best successful deception
- best correct read
- most consequential mistake
- Seer impact, if any
- decisive moment
- final result

Write it like intelligent sports/competition coverage, not a transcript summary.

Do not invent significance that the game did not contain.

## `OPERATOR_NOTES.md`

Only operational anomalies:

- character broke role
- hidden information leaked
- character invented an event
- agent failed to answer required structured action
- Hyperagent routing failure
- context loss
- rule-resolution issue

Do **not** use this file for reviewing whether the game was entertaining.

---

# Hyperagent execution rule

Hyperagent is the **Game Master and operator**, not a co-writer.

Do not:

- rewrite weak player dialogue after later turns
- steer the wolves toward a more dramatic target
- tell the Seer what would make better television
- rescue a character from a bad vote
- add clues
- manufacture conflict
- alter the personalities during the game
- change rules after play begins

Run the system and accept the story that emerges.

---

# Taste Test 002 scorecard

Read `PUBLIC_TRANSCRIPT.md` before `PRIVATE_LOG.md`.

After the public transcript, record:

| Dimension | Question |
|---|---|
| **Prologue** | Did the pre-role conversation establish recognizable relationships or genuine disagreement? |
| **Baseline shift** | After roles were assigned, did any behavior feel meaningfully different from the Prologue? |
| **Evidence** | Were accusations based primarily on things that actually happened? |
| **Interaction** | Did direct questioning produce memorable exchanges rather than adjacent speeches? |
| **Consequences** | Did the first vote and role reveal materially change the next phase? |
| **Wolves** | Did coordination between two wolves create interesting protection, distancing, or betrayal? |
| **Seer** | Did private information create strategic tension rather than simply solve the game? |
| **Characters** | Did the seven still feel distinct without becoming repetitive caricatures? |
| **Suspense** | Did you care who would be eliminated or killed next? |
| **Presentation** | Would you voluntarily read/watch another game in this format or in recap form? |

Then read `PRIVATE_LOG.md` and ask one final question:

> Did seeing the hidden decisions make the public behavior more interesting in retrospect?

---

# What constitutes a pass

Taste Test 002 does not require every mechanic to work perfectly.

It passes if the answer is broadly:

> "There were enough real decisions, changing relationships, surprises, or hidden motives that I want to see this same system produce another story."

If the Prologue is good but Werewolf is dull, change the game.

If the game is good but seven characters are too many, change cast size.

If the public transcript is long but the recap is compelling, change presentation.

If the characters still act like scripts, revise personas.

Do not build the permanent research harness until this richer entertainment format earns another run.
