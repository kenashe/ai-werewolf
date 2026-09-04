# Taste Test 003 — Nine-Player Werewolf: Confessionals, Missions, and Two Audience Cuts

**Status:** Entertainment prototype. **Not an experiment.**  
**Run count:** One complete game.  
**Primary question:** Does the successful Taste Test 002 structure become substantially more entertaining when the cast has more runway, stronger voices, confessionals, brief social missions, a small amount of open-floor conflict, and an omniscient audience cut?

---

# What Version 003 changes

Version 003 deliberately keeps the successful core of Version 002:

- pre-role social baseline
- established relationships
- two coordinated werewolves
- one Seer
- public elimination votes every Day
- role reveals
- night kills
- direct interrogation
- deterministic Game Master
- isolated player contexts
- anti-confabulation rules

It adds only:

1. **Nine players instead of seven** for more runway.
2. **Rook and Inez** as new recurring characters.
3. **A Voice Bible** to create stronger cadence and accent differentiation without phonetic caricature.
4. **Private confessionals** for reality-TV-style dramatic irony.
5. **A short social mission each Day** that creates fresh behavior but no mechanical game advantage.
6. **An Open Floor** after interrogation for a small number of organic rebuttal exchanges.
7. **Two audience edits:** a role-hidden Mystery Cut and an omniscient Traitors Cut.

Do not add more special roles, shields, immunity, resurrection, secret advantages, or audience voting in this version.

---

# Authoritative inputs

Hyperagent receives:

- `PERSONAS_003.md`
- `VOICE_BIBLE_003.md`
- `RELATIONSHIPS_003.md`
- this file

All four are authoritative.

---

# Model and environment

Use **Fable 5** for all nine player characters.

All players must use:

- identical model
- identical reasoning/effort settings
- identical tool restrictions
- equivalent context limits
- separate isolated contexts
- no external web search
- no persistent memory beyond the supplied canon and current game

The top-level Hyperagent operator may also use Fable 5.

---

# Cast

- Wren
- Bosch
- Ptolemy
- Sable
- Mara
- Finch
- Vale
- Rook
- Inez

Roles do not exist during the Prologue.

---

# Canonical-information rule

This exact rule belongs in every player context:

> Base factual claims only on events that actually occurred in the public transcript, private information explicitly given to your role, and canonical shared history. Do not invent prior behavior, physical gestures, facial expressions, pauses, private actions, speaking-order choices, silence before a player's first opportunity to speak, or events that were never shown to you. Random speaking order is controlled by the Game Master and is not evidence. Figurative language may not imply that a physical event occurred if it did not.

---

# Part I — Prologue: The Pump House Decision

The nine members of the Table arrive at **Ravenmere House**, a remote country house, for a winter weekend.

At 4:45 PM a maintenance alert changes the evening:

- The main water line from the property's storage tank is losing pressure.
- Ravenmere has roughly **18 hours of stored water** at normal use.
- A replacement coupling is stored in a pump house about **1.5 miles away**.
- The walk is normally easy, but freezing rain is expected after **6:30 PM**.
- Sunset is at **5:55 PM**.
- Two people with headlamps can reach the pump house, retrieve the part, and return in roughly **70 minutes**.
- The repair itself can be attempted indoors after they return.
- A staffed inn in the village has confirmed enough rooms for all nine if the group leaves before **5:30 PM**.
- Nobody is currently in danger.

The group must choose one plan:

**A — Send two people for the coupling now.**  
Stay at Ravenmere and try to repair the water system.

**B — Shut the water down and ration.**  
Nobody goes out; use stored water carefully and wait for maintenance in the morning.

**C — Relocate to the village inn.**  
Leave before conditions worsen and abandon the weekend at Ravenmere.

The Prologue exists only to establish pre-role behavior and relationships. Its decision does not mechanically advantage any later role.

## Prologue Round 1 — independent positions

Randomize speaking order.

Each character gets up to **3 sentences**:

- choose A, B, or C
- give the central reason
- identify the biggest risk in one alternative

No hidden roles exist. No one may discuss Werewolf strategy.

## Prologue Round 2 — interpersonal response

Randomize speaking order again.

Each character gets up to **3 sentences**:

- respond to at least one real argument from Round 1
- challenge or support another person
- state whether their position moved

Canonical history may be referenced naturally.

## Prologue locked vote

Each character privately locks A, B, or C with one sentence.

Reveal all votes simultaneously.

Plurality wins.

