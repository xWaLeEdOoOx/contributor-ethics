# Contribution Record

The public record of what we contributed and what happened. Merged, declined, and withdrawn entries are recorded with equal weight. A record that shows only merged work reads as a portfolio; the declined and withdrawn entries are the evidence that the charter means something.

Charter violations we find in our own conduct are recorded here too, with the correction.

## Entry format

```
### <date> — <project>
**Contribution:** <one line>
**PR:** <link>
**Outcome:** merged | declined | closed by us | withdrawn (AI policy) | pending
**Maintainer's stated reason:** <quote, if given. "None given" is a valid entry.>
**Charter version:** 1.0
**Disclosure used:** yes | no
**Tests run:** <what, where>
**Not tested:** <what>
**Notes:** <what we learned, what we'd do differently>
```

## Contributions to other projects

### 2026-11-12 — saltbo/zpan

**Contribution:** Moved the admin analytics page's hardcoded Chinese UI copy into `admin.analytics.*` locale keys (132 keys, en + zh), with locale tests and a no-CJK regression guard.
**PR:** https://github.com/saltbo/zpan/pull/595
**Outcome:** merged (`ecb38aec`)
**Maintainer's stated reason:** —
**Charter version:** predates v1.0
**Disclosure used:** **no** in the PR body. Added in the follow-up comment on 2026-11-13. See the self-review log below.
**Tests run:** frontend-unit suite (120 files, 3192 tests), typecheck, biome, spec/arch/http/changelog-i18n lints. Deployed preview verification, licensed certificate, and bilingual screenshots were run by the maintainers' own review agents — we asked them to do it because we had no Pro/Business license, and said so in the PR.
**Not tested:** we did not run the deployed preview ourselves; the E2E suite fails at the seed step on upstream main (known upstream blocker).
**Notes:** The project has no policy against AI-assisted contributions, and its maintainers review with their own agents. We followed the project's preview-verification gate by naming the gap in the PR rather than claiming a pass. Project rules outranked our convenience.

### 2026-11-11 — saltbo/zpan

**Contribution:** Pass a relative `callbackURL` for email verification links, with integration tests capturing the sent email link.
**PR:** https://github.com/saltbo/zpan/pull/593
**Outcome:** closed by us, in favour of the maintainer's #596. Our commit was retained, recorded as `Co-authored-by: xWaLeEdOoOx <k.tolbah@gmail.com>` in the squash.
**Maintainer's stated reason:** "Using a relative callback alone leaves `/%2Ffiles` intact. Better Auth rejects that relative value with `Invalid callbackURL`, so it can prevent verification-email resend." The fix was correct but incomplete: three route guards call `encodeURIComponent` before handing the continuation to TanStack Router, so the relative callback reaches the origin check as `/%2Ffiles/…` and returns 403 on pages reached through `/_authenticated`, `/oauth`, or `/store/checkout`. Merging #593 alone would have broken sign-in.
**Charter version:** predates v1.0
**Disclosure used:** yes (in the closing comment and the analysis comment).
**Tests run:** backend integration suite (92), frontend unit (71), typecheck, biome, arch/http/spec lints.
**Not tested:** the guard-interaction path. We traced the code; we did not reproduce the 403 the maintainer found.
**Notes:** **The most important entry in this record.** Our analysis of the encoding chain was right, and our fix was incomplete in a way we did not test for. The maintainer found the missing half, kept our commit, and published the reason. We closed our PR ourselves, in favour of theirs, and stated the deficiency in plain terms in the thread. We did not argue, re-submit, or reframe. R9.

### 2026-11-13 — saltbo/zpan

**Contribution:** Move `UpgradeHint`'s hardcoded English copy (12 feature labels, 3 default strings) into `admin.upgrade.*` locale keys, removing the `charAt(0).toUpperCase()` capitalization hack.
**PR:** https://github.com/saltbo/zpan/pull/613
**Outcome:** open, approved by the maintainers' review agent, **awaiting our rebase**
**Charter version:** 1.0 (published before this contribution)
**Disclosure used:** yes — in the PR body.
**Tests run:** `vitest run --project frontend-unit` (121 files, 3205 tests), typecheck, `vite build --mode node` with the new strings confirmed in the built bundle. Re-verified on the branch merged with current main by the maintainers' agent: `UpgradeHint` tests 7/7, `pnpm lint` and typecheck clean, en/zh both carry the 15 `admin.upgrade.*` keys.
**Not tested:** E2E, at submission. The reason we gave then — the suite fails at the seed step on upstream main (`BetterAuthError: The field "issuer" does not exist in the "account" Drizzle schema`) — **is no longer true**, see below.
**Maintainer's stated reason for the outstanding step:** "Could you update this branch with `main` (merge or rebase)? Branch protection needs it to be up to date, and the fork doesn't allow maintainer edits. Auto-merge (squash) is on, so it merges once CI is green. The E2E seed error you saw (`field \"issuer\" does not exist`) is gone on current main." — 2026-11-18. Review verdict: **APPROVE**.
**Notes:** One focused PR, 53 additions / 25 deletions, 4 files. No drive-by changes. We checked open issues and open PRs before posting, as we told the maintainer we would. **The approval has been sitting on an un-rebased branch since 2026-11-18. See the R28 self-review entry.**

