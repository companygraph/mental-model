# Governance as data — research report

Research, asked by the Owner; the state as of 2026-10-15. Question: which checks hold a company's model and the repositories around it, where each one runs, and on which level of the levels talk (<https://companygraph.io/talks/levels/>) it sits. Three passes, as asked: the CI pass (scripts, in a hook or a workflow), the agent pass (skills, seats, the agent harness) and GitHub's own checks (rulesets, settings, environments).

Read at: meta-model v0.94.0, conventions v1.52.0, companygraph/mental-model 1b505ba, guestgraph/mental-model bd1aa8c, robertblust/mental-model f2ef125, obsidian-plugin v0.34.0, and GitHub's settings by `gh api` on the 21 repositories of the family, as `conventions/REPOSITORIES.md` lists them. Every version and count is as read on these dates and moves.

## At a glance

| Measure | Now |
| --- | --- |
| Repositories that merge only with a merge commit | 21 of 21 |
| Repositories with secret scanning and push protection | 21 of 21, and on by default for new repositories in both organizations |
| Repositories whose release tags only an admin can create, move or delete | 21 of 21 |
| Repositories where only the Owner's account can push to main | 15, companygraph and guestgraph; robertblust's 6 have the Owner as their only collaborator |
| Meta-model release the seat check runs at | the one the governing instance's manifest names, wherever it runs |
| Conventions release of the members | v1.52.0, all 20 |
| Rules with a control | companygraph 17 of 17 (20 controls), guestgraph 17 of 17 (20 controls), robertblust 11 of 11 (15 controls) |

## The levels

From the talk, each level adds one thing that reads from the model:

| Level | Name | What it adds | Where it runs |
| --- | --- | --- | --- |
| 1 | Model | `init` writes core at a release, the manifest, the check, the agent skills, a commit hook | a laptop: CLI, git hook, agent session |
| 2 | Gated | the same check on every pull request; main protected; a repository off GitHub takes git hooks instead | GitHub Actions, GitHub ruleset, or git hooks (`--gate git`) |
| 3 | Governed | one Markdown form, pins and which are behind, `adopt` for repositories without a model, seat-authored commits, rules, risks and controls as pages | the conventions job, family report and resync, the seat check, GitHub's org and repo settings, the agent's own rules |
| 4 | Served | read-only MCP server and chat answer from the model at one named commit | Cloud Run deploy jobs, server and chat runtime |
| 5 | Published | the site draws its pages from the model at a pinned commit; the editor reads the same files | the site's `verify` job, GitHub Pages, the Obsidian plugin |

The talk puts the editor at level 5 ("the editor reads the same files"); the editor runs the level 1 check while typing. Kept at 5 here as the talk has it.

## A. CI pass — scripts

Where a check runs both in a hook and in a workflow, it is the same script at the same release.

### Level 1 and 2 — the instance