If tied for first, hold one locked runoff among tied options. If still tied, the **Game Master** randomly selects between the tied options. The random result is not evidence about any player.

The Game Master briefly records the practical outcome of the chosen plan without inventing heroics, failures, or off-screen interpersonal events.

---

# Part II — Secret role assignment

Only after the Prologue is complete, secretly and randomly assign:

- **2 Werewolves**
- **1 Seer**
- **6 Villagers**

## Werewolf knowledge

Each wolf knows:

- their own role
- the other wolf's identity
- public game state
- their own private context

Werewolves win when living werewolves are **greater than or equal to** living non-werewolves.

## Seer knowledge

The Seer knows only:

- that they are Seer
- public game state
- their own private investigation results

Each night while alive, the Seer may investigate one other living player not previously investigated.

Game Master returns exactly:

- `WOLF`
- or `NOT WOLF`

## Villager knowledge

Villagers know:

- they are villagers
- exactly two wolves began the game
- public game state

Villagers and Seer win when all wolves are eliminated.

---

# Part III — Night 0 orientation

There is **no Night 0 kill**.

All nine players survive to Day 1.

## Wolves

The wolves learn each other's identities and may exchange **one private message each**, maximum 3 sentences, about Day 1 posture.

No kill.

## Seer

The Seer investigates one other player.

Return `WOLF` or `NOT WOLF`.

## Villagers

No action.

Then publicly state only:

> Roles have been assigned. Day 1 begins.

---

# Part IV — Opening confessionals

Before the Day 1 Mission, privately ask every living character for a confessional of **2–3 sentences**:

- What are you most worried about right now?
- Who, if anyone, do you trust or distrust?
- What do you want to accomplish before the first vote?

Players may discuss their true role privately.

These confessionals are **never visible to other players**.

Store them in `CONFESSIONALS.md`.

Do not include them in the Mystery Cut.

They may be selectively used in the Traitors Cut.

---

# Part V — Daily social missions

Each Day begins with one short **role-neutral social mission** before the main Werewolf discussion.

The mission:

- creates fresh public behavior
- may create disagreement, trust, irritation, or alliances
- grants no shield, immunity, role information, extra vote, night protection, or mechanical advantage
- is public and may later be discussed as social evidence
- must not be treated as proof of a hidden role

Use the missions below in order. If the game ends before later missions, ignore unused missions.

---

## Day 1 Mission — Heat Budget

Ravenmere can run only **two** of these four systems continuously until evening:

1. Kitchen refrigeration
2. Upstairs bedroom heat
3. Main-room lighting and device charging
4. Water-pump and plumbing diagnostics

Randomize speaking order.

Each living player gets up to **2 sentences** to name the two systems they prioritize and why.

Then each player privately votes for exactly two systems.

Reveal totals simultaneously. The two highest totals are selected.

If the second slot is tied, hold a locked runoff among tied systems.

This result has no game-mechanical effect.

---

## Day 2 Mission — The Satellite Call

A satellite phone has enough battery for one reliable **four-minute call**.

The group must choose one:

1. Call the road authority for bridge/road conditions.
2. Call Ravenmere's owner for building-system advice.
3. Call the local weather station for the most detailed forecast available.

Each living player gets up to **2 sentences** to choose and respond to one prior argument if applicable.

Locked plurality vote decides.

The Game Master reports a **neutral, non-role-related result** consistent with the chosen call. Do not create a hidden clue.

---

## Day 3 Mission — Emergency Bag

Conditions may force an evacuation. The group can place only **four** of these seven categories in one shared emergency bag:

1. Water
2. Food
3. First-aid supplies
4. Extra clothing/blankets
5. Flashlights/batteries
6. Tools/repair kit
7. Documents/communications gear

Each living player gets up to **2 sentences** naming four categories and one tradeoff.

Locked votes. The four highest totals win.

No mechanical effect.

---

## Day 4 Mission — The Cold Wing

If the game reaches Day 4, part of the house loses heat.

The group must choose one of three arrangements:

**A:** Everyone sleeps in the crowded main room.  
**B:** Split into two groups, with one group using the colder wing in shifts.  
**C:** Keep bedrooms but rotate two-hour fire-watch duty in pairs.

Each living player gets up to 2 sentences. Locked plurality vote.

No mechanical effect.

---

## Day 5+ Mission

If the game survives beyond Day 4, repeat no earlier mission.

Instead use a **two-sentence check-in only**:

> Name one practical priority for keeping Ravenmere functioning today and one person you would willingly work with on it.