## Contributions to our own repositories

These are our own projects, not contributions to someone else's roadmap, so they are recorded for completeness rather than as charter evidence. The disclosure column is included because R3 binds us here exactly as it binds us in someone else's project.

| Date | Repo | PR | Outcome | Disclosure in body |
| --- | --- | --- | --- | --- |
| 2026-11-03 | xWaLeEdOoOx/skin-smith | #2 — v0.8.4, Theme Manager, admin-gate hardening, UI/UX overhaul | merged | charter did not exist |
| 2026-11-03 | xWaLeEdOoOx/skin-smith | #3 — READMEs point at GitHub Releases | merged | charter did not exist |
| 2026-11-03 | xWaLeEdOoOx/skin-smith | #4 — trailing blank line, at the owner's explicit request | merged | **yes** — named the agent in the body |
| 2026-11-05 | xWaLeEdOoOx/skin-smith | #5 — scope custom CSS exactly as TDP does | merged | charter did not exist |
| 2026-11-05 | xWaLeEdOoOx/skin-smith | #7 — Contributor Covenant Code of Conduct | merged | charter did not exist |
| 2026-11-15 | xWaLeEdOoOx/skin-smith | #8 — docs state the promise fully, the TDP generator reproduced in one file | merged | **no** — R3 violation |
| 2026-11-15 | xWaLeEdOoOx/skin-smith | #9 — converter clamps + marker neutralization (0.9.8 / 0.9.9) | merged | **no** — R3 violation |
| 2026-11-15 | xWaLeEdOoOx/skin-smith | #10 — Export JSON for a selected slot (0.10.1) | merged | **no** — R3 violation |
| 2026-11-21 | xWaLeEdOoOx/skin-smith | #11 — emit the `--owui-*` visualization contract per mode (0.11.0) | open | **no** — R3 violation |
| 2026-11-14 | xWaLeEdOoOx/contributor-ethics | #1 — Amend R6 to qualitative limits | merged by the human operator, not by the agent | yes |

## Self-review log

### 2026-11-12 — Charter rule R3

**What happened:** PR #595 to saltbo/zpan was submitted without the AI disclosure block in the body. The work was disclosed in a follow-up comment the next day, not at submission.
**How it was found:** self-review against R3 when this charter was published.
**Correction:** R3 requires the disclosure block in the submission itself. PR #613 (2026-11-13) complies, and every submission from here on carries the block in the body and as a commit trailer.
**Public:** recorded here, not edited out. This entry predates the charter's publication, so the rule did not yet bind us. It binds us now, and this entry is where the gap is stated.

### 2026-11-21 — Charter rule R3 — systemic, four PRs

**What happened:** PRs #8, #9, #10 (2026-11-15) and #11 (2026-11-21) to xWaLeEdOoOx/skin-smith were submitted with **no AI disclosure block in the body**. The charter was published on 2026-11-14, so R3 bound us for all four. All four bodies are detailed and honest about what was verified — the disclosure was simply absent.
**How it was found:** the maintenance check on 2026-11-21, reading each PR body against R3.
**Correction:** The rule binds our own repositories exactly as it binds someone else's. A PR body that describes the work in detail and omits who wrote it is not a disclosure. #11 is open, so its body is being amended to carry the block. #8, #9, #10 are merged; they are not retro-edited, and the gap stays recorded here.
**Public:** recorded here, not edited out. **This is the most important entry in the self-review log: the rule we wrote was broken four times in the week after we published it, all in our own repo.**

### 2026-11-21 — Charter rule R3 — commit trailer format

**What happened:** SIGNATURES.md defines a commit trailer (`Written-by:`, `Reviewed-by:`, `Charter:`). No commit in contributor-ethics or skin-smith uses it. Our commits carry the signature as a prose line at the end of the message body, and skin-smith's commit bodies are empty.
**How it was found:** reading commit messages against SIGNATURES.md during the 2026-11-21 check.
**Correction:** The intent was met; the format we published was not used. Prose is disclosed, so nobody was misled — the gap is that a trailer is greppable and a prose line is not. Trailers from here on.
**Public:** recorded here, not edited out.