| Check | What it enforces | Executed in | Trigger | Result | Level | Rests on in the model |
| --- | --- | --- | --- | --- | --- | --- |
| Instance checks (55 named checks, R-rule families R2–R20; three of them note and fail nothing) | every page holds to the schemas of the core and packs it vendored | `companygraph check` (CLI); job `companygraph / companygraph` (meta-model `instance-check.yml`, reusable, required); git-gate `pre-commit`; editor plugin | on demand; PR and push to main; commit; while editing | failure, or note | 1 run, 2 required | feature Checks an instance runs; concept Check; bounded context Checking; use case Check a change against the schemas |
| Pack checks (`PACKS` table: oneSided, oneOf, refKind, labels, acyclic, once, within, inherits, carries, atMostOne) | each pack's own constraints, declared as data, run by the same checker | same as above | same | failure | 1–2 | concept Pack |
| Tooling pin guard | the checker is the release the manifest names; refuses a newer vendored core or a pack the checker does not ship | `check-instance.mjs` (inside every run above); editor plugin warns instead | every run | refusal | 2 | concept-design Tooling pin; requirement An instance is checked only against the release it adopted; event Run refused |
| Vendored file hashes | every vendored core, pack and skill file matches the sha256 the manifest recorded | `check-instance.mjs` | every run | failure | 2 | control A vendored copy is held to the release it names; aggregate Manifest |
| Gate value | the manifest's `gate` is github, git or none | `check-instance.mjs` | every run | failure | 2 | — |
| `judge/known.md` rows | an accepted judge finding names a real page, owner and rule; a lapsed row is noted | `check-instance.mjs` | every run | failure; note when lapsed | 1 | — |
| What a run left | a passing run still says it did not judge any `## Writing rules` (R0) and which types had no schema | `check-instance.mjs` | every run | information | 1 | requirement A check that passes says what it left |
| Markdown form | markdownlint-cli2 0.23.2 plus `paragraph-on-one-line` and `table-delimiter-row` | `companygraph form`; inside `check`; instance job; `repository-check.yml` for adopted repositories; editor rewrites on save | on demand; PR and push | failure (editor: rewrites) | 1 in an instance, 3 in an adopted repository | feature A repository is held to one form and told which pins are behind |
| An id never changes | an id already on main is never changed (R18) | `companygraph ids --range`; instance job (PR only); git-gate `pre-commit`; meta-model `verify` for schema ids | PR; commit | refusal (exit 3) | 2 | control An id, a decision and a label are held as they were; rule What is cited from outside the model is not rewritten |
| A decision is not rewritten | a kept page changes only its status and one dated closing sentence | `ids --range` (`keptChangesOf`) | PR; commit | refusal | 2 | same |
| A label stays with its item | invariant, scenario and use-case step labels are not moved, swapped or reused | `ids --range` (`labelChangesOf`) | PR; commit | refusal | 2 | same |
| Git gate | refuses unstaged or untracked changes, runs `check`, `ids` and each pins.json `verify` command; a merge is gated like a commit | `pre-commit` and `pre-merge-commit`, written only with `--gate git` | commit, merge | refusal, also when a check cannot run | 2 | talk: "a repository that never reaches GitHub takes hooks in git" |
| `init`, `adopt`, `upgrade` refusals | no edited vendored file, no move to an older release, no Markdown outside the new release's form, no seat-migration conflict | CLI | on demand | refusal; `upgrade` reports after moving | 1 | feature An instance is made and kept from one command; decision Core is vendored into an instance at a release its manifest names |

### Level 3 — governed

| Check | What it enforces | Executed in | Trigger | Result | Level | Rests on in the model |
| --- | --- | --- | --- | --- | --- | --- |
| Seat author and trailers | an author at the instance's domain is a declared seat, listed in the `executed-by` of the Phase its trailers name; Process, Phase and, where the process has tracks, Track are present once | `companygraph commits`, at the release the governing instance's manifest names, everywhere it runs: `commit-msg` hook; instance job (PR); conventions job (PR, in repositories without a manifest) | commit; PR | refusal (exit 3); the hook lets a commit through with a warning when it cannot run | 3 (hook installed at 1) | decision An agent's commit is authored by the seat it held; rule A commit keeps the author it was made with |
| Conventions release pin | the conventions workflow release equals the `conventions.json` tag | job `conventions / conventions` (conventions `check.yml`, reusable, required in every repository but conventions itself) | PR and push | failure | 3 | control A vendored copy is held to the release it names |
| `conventions-sync check` | the vendored `conventions/`, root lint config, `CLAUDE.md` and the AGENTS.md block are the pinned release | same job | PR and push | failure | 3 | same |
| `conventions-check` | American spelling, no closed em dash, no unclosed fence, README H1 equals the title REPOSITORIES.md gives, every dependabot.yml ignores the family's own repositories | same job | PR and push | failure | 3 | core R14 (names are American English) |
| `conventions-format` | the same Markdown form as `companygraph form` | same job | PR and push | failure | 3 | — |
| `companygraph pins` | each pins.json pin is current, behind, unknown, unmanaged, family or missing | CLI | on demand | note; fails only on a missing or invalid entry | 3 | concept Pin |
| Family resync report | members' pins behind, unreleased work on main, failing checks on members' main | conventions `report.yml` → issue "Family resync report" | weekdays at 17:00 Zurich; dispatch | report | 3 | — |
| Family resync | each member's pins.json `verify` passes after its pins move; waits on required checks; refuses beside a live lock or an open `resync-` PR it did not open | `family/resync.mjs`, started by the Owner | on demand | blocks that member; refuses to start | 3 | control A family resync refuses to start beside another; rule One session holds a piece of shared work |
| Release manifest (meta-model) | core and package versions agree; both reusable workflows' `ref:` is `v<version>`; the tag on HEAD matches | meta-model job `verify` (`verify/check.mjs`) | PR and push | failure | 3 | control A vendored copy is held to the release it names |
| Rule citations | every R-number cited in shipped code is defined in core/CONVENTIONS.md | meta-model `verify` | PR and push | failure | 3 | — |
| Types build | committed type declarations equal what the JSDoc builds | meta-model, mcp-server and chat-server `build:check` | PR and push | failure | 3 | — |
| Merges Past Their Checks | merges that bypassed a required check, per week | mcp-companygraph-io `kpi.yml` → mcp-server `kpi-google.yml` → bucket | weekly | measurement | 3 (measures 2) | KPI Merges Past Their Checks; control Main takes a change only through a green, current pull request |

