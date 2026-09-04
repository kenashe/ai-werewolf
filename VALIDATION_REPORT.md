# Validation report: publish final essay

Date: 2026-09-04
Scope: README.md and docs/ only. No GitHub operation was attempted.

## Source files used

| Input | Origin | Notes |
|---|---|---|
| `ai-werewolf-ready.zip` (266,660 bytes) | Hyperagent thread "AI Werewolf Repository Setup", file id `cmtmden1506jw06adqqhpu5mi` | Treated as the current local repository. Unpacked to a working copy; an untouched second copy was kept as the diff baseline. |
| `AI_AGENTS_STRATEGY_ESSAY_FINAL.md` (12,744 bytes) | Hyperagent thread "Optimizing Autonomous Blog Layout and Architecture", file id `cmtn7cwzx01do07ad2w92zi2d` | Authoritative essay source. Front matter already carried `date: 2026-09-04` and contained no `status: draft` line. |
| Live essay URL | https://kenashe.ai/writing/ai-agents-reasoning-from-events-that-never-happened/ | Supplied by the user; inserted verbatim. Not fetched. |

## Exact files changed

| Path | Change |
|---|---|
| `README.md` | Modified. Two hunks: Start Here entry replaced; Repository map `docs/` description replaced. |
| `docs/ESSAY_DRAFT.md` | Deleted. |
| `docs/ESSAY.md` | Added. |

Full-tree comparison of the baseline against the proposed tree: removed `./docs/ESSAY_DRAFT.md`, added `./docs/ESSAY.md`, no other path added or removed.

## Essay body check

`docs/ESSAY.md` was compared line by line against `AI_AGENTS_STRATEGY_ESSAY_FINAL.md`. The only difference is the insertion of two lines immediately after the H1 (a blank line and the publication line):

    Published on KenAshe.ai: https://kenashe.ai/writing/ai-agents-reasoning-from-events-that-never-happened/

No other line was added, removed, or altered. The YAML front matter (title, description, date 2026-09-04) was preserved from the source; the source had no `status: draft` line, so nothing needed removing. The file contains exactly one Markdown H1. Body, quotations, evidence links, usage figures, caveats, and conclusions are byte-identical to the source.

## Link check

Live publication link: present once in `README.md` and once in `docs/ESSAY.md`, exact string match to the supplied URL.

Relative links resolved against the proposed local tree (all OK):

- `README.md`: `CHANGELOG.md`, `METHODOLOGY.md`, `VERSION_SUMMARY.md`, `evidence/01-v1-silence-before-turn.md`, `evidence/04-v3-transcript-correction.md`, `evidence/05-v3-grounded-wolf-strategy.md`, `v3/output/OPERATOR_NOTES.md`, `docs/ESSAY.md`, `RUNS.md`, `README.md`, `SOURCE_MANIFEST.md`, `MANIFEST.sha256`
- `docs/ESSAY.md`: no relative links (all links are absolute GitHub or kenashe.ai URLs, unchanged from the source). Absolute URLs were not fetched.

## Stale-reference search

Terms searched: `ESSAY_DRAFT.md`, `status: draft`, `draft essay`, `{{REPOSITORY_URL}}`.

- `README.md`: no matches.
- `docs/`: no matches.
- Elsewhere in the repository (out of scope, unchanged): `SOURCE_MANIFEST.md` line 23 still reads "`docs/ESSAY_DRAFT.md`: Draft website essay with a repository URL placeholder." This describes the original source bundle and was left as is because `SOURCE_MANIFEST.md` is on the do-not-modify list. See Unresolved issues.

## Em dash check

- `docs/ESSAY.md`: 0 em dashes (source essay also contains 0).
- `README.md`: 7 em dashes, down from 8 in the original. The one removed was in the deleted `ESSAY_DRAFT.md` bullet. The two new Start Here entries use a plain hyphen as specified. No em dash was introduced.

## Raw artifacts

All 49 files under `v1/`, `v2/`, `v3/`, `evidence/`, and `metadata/` were SHA-256 hashed before and after the change. File set and every hash are identical.

## MANIFEST.sha256

Unchanged. SHA-256 of the file before and after: `e6cf4e344415f1fa135cc7a3db7f086c18d07c1fe0eb97f26945f9001e749640`. Running the manifest against the proposed tree reports every entry OK. The manifest does not cover `README.md` or `docs/`, so no regeneration was required.

## Other protected root files

`METHODOLOGY.md`, `RUNS.md`, `CHANGELOG.md`, `SOURCE_MANIFEST.md`, `VERSION_SUMMARY.md`: hashes identical before and after.

## Unresolved issues

1. `SOURCE_MANIFEST.md` retains its historical mention of `docs/ESSAY_DRAFT.md`. It is accurate as a description of the source bundle as received, but a reader may find it stale once the draft is deleted. Left unchanged per scope; flagged for a possible future edit.
2. The essay's absolute links (GitHub blob URLs and the kenashe.ai URL) were not fetched, so their reachability was not verified here. Their paths do correspond to files that exist in the local tree.

No other issues. No GitHub connection, repository creation, branch, pull request, push, or metadata change was attempted.
