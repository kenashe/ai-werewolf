# Apply instructions: publish final essay

These steps apply the packaged update to a local clone of `kenashe/ai-werewolf`. No GitHub operation was performed by the agent that produced this package; every step below is manual.

## Files in this package

- `README.md` (replacement for the repository root README)
- `docs/ESSAY.md` (new file)
- `CHANGES.diff` (unified diff of the intended change, for review)
- `VALIDATION_REPORT.md` (what was checked and the results)
- `APPLY_INSTRUCTIONS.md` (this file)

## Steps

1. Open a terminal at the root of your local clone and make sure you are on `main` with a clean working tree:

       git checkout main
       git pull
       git status

2. Replace the repository's root `README.md` with the packaged `README.md`:

       cp /path/to/unzipped/README.md ./README.md

3. Delete the draft essay:

       git rm docs/ESSAY_DRAFT.md

4. Add the final essay:

       cp /path/to/unzipped/docs/ESSAY.md ./docs/ESSAY.md
       git add docs/ESSAY.md README.md

5. Review the staged change. It should touch exactly three paths: `README.md` (modified), `docs/ESSAY_DRAFT.md` (deleted), `docs/ESSAY.md` (added). Nothing under `v1/`, `v2/`, `v3/`, `evidence/`, or `metadata/` and none of `MANIFEST.sha256`, `METHODOLOGY.md`, `RUNS.md`, `CHANGELOG.md`, `SOURCE_MANIFEST.md`, or `VERSION_SUMMARY.md` should appear:

       git status
       git diff --cached --stat

6. Commit with exactly this message:

       git commit -m "Publish final essay and link live write-up"

7. Push to `main`:

       git push origin main

8. Copy the resulting commit SHA for use in the website update:

       git rev-parse HEAD

## Notes

- `MANIFEST.sha256` does not cover `README.md` or `docs/`, so it does not need to be regenerated.
- `SOURCE_MANIFEST.md` still contains a historical line describing `docs/ESSAY_DRAFT.md` as part of the original source bundle. That file was out of scope for this update and was intentionally left unchanged; it describes the source bundle as received, not the current tree.