### Level 4 — served

| Check | What it enforces | Executed in | Trigger | Result | Level | Rests on in the model |
| --- | --- | --- | --- | --- | --- | --- |
| Host build | snapshot, JSON-LD, tests, image | `deploy / build`, `chat / build` (mcp-server and chat-server `deploy-google.yml`, reusable, required on the three MCP hosts) | PR and push | failure | 4 | bounded context Serving; concept-design Snapshot |
| Terraform | `fmt -check`, `validate`, plan on PR (commented), apply on push | `deploy / terraform`, `chat / terraform`; `terraform` in mcp-server and chat-server | PR and push | failure | 4 | — |
| Served commit | after apply, the live server's `list_types` names the commit `source.json` pins | `deploy / terraform` post-deploy step | push to main | failure | 4 | control A deployed server is asked which commit it serves; rule A state is read again before it is relied on |
| Three-place pin | package.json, workflows and the installed module agree; the page and health name the release | mcp-server `deploy/test`, run by each host | PR and push | failure | 4 | — |
| Chat portability | chat-server code names no instance | chat-server `test` | PR and push | failure | 4 | — |
| Chat deployment report | weekly report of the chat deployment | chat-server `report-google.yml` via the hosts | weekly | report | 4 | — |
| Registry publish | tests, then `server.json` to the MCP registry, signed with a key only the `registry` environment holds | `publish.yml` (and `registry.yml` for mcp.companygraph.io) | `v*` tag, after the Owner approves | failure | 4 | control A registry entry waits for a release tag and the Owner |

### Level 5 — published

All but the last two run in the site's job `verify`, required by the ruleset, on companygraph.io and blust.ch.

| Check | What it enforces | Trigger | Result | Rests on in the model |
| --- | --- | --- | --- | --- |
| `pages:check` | every region drawn from the model equals what the pinned model draws | PR and push | failure | control Pages drawn from the model are held to it; rule The model is corrected first |
| `build:check` / `model:check` | committed `model.json` (and `example.json`, `company.json`) equals the parse of the pinned commits | PR and push | failure | same |
| `design german stale` | an English edit did not leave its German behind; a `German-unchanged:` trailer releases it | PR | failure | control German left behind is found; rule German follows reviewed English |
| `pin:check` | how far `source.json` pins are behind | PR and push | note, never fails | concept Pin |
| `design:check` | design-synced files equal the pinned design release | PR and push | failure | — |
| `og:check`, `test:og` | the share card's stamp equals its recipe | PR and push | failure | concept-design Share card |
| `sitemap:check` | each `lastmod` is the page's last commit | PR and push | failure | — |
| Playwright `verify` | per-page checks: fonts, tokens, contrast, fences, SEO, German typography, header and footer, storage keys, links | PR and push | failure | — |
| `design links` | every own link resolves in the checkout | PR and push | failure | — |
| Clips, `test:d3`, blust.ch `test:cost` and `test:dupes` | narration not stale; vendored d3 byte-equal; cost arithmetic; cross-site duplication | PR and push | failure | — |
| External links | weekly, into an issue (`links.yml`) | weekly | report | — |
| Editor plugin | runs `checkInstance` at its bundled release; refuses an edit that removes a declared heading or changes an id; rewrites the form on save | Obsidian, while editing (400 ms debounce) | marks; refused edit | feature Checks while a file is edited |

Shipped but not wired: `pdf:check` (design `decks/check`); no site runs it.

## B. Agent pass

