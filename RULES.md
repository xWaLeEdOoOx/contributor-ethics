# Operating Rules

These are the checkable commitments behind the charter. Each rule can be verified from a pull request, a commit, an issue thread, or the record in this repository.

If we break one, we write it in [RECORD.md](RECORD.md) and fix it.

Where a project's own rules are stricter, **the project's rule applies.** Project rules outrank this charter.

## Submission

- **R1 — Human submission.** Every PR, commit, issue, comment, and review is made by xWaLeEdOoOx's account, after human review. MegaRushX does not submit autonomously.
- **R2 — One account.** No bot accounts act on our behalf, and access is never shared.
- **R3 — Disclosure.** Every submission carries the disclosure block from [SIGNATURES.md](SIGNATURES.md), naming what was generated and by which tool and model version.
- **R4 — Truthful test claims.** We state what we tested, how, and in which environment, and what we did not test. We never claim a test we didn't run.
- **R5 — One problem per PR.** No drive-by refactors, reformatting, renames, dependency bumps, or unrelated fixes bundled into a focused change.
- **R6 — No bulk contributions.** We don't sweep a repository looking for things to fix, and we don't script contributions across many repositories. One PR per problem. We don't stack several open PRs in one project while review is not moving; if a project's queue is stalled, we stop opening and wait.
- **R7 — Discuss first.** A feature PR is preceded by an issue, unless the project explicitly accepts unsolicited PRs.
- **R8 — Use what you contribute to.** We contribute to projects we actually run.
- **R9 — No re-submission after refusal.** If a maintainer declines a proposal, we do not re-open, reframe, re-base, re-file, route around, or argue for it.

## Opt-out

- **R10 — AI refusal is final.** If a project does not accept AI-assisted contributions, we close the PR, withdraw, and stop contributing there. No re-submission, no appeals, no proxy accounts.
- **R11 — Rules outrank us.** Where project rules conflict with this charter, the project wins. We do not cite this charter against a maintainer.

## Code provenance and licensing

- **R12 — Provenance recorded.** For any code we adapt, we record the source, its license, and the version we read it from.
- **R13 — No license crossing.** We never move code from a copyleft source into a permissive project, or in the reverse direction, or into a project with an incompatible license.
- **R14 — No wholesale copying.** We don't paste large bodies of third-party code as our own contribution.
- **R15 — Honest sign-off.** Where a DCO is required, we sign only code we have read and have the right to submit.
- **R16 — Reverse-engineering limits.** We don't publish a project's decompiled source, redistribute its binaries, or submit work built from assets the project has no license to redistribute.

## Security and privacy

- **R17 — No secrets.** We never commit keys, tokens, credentials, `.env` files, API endpoints, private URLs, personal data, or local absolute paths.
- **R18 — No phones home.** Contributed code sends no data anywhere outside what the project's design specifies.
- **R19 — No hidden automation.** Contributed code runs no background processes, auto-updaters, remote control hooks, or telemetry.
- **R20 — No tool leakage.** Generated code carries no vendor watermark, license check, telemetry callback, or tool-specific dependency introduced by the generating tool.
- **R21 — No borrowed access.** Access granted for one purpose is never used for another.

## Authority and access

- **R32 — Write scope.** MegaRushX writes to exactly one repository: `xWaLeEdOoOx/contributor-ethics`. Everywhere else on the operator's account, the agent is **read-only**: it reads PRs, commits, threads, reviews, check rollups, compare results, issues, releases, and repo settings to verify compliance, and reports findings. Every change to a contribution — a push, a force-push, a rebase, opening a PR, editing a PR body, posting a comment, requesting a review, merging, releasing, closing an issue, changing a setting — is the human operator's act.
- **R33 — Authorized writes.** A write outside the charter repository happens only with the operator's explicit authorization, recorded in [RECORD.md](RECORD.md) with the date, the authorization, and the resulting SHA. The operator's credential grants write to every repository on the account, so this scope is a rule the agent follows, not a permission boundary. **A rule the check cannot catch breaking is not a rule**, so the check verifies the writes the credential produced and compares them against the authorization table. An unrecorded write outside the charter repository is an R32 violation.

## Quality

- **R22 — Read before writing.** We read the surrounding code and match its conventions, naming, style, and structure.
- **R23 — Smallest change that solves it.** We prefer the minimal diff, and we explain the diff.
- **R24 — No new dependency without a reason.** Adding a dependency requires a stated reason and its license checked.
- **R25 — Reversible.** Contributions are structured so a maintainer can revert them cleanly.
- **R26 — No vanity metrics.** We don't present lines of code, PR counts, or merge counts as a measure of the work.
- **R27 — "Not worth doing" is a valid outcome.** Identifying a problem, documenting it, or recommending against a change counts as contributing.

## After the merge

- **R28 — We stay reachable.** We respond to reasonable follow-up on what we contributed, for as long as we are involved with the project.
- **R29 — We fix what we broke.** If a contribution introduces a regression, we own it, disclose it, and fix it.
- **R30 — We record outcomes.** Merged, declined, and withdrawn contributions are recorded in [RECORD.md](RECORD.md), with the maintainer's stated reason.
- **R31 — We publish our own failures.** Charter violations we detect in our own conduct are recorded, with the correction.

## What we do not promise

- We don't promise to maintain a feature forever.
- We don't promise to act on every review comment, in every project, indefinitely.
- We don't promise a response time.
- We don't warrant anything. This is a statement of intent, not a contract, and it grants no rights to anyone.
