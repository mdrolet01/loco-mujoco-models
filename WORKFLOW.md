# Branch workflow & preferred working style

Official protocol for the **"Learning Natural Quadruped Locomotion: Token by Token"**
submission. Applies identically to all three project repos: **jadex_loco**,
**loco-mujoco-models**, **loco-mujoco-private**.

Goal: **iterate fast, review daily, don't fight to keep the codebase clean** — cleanliness
is handled in one elegant pass *after* the final submission.

## Branches
| branch | role |
|---|---|
| **`quad-tokens-wip`** | **Canonical working branch.** ALL day-to-day development happens here. Sloppy-but-working is fine — do not slow down for cleanliness. |
| **`quad-tokens-dirty`** | Branched off `main`. The reviewed accumulation of `-wip`. |
| **`quad-tokens`** | Reserved for the FINAL clean release (created off `main` at the very end). |
| **`quad-tokens-clean`** | Created off `quad-tokens-dirty` at the end; the spring-cleaned version that becomes the release. |

## The standing PR (all three repos)
```
quad-tokens-dirty  <--  quad-tokens-wip
```
- This PR is **always open** during the project. Merging it lets the maintainer see
  **what changed each day** in one place.
- **Nothing targets `main`** while the project is active.

## End of project (weeks out)
1. Create **`quad-tokens`** off `main`.
2. Finalize and **release `quad-tokens-dirty`** — an immutable tag + GitHub release:
   *"this is all the code we used for the submission."* The dirty branch can then be
   deleted later without losing anything.
3. Branch **`quad-tokens-clean`** off `quad-tokens-dirty`; spring-clean it hard.
4. Open the final PR: **`quad-tokens`  <--  `quad-tokens-clean`** (the polished release).

## Working style (during the project)
- **Speed over polish.** Nothing is expected to be perfect yet.
- **Don't clean as you go.** Repo tidiness is deferred to the post-submission clean pass.
- **Keep the `-wip -> -dirty` PR current** so the codebase state is always reviewable.
