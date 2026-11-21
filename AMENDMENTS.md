# Amendments

## Policy

This charter binds us to a position we can be measured against. We cannot quietly rewrite it.

- Every version carries a version number and an effective date.
- Amendments are made through a **public pull request to this repository**, in the open, with the reason stated.
- Amendments that weaken a commitment are treated as significant, and are labelled as weakening in the changelog. No silent softening.
- We do not amend the charter to excuse a contribution we have already made.
- Once a version is published, we cite the version we are operating under, not "the charter".
- A maintainer is entitled to rely on the version in force at the time of a contribution.

## Version numbering

- **Major (x.0)** — a commitment is added, removed, weakened, or reversed.
- **Minor (x.y)** — clarifications, added rules, expanded commitments, editorial changes.
- **Patch (x.y.z)** — wording, links, typos. No change of meaning.

## Amendment process

1. Open a PR against this repository titled `Amend <rule> — <reason>`.
2. State the rule affected, the reason, and whether the change strengthens or weakens the commitment.
3. The human operator reviews and merges. The agent does not merge its own amendments.
4. Bump the version in the README, add the changelog entry, update the effective date.
5. If any published contribution relied on the old wording, note it in [RECORD.md](RECORD.md).

## Changelog

| Version | Date | Change | Direction |
| --- | --- | --- | --- |
| 1.0 | 2026 | Initial charter published. | — |
| 1.1 | 2026-11-14 | R6 numeric limits (2 open PRs per project, 1 PR per issue) replaced with qualitative rules: no sweeps, no scripted PRs, one PR per problem, stop opening when a project's review queue is stalled. | **weakening** — the numeric ceiling is removed. The qualitative rules remain checkable from issue and PR history. |
| 1.2 | 2026-11-14 | `MAINTENANCE.md` added — the upkeep procedure, as an operational document outside charter versioning. A link to it is added to the README. The README's version line was left at 1.1 and is brought to 1.2 in the 2026-11-21 amendment. | neutral |
| 1.3 | 2026-11-21 | Clarified what is adoptable: `AGENTS.md` and `MAINTENANCE.md` are internal to one agent on one account and are not charter text. The README says the same. A proposed R32/R33 (the agent's write scope) was withdrawn by the operator on 2026-11-21 and moved to `AGENTS.md`; the charter stays at 1.3 with 31 rules. | **neutral** — a clarification of scope. The withdrawn rules named one agent on one account, which is not general contribution conduct. |