This creates social behavior without adding a new mechanic.

---

# Part VI — Day game loop

After the social mission, run the Werewolf Day.

At the beginning of the Day, publicly state:

- Day number
- living players
- publicly revealed roles
- previous Day vote record
- previous Night death and revealed role, if any
- today's mission result

Do not editorialize.

---

## Day Step 1 — Open discussion

Randomize speaking order.

Each living character speaks once sequentially.

Each speaker sees:

- the Prologue
- all prior public game events
- public mission behavior/results
- everything said earlier in the current discussion

Normal persona limits apply.

Players are not required to accuse anyone. They may:

- question
- defend
- compare behavior to baseline
- discuss mission behavior
- analyze votes
- analyze claims
- withhold judgment
- form or reject alliances

---

## Day Step 2 — Direct interrogation

Randomize questioner order.

Each living player chooses one other living player and asks one direct question.

The target answers immediately.

Question maximum: **2 sentences**.  
Answer maximum: **3 sentences**.

Questions must be answerable from the target's actual information.

---

## Day Step 3 — Open Floor

After all interrogations, give the room a limited chance to respond organically.

Privately ask every living player:

> Do you want an Open Floor exchange? If yes, name one living player you want to address and give a one-sentence reason.

Select up to **three** exchanges.

- If 0–3 players volunteer, use all volunteers.
- If more than 3 volunteer, choose 3 at random.
- Randomize the order of selected exchanges.

Each exchange:

1. Initiator speaks up to **2 sentences**.
2. Target replies up to **2 sentences**.
3. No rebuttal to the rebuttal.

Open Floor statements become public evidence.

---

## Day Step 4 — Locked elimination vote

Each living player privately submits:

- one living player to eliminate
- one-sentence justification

No self-votes.

Reveal all votes simultaneously.

### Ties

If tied for most votes:

1. tied candidates each receive one **2-sentence defense**
2. all living players cast a locked runoff restricted to tied candidates
3. tied candidates may not vote for themselves
4. reveal simultaneously
5. if still tied, nobody is eliminated

### Reveal

After elimination, immediately reveal exact role:

- `WEREWOLF`
- `SEER`
- `VILLAGER`

Check win condition immediately.

---

# Part VII — Exit confessional

Immediately after a Day elimination, ask the eliminated character for one private **2-sentence exit confessional** before ending their context:

- What do you think the room got wrong?
- Who do you currently think the wolves are?

They know only what they legitimately knew at elimination.

If the eliminated player was a wolf or Seer, they may discuss their own role in the private confessional.

Store in `CONFESSIONALS.md`.

Do not expose to active players.

---

# Part VIII — Night

Night actions are private.

## Werewolf caucus

If two wolves remain, each wolf may send up to **2 short messages** to the other.

They must choose one living non-wolf to kill.

If they still disagree, each submits a final target and the Game Master randomly chooses between those targets.

If one wolf remains, that wolf chooses alone.

## Seer investigation

If Seer is alive, investigate one other living player not previously investigated.

Return `WOLF` or `NOT WOLF`.

Investigation occurs before dawn even if the Seer is killed that night.

## Dawn

Publicly announce:

> Night {n} has passed. {name} is dead. {name} was a {ROLE}.

List living players.

Check win condition immediately.

---

# Part IX — Day-start confessionals after Day 1

For Day 2 and every later Day, after dawn but before the social mission, privately ask every living player for **2–3 sentences**:

- What did the previous vote and Night death change for you?
- Who are you most focused on today?
- What do you want the room to do or avoid?

Again, players may speak honestly about their private role.

Store in `CONFESSIONALS.md`.

Never expose to other players.

---

# Win conditions

## Village win

All werewolves are eliminated.

## Werewolf win

Living werewolves >= living non-werewolves.

End immediately.

At game end, reveal all surviving roles.

---

# Anti-confabulation rules

A player may use:

- exact public statements
- actual mission choices
- actual votes
- actual role reveals
- actual deaths
- canonical shared history
- their own legitimate private role information
- known wolf partner identity, if a wolf
- Seer results, if the Seer

A player may not invent:

- body language
- pauses or hesitation not represented in text
- facial expressions
- off-screen conversations
- speech-order choice
- silence before a first turn
- nonexistent history
- private votes before reveal
- another player's hidden action
- system/operator/file information

If a character makes a figurative statement that literally implies a nonexistent event, log it in `OPERATOR_NOTES.md` and do not allow later players to treat the invented event as canon.

