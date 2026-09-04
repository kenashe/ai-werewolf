---
title: "AI agents can sound strategic while reasoning from events that never happened"
description: "I built three versions of an AI Werewolf game. The first agents made confident accusations from silence before a player had even spoken. The fix was not more prompting. It was an environment that could push back."
date: 2026-09-03
status: draft
---

# AI agents can sound strategic while reasoning from events that never happened

I gave four Fable 5 agents hidden roles and asked them to play Werewolf.

The first speaker opened with this accusation:

> **Sable:** "Ptolemy. Hasn't said a word yet and that silence is doing a lot of work."

Ptolemy had not said a word because it was not his turn.

The second speaker immediately did the same thing:

> **Bosch:** "Wren has said nothing, which is precisely what a careful operator does when the opening move belongs to someone else."

Wren had not received a turn either.

The dialogue sounded strategic. Silence can be suspicious in a social deduction game. A careful player might wait for others to commit before choosing a target. The explanation made sense in the abstract.

It just did not describe anything that had happened.

That failure repeated across all three games in the first version. The agents were not producing random gibberish. They were producing plausible social reasoning from nonexistent evidence.

That turned out to be the most useful result of the project.

## Version 1: strategy without a world

I built the game in Hyperagent. All four players used Fable 5, with separate character prompts and hidden roles.

Version 1 was intentionally stripped down:

- four players
- one werewolf
- three discussion rounds
- no eliminations during play
- no night kills
- one final vote

I was testing whether four strongly defined personalities could remain distinct. They did. The characters sounded different.

But the game gave them almost nothing real to reason about.

In Game 2, Bosch spoke first and announced:

> "I have been watching, and Ptolemy strikes me as the one to watch: there is something in the way a methodical mind hides behind silence."

Again, Ptolemy had not spoken.

In Game 3, Ptolemy asked Wren:

> "How did you decide on the order in which you were going to speak today?"

Wren did not decide. The Game Master randomized the order.

Across all three games, at least one agent treated behavior that had not occurred, or an operator-controlled condition, as evidence about another player.

This was not limited to the werewolf. Villagers did it too.

## What the agents were actually doing

The prompt required the agents to interpret one another strategically. The environment provided almost no meaningful evidence, but the agents still had to produce an answer.

So they substituted a model of what *usually matters* in a social deduction game:

- silence can indicate concealment
- patience can be strategic
- early accusations can be deflection
- neutrality can be a way to avoid commitment
- speaking order can reveal intent

Those are reasonable concepts. The problem was that the models applied them to events that were absent from the actual record.

The result was reasoning-shaped language without reasoning grounded in the environment.

That distinction is easy to miss because the prose was coherent. Each agent could also respond to the previous agent's invented premise, which made the conversation feel increasingly structured. One unsupported inference became material for the next.

More agents talking did not create more evidence. It created more interpretations of the same evidentiary vacuum.

## I changed the environment, not just the prompt

I built two larger versions.

Version 2 added seven recurring characters, shared history, a pre-role prologue, two werewolves, a Seer, elimination votes, night kills, role reveals, and direct interrogation.

Version 3 expanded to nine characters and added stronger voices, social missions, private confessionals, an open floor, and two edited audience formats.

The system also gained a canonical public transcript and explicit private state. Each player received only the information their role was allowed to know. Votes changed who remained alive. Night actions changed the next day's state. Eliminated roles were revealed. Claims could be checked against the transcript.

The project grew quickly:

| Version | Run shape | Runtime | Player calls | Subagent tokens | Hyperagent-reported metered usage |
|---|---|---:|---:|---:|---:|
| V1 | Three small games | 16 min | Not recorded | ~2.85M | ~$18 |
| V2 | One seven-player game | 36 min | 75 | ~4.44M | ~$48 |
| V3 | One nine-player game | 1 hr 56 min | 231 | ~19.7M | $50.29 |

The usage figures were covered by Hyperagent credits. I am reporting the platform's displayed numbers, not using them to infer token pricing.

The larger versions were much more entertaining, but the important change was not the cast size. The environment now contained facts that could survive contact with another agent.

## A claim that could actually fail

Late in Version 3, Ptolemy claimed that Finch's position had followed Inez's lead.

Finch checked the public record:

> **Finch:** "The transcript has me naming Ptolemy in my own speech before Inez ever opened her mouth."

Ptolemy then conceded:

> **Ptolemy:** "Yes, I concede in full... the transcript has Finch's 'leans Ptolemy' before Inez ever spoke."

The models were still capable of making factual mistakes. The difference was that the world now had an answer.

The transcript could contradict them.

That is a much more useful target than trying to prompt every hallucination out of existence. The goal is not a system in which agents never make incorrect claims. The goal is a system in which incorrect claims can fail visibly and change what happens next.

