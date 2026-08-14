# Maintenance Guide

This document describes how to keep Awesome-ACWM accurate, consistent, and easy to extend over time.

## Repository history

The current `initial commit` is a historical baseline created when the repository was cleaned up. It is not an ongoing release-management rule.

From this point forward:

- Use normal Git commits for every change.
- Keep commits focused and descriptive, such as `Add IRASim entry`, `Fix project link`, or `Update citation metadata`.
- Do not amend, squash, reset, or rebase `main` merely to preserve the `initial commit` message.
- Do not force-push `main`. History should evolve normally through regular pushes or pull requests.
- Preserve unrelated work when making an update; avoid bundling formatting-only changes with paper additions.

The repository should normally have a linear, reviewable history in which each commit explains one logical maintenance action.

## Adding a paper

An entry belongs in this list when it satisfies the scope in `README.md`:

1. It models visual observations as pixels/video, visual tokens, a renderable 3D/4D representation, or learned visual features/latents.
2. Its transition is conditioned on explicit controls or learned latent actions.
3. The learned transition is used for interactive rollout, simulation, planning, policy learning, evaluation, or control.

Before adding an entry:

- Check whether the work is already listed under another name or version.
- Use the first public release month, not the publication or revision month.
- Copy the official paper title and capitalization.
- Choose the closest representation tag (`Video`, `Token`, `Latent`, `Feature`, `3D/4D`, or `Unified`).
- Add every demonstrated downstream-use tag (`Game`, `Eval`, `IL`, `RL`, `Plan`, `Policy`, or `Data`). Embodied simulation remains one flat list because a paper may support several uses.
- Prefer the arXiv abstract page, official project page, and official code repository. Omit links that do not exist.

For papers first publicly released before 2026, retain entries only when their citation count is above 20 at review time. Papers first released in 2026 are exempt from this threshold because they are too recent for citation counts to be informative.

## Updating an entry

Update an existing row when the paper receives a new version, an official project or code link becomes available, or a factual title/tag/link correction is needed. Do not create duplicate rows for a paper that has multiple downstream uses or publication venues.

Keep rows ordered by first public release date, newest first. If several works share a month, keep their existing relative order unless there is a clear reason to reorder them.

## Link and metadata checks

For each new or changed row:

- Open the paper link and confirm that it resolves to the intended work.
- Check project and code links against the authors' official pages or repositories.
- Remove stale, redirected, personal mirror, or unrelated links.
- Confirm that the representation and use tags are supported by the paper rather than inferred from marketing language.
- Run `git diff --check` before committing.

The `Last metadata check` date in `README.md` should be updated when a broader review of the list is completed, not for every single typo fix.

## Normal update workflow

1. Create a branch for a focused update.
2. Edit `README.md` and, when needed, this guide.
3. Review the rendered Markdown table and run `git diff --check`.
4. Commit the logical change with a concise message.
5. Push the branch and open a pull request, or merge through the repository's normal workflow.
6. After merging, verify that `main` is clean and that the new links are reachable.

Never rewrite shared history to change a commit message or to reduce the number of commits. A normal follow-up commit is the preferred fix.

## Periodic review

At least once per quarter, review:

- new action-conditioned video, game-world, embodied-simulation, 3D/4D, unified, and latent-control papers;
- broken or redirected project and code links;
- citation thresholds for pre-2026 entries;
- duplicate versions, inconsistent tags, and incorrect release months;
- the benchmark and dataset sections;
- the `Last metadata check` date.

When a paper no longer meets the inclusion criteria, remove it in a dedicated, clearly named commit rather than silently rewriting earlier history.