| Check | What it enforces | Executed in | Trigger | Result | Level | Rests on in the model |
| --- | --- | --- | --- | --- | --- | --- |
| `companygraph-validate` (R0) | copies the mechanical check's output, then judges every entity against its schema's `## Writing rules` | agent skill, local session | "before every commit" (robertblust/mental-model AGENTS.md); no script requires it | report; blocks nothing | 1 | concept-design Agent pass; bounded context Procedures |
| `companygraph-judge` / `companygraph judge` | asks TypeSafe Jev each writing rule per page; flags a verdict below 0.6 | agent skill and CLI, with consent per run and a key | on demand; never in CI | advisory | 1 | — |
| Validate step of `companygraph-profile` and `companygraph-company` | a run writes only what holds, and hands it back uncommitted | agent skill | at the end of each run | report | 1 | aggregate Procedure run; event Change left for approval |
| Reviewer | reads the diff and the checks' output, and the implementer's report as a claim | Reviewer seat, Delivery process | after each task, and once over the branch | finding | 3 | control A reviewer reads the output, not the report; rule A check counts only when its output was seen |
| Merge refusal | a merge without the Owner's word in that conversation is refused | the agent harness's auto-mode classifier | before the command runs | refusal | 3 | control An agent's permissions refuse a merge it was not given; rule The Owner's word merges |
| Message from another session | a message from another session is delivered as that session's, grants no permission, and is judged against the receiving session's own conversation | the agent harness | every message between sessions | refusal by the permission layer; the rest rests on the agent | 3 | control A message from another session carries no word of the Owner's; rule A refusal is not carried out by another session |
| Worktree guard | refuses `git worktree remove` on a worktree holding an unfinished plan's ledger | a hook the agent harness runs before every shell command, on the Owner's machine | before the command runs | refusal | 3 | control An agent's hook refuses removing a worktree that holds a plan; rule A worktree is removed only once its plan is done |
| Branch deleted after its merge | the pull request is read as merged in a step of its own before the branch, worktree and remote branch go | Implementer seat | end of Integrate | manual | 3 | control The Implementer reads the merge before deleting the branch; rule A branch is deleted only after its merge is confirmed |
| A request's gap, never its company | only the missing entity, field or rule is asked for; an offered name stays out; the vocabulary skill refuses a spec commit that still carries a name to keep out | Owner in Understand; the vocabulary skill | every feature request; every vocabulary spec | manual; the skill refuses | 3 | control A request is asked for its gap and never its company; rule Nobody is asked which company a request comes from |
| A new type's unit | core only where companies of more than one kind show it, a pack for one kind, a wait for one company | Specifier, through the vocabulary skill | every new type | manual | 3 | control A new type's unit follows the companies that show it; rule No type enters core before an instance had to be written with it |
| A guest's data in a request (guestgraph) | every request and comment read for a guest's data, which is edited out and deleted from the edit history | Owner in Understand | every feature request | manual | 3 | control A guest's data in a request is taken out of it; rule A feature request carries no guest's data |
| Claim check of a chat answer | each claim is read back against the tool answers it rests on; one they do not carry is marked, in English answers | chat-server, Jev, at runtime, turned on in each deployment's `chat.json` | every answer | marks a claim | 4 | control A chat answer's claims are read back against the model; rule Nothing claims what the model does not hold |
| Chat notice | an AI answers, where the message goes, before anything is sent | design `chat.js` | every chat opened | preventive | 4–5 | control The chat says who answers before the first message; rule A visitor is told an agent answers |