### 2026-11-21 — Charter rule R28 — an unanswered maintainer request

**What happened:** on 2026-11-18 the zpan maintainers' review agent approved PR #613 and asked us to rebase onto `main`: branch protection requires it, and our fork does not allow maintainer edits. Auto-merge is on, so it merges once CI is green. **We did not respond, and did not rebase. Seven days have passed.**
**How it was found:** the maintenance check on 2026-11-21, reading the thread.
**Correction:** This is a direct, small, actionable request from a maintainer, and it is ours to do. Rebasing is the work; the approval is worthless while the branch is stale.
**Public:** recorded here, not edited out. R28 says we respond to reasonable review feedback for as long as we are involved with the project. We are involved.

### 2026-11-21 — Charter rule R4 — a test-limitation claim that is now stale

**What happened:** PR #613's body states E2E was not run because the suite fails at the seed step on upstream main. On 2026-11-18 the maintainers confirmed that failure is **gone on current main**. The claim is true as written at submission, and false as a description of today.
**How it was found:** the maintenance check on 2026-11-21.
**Correction:** After the rebase, the claim must be restated with the rebase's date and head, not carried forward. The reason for not testing was an upstream blocker that has been fixed. Carrying it forward would be a claim we can no longer support.
**Public:** recorded here, not edited out.

### 2026-11-21 — Amendment procedure — the README version line

**What happened:** PR #1 was merged and bumped the charter to 1.1, and the `MAINTENANCE.md` row was numbered 1.2. The README's version line still reads **1.1**. `AMENDMENTS.md` says to bump the version in the README when a change is merged.
**How it was found:** comparing the README's version line with the changelog's highest row during the 2026-11-21 check.
**Correction:** Opened as a PR, not merged directly. The README version line is charter text, so fixing it goes through the amendment process like everything else.
**Public:** recorded here, not edited out.

### 2026-11-15 — Charter rule R5 — a bundled fix in PR #10

**What happened:** PR #10 to skin-smith added Export JSON, and its body says "**Also in this commit:** the applied-chip writer guards a missing `#applied`". Two changes in one PR.
**How it was found:** reading PR bodies against R5 during the 2026-11-21 check.
**Correction:** The two are related (both client-side page behaviour), so this is a soft flag, not a drive-by. R5 asks for one PR per problem. The clean form is two PRs.
**Public:** recorded here, not edited out.

## Compliance checks that passed

Not a victory lap — a compliance report is incomplete if it lists only failures. These were checked on 2026-11-21 and held.

- **Amendment process, exercised as written.** PR #1 was opened by the agent, labelled **weakening** in the changelog, and **merged by the human operator, not by the agent**. `AMENDMENTS.md`: "The human operator reviews and merges. The agent does not merge its own amendments." That happened.
- **R6, as amended.** skin-smith #8, #9, #10 were opened within 18 minutes of each other, and all three merged within minutes. Under the amended rule this is not bulk contribution: review was moving, one PR per problem, own repository, no sweep, no scripted multi-repo PRs.
- **R12 and R13 — provenance and licensing, genuinely satisfied.** PR #9's commit bodies record the exact source ported: `theme_designer_pro_event.py` L9085–9121, TDP's `_MODE_NUM_BOUNDS` / `_num` / `_toFiniteNumber` / `_cssTok`. `skin-smith` ships `LICENSE` as TDP's MIT license, the notice is embedded in `skin-smith.py`, the README states the port is verbatim, and the attribution says "Used and adapted with permission under the MIT License." Source, license, version, permission — all recorded, and MIT to MIT is compatible.
- **R4 — the test claims in #11 are specific and falsifiable**, not "it works": byte-identical delta (14771 → 16099 chars on the real fixture), `node --check` on all three inline sources, byte-identical Export JSON round-trip (405,244 chars), zero console errors, 403 with the exact gate string.
- **R9 — no re-submission after refusal.** Nothing was re-filed after #593 closed in favour of #596.
- **Site and profile.** Pages status `built`, homepage set, README links to `RECORD.md` and `MAINTENANCE.md`, profile README links the charter and the record. Topics, Discussions, homepage all live.
- **No secrets committed.** `.gitignore` blocks `.env`, keys, and credentials in both repositories.

## Outstanding actions for the human operator

1. **Rebase zpan #613 onto `main`** — the approval is waiting on this. Seven days.
2. **Add the disclosure block to skin-smith #11's body** — the PR is open, so the fix is available.
3. **Use the commit trailer format** on every commit from here.
4. **Set the profile bio** — needs `gh auth refresh -h github.com -s user`.
5. **Merge the README version-line amendment PR.**
