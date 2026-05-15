# Contributing to MTMVideo repos

## Branch naming

Use one of:

- `feature/<TICKET-ID>-short-description` — new functionality
- `fix/<TICKET-ID>-short-description` — bug fixes off main
- `hotfix/<TICKET-ID>-short-description` — production hotfixes off the latest prod tag

`<TICKET-ID>` is uppercase letters + digits, e.g. `MTM-1234`. PRs from
non-conforming branches fail the **Branch name check** and cannot merge.

## Commit messages

[Conventional Commits](https://www.conventionalcommits.org/). Format:

    <type>: <imperative summary>

    [optional body]

    [optional footer, e.g. BREAKING CHANGE: ...]

Types we use:

- `feat:` — new feature → minor version bump
- `fix:` — bug fix → patch version bump
- `chore:` — tooling, deps, no behavior change
- `ci:` — pipeline / workflow changes
- `docs:` — docs only
- `refactor:` — no behavior change, code restructuring
- `test:` — tests only

A `BREAKING CHANGE:` footer (or `!` after type, e.g. `feat!:`) bumps the
major version.

## Merge strategy

Squash-merge only. One commit per feature lands on `main`. The PR title
becomes the squash commit subject — write it as a Conventional Commit
(`feat: add retry logic to agent matcher`).

## PR requirements

- Branch matches naming convention
- At least one approval
- All required status checks pass
- Branch is up to date with `main` (the protection rule enforces this)
- Branch is deleted on merge (automatic)

## Release tags

Releases are cut by tagging `main` with `vMAJOR.MINOR.PATCH`. Tag triggers
the build pipeline. Don't tag from feature branches.
