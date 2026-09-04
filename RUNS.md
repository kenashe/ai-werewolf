# Runs

Run figures below are taken directly from [`metadata/run-summary.csv`](metadata/run-summary.csv). See [`metadata/NOTES.md`](metadata/NOTES.md) for the owner's notes on how these numbers were recorded.

| Version | Games | Runtime | Player calls | Approx. subagent tokens | Hyperagent-reported metered usage | Notes |
|---|---:|---:|---:|---:|---:|---|
| V1 | 3 | 16 min | Not recorded | ~2.85M | ~$18 (approximate) | Full three-game batch. Metered usage was covered by Hyperagent credits. |
| V2 | 1 | 36 min | 75 | ~4.44M | ~$48 (approximate) | Single seven-player game. Metered usage was covered by Hyperagent credits. |
| V3 | 1 | 116 min (about 1 hr 56 min) | 231 | ~19.7M | $50.29 (exact as displayed) | Single nine-player game. All player calls used Fable 5. Hyperagent also displayed a small amount of Fable 5.1 thread usage. Metered usage was covered by Hyperagent credits. |

## Notes on these figures

- All dollar amounts are Hyperagent-reported metered usage. The usage was covered by existing Hyperagent credits; the figures are not out-of-pocket cost.
- V1 and V2 usage numbers are approximate values recorded by the project owner. The V1 player-call count was not recorded.
- V3 runtime, call count, and token count are approximate; the V3 usage total of $50.29 is exact as displayed by Hyperagent and is supported by screenshots. V3 ran from approximately 7:51 AM to 9:47 AM.
- The V3 player agents used Fable 5. Hyperagent's thread usage panel also showed a small amount of Fable 5.1 usage outside the documented player-call total.
- Do not use these three figures to infer per-token prices.

## V3 supporting screenshots

- [`v3/metadata/runtime-calls-tokens.png`](v3/metadata/runtime-calls-tokens.png) — runtime, player calls, and subagent tokens as displayed by Hyperagent.
- [`v3/metadata/usage-breakdown.png`](v3/metadata/usage-breakdown.png) — metered usage breakdown as displayed by Hyperagent.

No screenshots exist for V1 or V2.