Agent rules with no script behind them, written in conventions WORKING.md and WRITING.md, the repositories' AGENTS.md and the agent's memory: one branch per change in a sibling worktree; an agent commits only when asked; re-read state before relying on it; never `gh stack sync`; `git config user.email` before the first commit (GitHub's `commit_author_email_pattern` is not on this plan); never rename a required job without its ruleset; claim only what was measured; never write a number that moves. Each rule of the three models has a control, manual where no machine holds it.

## C. GitHub's own checks

| Feature | What it refuses | Where | Level | Rests on in the model |
| --- | --- | --- | --- | --- |
| Ruleset `protect-main` on the default branch | deletion, force push, any change but through a pull request (0 approvals, stale reviews dismissed) | all 21 | 2 | control Main takes a change only through a green, current pull request |
| Required status checks, strict | a merge until the named checks pass on a branch up to date with main | all 21 | 2 | same; rule A state is read again before it is relied on |
| Merge commit only | squash and rebase merges | all 21: squash and rebase off in every repository's settings; several rulesets also allow merge alone | 3 | rule A commit keeps the author it was made with |
| Admin bypass | — (allows an admin past the ruleset) | 20; guestgraph/service-conventions has no bypass actor | 2 | measured by KPI Merges Past Their Checks |
| Push restriction to robertblust (classic protection) | a push or merge to main by anyone else | the 8 companygraph and 7 guestgraph repositories; a personal account's repositories cannot take one, and robertblust's have the Owner as their only collaborator | 3 | control Only the Owner's account changes main; rule The Owner's word merges |
| Ruleset `protect-release-tags` on `v*` | creating, moving or deleting a release tag, but by an admin | all 21 | 3 | control A release tag stays where the Owner put it |
| Secret scanning with push protection | a push carrying a secret GitHub recognizes, unless the pusher gives a reason, which GitHub records | all 21, and on by default for new repositories in both organizations | 3 | control A secret is refused at the push; rule A secret is never written into a repository |
| Dependabot | alerts on all 21, security update PRs on 12, version updates on the 14 with a dependabot.yml (cooldown 0 on 7, no cooldown key on 7); family repositories ignored, held by `conventions-check` | per repository | 3 | — |
| Workflow token read, Actions cannot approve | a workflow writing without declaring it; Actions approving a PR | all 21 | 2 | — |
| Environment `registry` | a registry publish from anything but a `v*` tag, or without robertblust's approval; the signing key is its secret alone | the three MCP hosts | 4 | control A registry entry waits for a release tag and the Owner |
| Environment `github-pages`; Pages from `main` | a Pages deployment from another branch | the three sites | 5 | — |

Not used anywhere: CODEOWNERS, required approvals above 0, signed commits, linear history, conversation resolution, code scanning, auto-merge, the update-branch button, delete-branch-on-merge, an org-level ruleset. Org: companygraph's base permission is write; guestgraph's is read. Not readable without `admin:org`: org rulesets and the org Actions policy.

## Open points

- The controls of the three models are on each instance's main branch and not yet on companygraph.io, blust.ch, guestgraph.io or the MCP hosts, which pin each model by commit; the content re-pin waits for the Owner's word.
- An issue template that warns against a guest's data before anyone writes it would make guestgraph's guest-data control preventive, where today it acts after the fact.
- The rule "No type enters core before an instance had to be written with it" measures an instance, and its control counts companies in the sources; tightening the rule's words to what the skill counts is open.
- The rule "Nothing claims what the model does not hold" has a control only for the chat's answers; specifications and pages are held by whoever writes them.

## Questions this raises for the meta-model

- A control's `## How it is carried out` holds what this research had to dig for (executed in, trigger, required or not) as prose. Whether a control should name where it executes as a reference (a landscape `system` or `service`, a data object such as the repository) and the level it belongs to is open.
- The levels are a talk, not entities. Whether a level is a concept page the controls and features point at, or stays prose, is open.

## Sources

- meta-model: `bin/check-instance.mjs`, `bin/companygraph.mjs`, `lib/checks.mjs`, `lib/instance-files.mjs`, `lib/plan.mjs`, `lib/seats.mjs`, `lib/pins.mjs`, `lib/form.mjs`, `lib/known.mjs`, `.github/workflows/{instance-check,repository-check,ci,conventions}.yml`, `verify/check.mjs`, `agents/claude/skills/`, `docs/superpowers/specs/2026-09-30-a-skill-for-new-vocabulary-design.md`.
- obsidian-plugin: `src/model.ts`, `src/main.ts`, `src/manifest.ts`, `src/headingmarks.ts`, `src/idlock.ts`.
- conventions: `.github/workflows/{check,ci,report}.yml`, `conventions/{conventions-sync,conventions-check,conventions-format,hooks/commit-msg,WORKING.md,WRITING.md}`, `family/resync.mjs`.
- Sites: companygraph.github.io and robertblust.github.io `.github/workflows/{ci,conventions,links,indexnow}.yml`, `package.json`, AGENTS.md.
- Servers: mcp-server `.github/workflows/{test,deploy-google,deploy-azure,kpi-google,registry}.yml`, `deploy/test/`; chat-server `.github/workflows/test.yml`, `lib/verdict.mjs`; the three hosts' `deploy.yml`, `publish.yml` and `chat/chat.json`.
- Agent harness: the Owner's permission settings and the worktree hook on the Owner's machine.
- Model: the three instances' `model/controls/` and `model/rules/`, `model/kpis/merges-past-their-checks.md`; `list_checks` of mcp.companygraph.io.
- GitHub: `repos/{o}/{r}`, `/rulesets`, `/branches/{b}/protection`, `/environments`, `/pages`, `/vulnerability-alerts`, `/actions/permissions`, `orgs/{o}`; GitHub's documentation on push protection, rulesets, environments and edit history.
- Talk: <https://companygraph.io/talks/levels/>