## The wolves started making real strategic decisions

The private behavior changed too.

In Version 3, the two werewolves, Ptolemy and Vale, entered the game with strong public reputations. During their private orientation, they agreed to preserve distance:

> "We only coordinate on the night kill, never on the floor."

They did not publicly defend one another. They let the village create its own majorities, then joined those votes without behaving like a visible pair.

After Day 1, they chose to kill Wren because she was auditing the transcript and comparing votes with prior commitments:

> "Kill the auditor, keep the misdirection."

They did not know Wren was the Seer. They killed her because of what she was actually doing in the game, and accidentally removed the village's information role at the same time.

That was strategy grounded in state:

- Wren had established a public method.
- That method threatened the wolves.
- The wolves privately evaluated the threat.
- Their action removed Wren.
- Her private information disappeared with her.
- The next day's decision environment changed.

The village ultimately eliminated three villagers and no wolves. Ptolemy and Vale won without ever voting against or openly rescuing each other.

## Grounding did not make the agents error-free

Version 3 still contained inaccurate claims.

Inez overstated how often Finch had endorsed Rook. Rook misremembered whether he had been given a chance to answer. Ptolemy reversed the order of two public statements.

The operator log recorded those errors. Some were corrected by other players during the game.

That is the point.

Version 1 allowed agents to build arguments from events that had never happened, with little in the environment capable of challenging them.

Version 3 still allowed agents to be wrong, but it gave the system a canonical record, adversarial readers, and consequences. Errors became contestable instead of decorative.

## What this does not prove

This was not a controlled experiment.

I changed many variables between versions:

- number of players
- game mechanics
- amount of private information
- persona prompts
- relationship history
- voting structure
- role reveals
- night actions
- interrogation format
- anti-confabulation instructions

The sample was tiny. All player agents ran through Hyperagent. Strong fictional personalities made the games more entertaining while making it harder to distinguish model behavior from persona behavior.

So I am not claiming that adding eliminations caused unsupported reasoning to disappear.

The narrower observation is this:

> In the minimally grounded version, all three games contained confident social reasoning based on nonexistent behavior or operator-controlled conditions. In the richer versions, much more of the reasoning attached to observable state, and factual errors could be challenged against a shared record.

That is an anecdotal build result, not a benchmark.

## The broader lesson for multi-agent systems

This is not really about Werewolf.

Many multi-agent demos consist mainly of language models talking to other language models. One agent proposes. Another critiques. A third synthesizes. The transcript becomes longer and more convincing, but the environment may still have no independent way to say whether any of them are right.

If the task demands an explanation and the system provides too little grounded evidence, an agent can substitute a plausible theory of the domain for evidence from the actual task.

A few design rules now seem obvious to me:

1. **Keep canonical state outside the agents.** Do not rely on each agent's conversational memory as the source of truth.
2. **Give actions observable consequences.** Votes, file changes, code execution, prices, approvals, test results, and state transitions create evidence.
3. **Make claims falsifiable against logs or tools.** A polished explanation should not outrank the record.
4. **Separate public and private information deliberately.** Hidden state should be controlled by the environment, not inferred from prompt leakage.
5. **Evaluate outcomes, not just prose quality.** Coherent discussion can still be detached from reality.

The shortest version is:

> Give agents a world that can contradict them.

## The entertainment tradeoff

The richer game worked as a story. It felt closer to *The Traitors* than to a conventional agent demo.

It also became too large.

Version 3 took almost two hours, used 231 player calls and about 19.7 million subagent tokens, and produced far more text than I would want to consume repeatedly. Accents, elaborate personas, relationships, confessionals, and social missions improved the fiction but made the system worse as an evaluation of the underlying model.

The thing that made the game more entertaining also became a confound.

## Next: make the models the cast

The next version removes the fictional personalities.

Instead, six different models will play against one another under the same rules. Their identities will be hidden from one another but visible to the audience. Each model will rotate through Werewolf, Seer, and Villager roles across multiple games.

That changes the question from:

> Can a carefully written character fool another carefully written character?

to:

> Which models are naturally better at deception, persuasion, evidence tracking, belief revision, and detecting lies?

The first game will still be a showcase, not a scientific benchmark. If the format works, I will move the player calls out of Hyperagent and into a direct-provider harness for cleaner comparisons.

For now, the useful result came from the failure.

The agents sounded as though they were reasoning strategically before the environment gave them anything real to reason about. The fix was not asking them to sound smarter.

It was giving them a world capable of proving them wrong.

---

All prompts, transcripts, hidden-role files, private logs, operator notes, and run metadata are available in the [GitHub repository](https://github.com/kenashe/ai-werewolf).