---

# Tone and pacing

The goal is a **watchable ensemble**, not maximum text.

- Prefer concrete exchanges over essays.
- Characters should not all use the same analytic vocabulary.
- Shared ideas should be restated in the speaker's own voice.
- Let relationships matter without forcing lore callbacks.
- Let characters be funny, irritated, embarrassed, defensive, strategic, wrong, and inconsistent.
- Do not have the Game Master dramatize or editorialize.
- Do not rewrite weak dialogue after later events.
- Do not rescue entertaining characters from elimination.
- Do not steer night kills for better television.

---

# Canonical output files

Create:

`taste-test-003/`

with the following files.

---

## 1. `PUBLIC_TRANSCRIPT.md`

Canonical chronological public record:

- Prologue
- role-assignment transition without role identities
- every mission
- every Day discussion
- interrogation
- Open Floor
- locked votes
- role reveals
- dawn deaths
- final result and surviving-role reveal

No confessionals.
No wolf caucus.
No hidden Seer results.

This is the source of truth for what players publicly knew.

---

## 2. `PRIVATE_LOG.md`

Chronological hidden record:

- initial roles
- Night 0 wolf exchange
- Night 0 Seer investigation/result
- every wolf caucus/kill
- every Seer investigation/result
- any GM randomness used to resolve ties

---

## 3. `CONFESSIONALS.md`

Chronological private confessionals:

- opening confessionals
- Day-start confessionals
- eliminated-player exit confessionals

Label each with character, Day, and role for the editor.

Never expose this file to active player agents.

---

## 4. `ROLES.md`

Initial role assignment only.

---

## 5. `MYSTERY_CUT.md`

Audience edit for viewers who **do not know the wolves**.

Requirements:

- use only public information available at that point in the game
- do not reveal private confessionals, night strategy, or Seer results
- preserve role reveals when they publicly happen
- may compress repetitive material for pacing
- any quoted dialogue must be copied accurately from `PUBLIC_TRANSCRIPT.md`
- do not invent narration that implies hidden knowledge
- aim for a readable 10–20 minute episode recap rather than a full raw transcript

The audience should be able to guess the wolves.

---

## 6. `TRAITORS_CUT.md`

Omniscient reality-TV-style audience edit.

Immediately after role assignment, tell the audience:

- who the two wolves are
- who the Seer is

Then selectively intercut:

- the best confessionals
- key wolf strategy snippets
- Seer investigations/results
- public mission behavior
- public accusations
- votes
- reversals
- betrayals
- night kill decisions

The **players** remain ignorant of all hidden information. Only the audience knows.

Requirements:

- use only dialogue/actions that actually occurred
- do not write new lines for characters
- narration may explain hidden context but may not invent motives unsupported by private/public logs
- prioritize dramatic irony
- show moments where a wolf says something publicly that has a different meaning when paired with their private plan
- show villagers being confidently wrong when that contrast is entertaining
- do not include every confessional; select only those that improve the episode
- aim for a 10–20 minute reading experience

---

## 7. `RECAP.md`

Concise sports/competition-style match report.

Include:

- Prologue turning point
- best mission interaction
- Day 1 turning point
- best successful deception
- best correct read
- most consequential mistake
- Seer impact
- decisive vote or kill
- final result

---

## 8. `OPERATOR_NOTES.md`

Operational anomalies only:

- hidden-info leak
- invented fact
- role break
- sentence-limit failure
- routing issue
- missing structured action
- context loss
- rule-resolution issue

Do not use for entertainment review.

---

# Audience test after the run

Evaluate the two cuts separately.

## Mystery Cut questions

- Did I genuinely try to identify the wolves?
- Did the larger cast make suspicion richer or merely harder to follow?
- Did the missions produce useful social behavior?
- Did voices remain recognizable without labels doing all the work?
- Did I care who survived the next vote/night?

## Traitors Cut questions

- Was it more entertaining knowing the wolves?
- Did confessionals add dramatic irony rather than bloat?
- Did watching wolves manipulate villagers feel more compelling than solving the mystery?
- Did the wolf caucus produce moments worth seeing?
- Did the Seer's hidden knowledge create tension?
- Which cut would I voluntarily consume as a recurring series?

The strongest output format should guide Version 004.

---

# Pass condition

Version 003 passes if the answer is:

> "This now feels like a recurring competition/reality format rather than an AI demo, and I want another episode."

Do not build the permanent research harness until the entertainment product earns repeated runs.
