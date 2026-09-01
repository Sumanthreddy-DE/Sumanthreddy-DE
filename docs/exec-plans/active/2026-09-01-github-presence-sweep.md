# GitHub public-presence sweep

## Start here (next session)

Launch Claude Code from `C:\Users\suman\Desktop\Docs\Job\Projects\Sumanthreddy-DE`,
not from `Myself`. The cwd decides which memory slug, `CLAUDE.md`, and `STATE.md`
load, and this work must file under the `Sumanthreddy-DE` slug.

Then paste: *"Read `docs/exec-plans/active/2026-09-01-github-presence-sweep.md`
and execute it."*

This plan is written to be self-contained. The prior session's chat is not needed;
a cold session rebuilds the repo audit with roughly six `gh` calls.

Run phases in order. **0, 1, 2, 4 form a complete result on their own** if the
session is cut short; phases 3, 5, 6, 7, 8 are the long tail.

Before the first change to any repo, state the repo and the change and wait for a
yes, per the approval rule below.

## Context

The job search is live: the CV packet went to MJS on 2026-08-30 and availability is
now immediate. A recruiter who receives that packet will click through to
`github.com/Sumanthreddy-DE`. What they currently find undercuts the CV.

An audit of all 37 repos (27 public) on 2026-09-01 found:

- **10 public repos with no description**, and **8 with a title-only README**
  (10 to 66 bytes, meaning the README says nothing but the repo name).
- **26 of 27 public repos have zero topics.** The one exception is the profile
  repo, tagged `config` and `github-config`.
- **The profile README states availability as "June 2026."** It is September 2026.
  A recruiter reads that as an abandoned profile.
- **Public repos containing material that is not ours to publish**:
  `Production-Engineering-Data-Automation` holds `Bhanu's code.txt` (72 KB of
  another named person's code) plus German business-data files
  (`Baukasten.json`, `Loesungsbibliothek.json`).
- **`The-Dumpster-App`** is public with untouched Lovable boilerplate as its
  README, including a live link to the private lovable.dev project dashboard.
- **Three public repos are empty shells**: `Solidity` (0 KB),
  `nxopen-cad-extractor` (0 KB), `sprachlog` (9 KB, no README at all).
- **Real engineering credibility is invisible.** `NX-Constraints-training`
  (999 KB: dataset, trained Keras model, training and prediction scripts,
  confusion matrix) has a 25-byte README, despite already containing four
  written internal docs that were never promoted.
- **Three public code repos have no license** (`cortex`, `ai-eng-tracker`,
  `anny-booking-bot`), which legally means all rights reserved.
- **Public facts contradict each other.** `Master-Thesis` says "Defended March
  2026"; the Interview-Prep timeline says February. The PINN README carries a
  `License-MIT` badge over an Apache-2.0 repo.
- **Two public repos are months stale on GitHub**: `cortex` (7 unpushed local
  commits) and `AI-Intro` (8).

Intended outcome: a public GitHub surface where every visible repo has a
description, topics, and a README that says what it is; where nothing published
belongs to someone else; and where every date and availability claim matches the
CV.

### Correction carried into this plan

**12 repos are already archived**, which makes them read-only: `AI-Intro`,
`sprachlog`, `github-readme-stats`, `The-Dumpster-App`, `My-Resume-Template`,
`nxopen-cad-extractor`, `Sumanthreddy-DE.github.io`, `Feed-Forward-Neural-Network`,
`Streamlit-project`, `DSSS`, `ML-project`, `Solidity`.

Archived repos accept **no** setting changes, including visibility changes and
pushes. Every touch below therefore runs **unarchive, change, re-archive** where
the repo should stay archived. This affects `Feed-Forward-Neural-Network` (kept
public, needs description and topics) and `AI-Intro` (needs a push before going
private).

Note also that `Sumanthreddy-DE/STATE.md` claims sprachlog was "dropped" in May
2026. It was archived, not removed, and is still public today. STATE.md overstates
what prior sessions actually did; verify against `gh`, not against STATE.md.

## Working location

**`C:\Users\suman\Desktop\Docs\Job\Projects\Sumanthreddy-DE\`**

That repo already is the GitHub-presentation project. It has a `STATE.md` whose
open pipeline items ("README-body em-dash sweep", "GitHub bio fix") are a strict
subset of this work. Its charter widens from "profile README" to "GitHub public
presence."

Not `Myself/`: that hub is documents-only by design and holds no repos, while this
work touches 27 GitHub repos.
Considered `career-ops` and rejected: it is a code tool for job-search automation,
and filing a presentation plan there muddies its charter.

**First execution step:** copy this plan to
`Projects/Sumanthreddy-DE/docs/exec-plans/active/2026-09-01-github-presence-sweep.md`.
That directory does not exist yet; the repo has no harness (no `docs/`, no
`BACKLOG.md`). Create `docs/exec-plans/active/` directly rather than running
`new-project-init.sh`, since a two-file docs repo does not need the full scaffold.

## Ownership and approval rules

Set by the user on 2026-09-01. These override anything else in this plan.

1. **Only repos owned by the `Sumanthreddy-DE` account are in scope.** Nothing
   owned by another person or organization is touched.
   `Projects/Modal_Analysis/` (remote `vamshidharre/Modal_Analysis`) is explicitly
   excluded. Separately, and outside this plan: PR #1 there is still open under
   Sumanth's name and needs a decision at some point.
2. **Per-repo approval.** Before the first change to any repo, state the repo name
   and exactly what will change, and wait for a yes. After that yes, complete that
   repo's changes without further prompting, then report what was done. One
   approval per repo, not per change.
3. **When ownership is unclear, stop and ask.** Do not guess.

### Out of scope by user decision

**`Production-Engineering-Data-Automation` is not touched at all.**

The ownership check on 2026-09-01 returned `owner=Sumanthreddy-DE`, `fork=false`,
no parent repo, and all four commits authored by Sumanth on 2025-08-09, so the
repo itself is his. What is not his is the content uploaded into it:
`Bhanu's code.txt` (72 KB, another person's named code), plus `Baukasten.json` and
`Loesungsbibliothek.json`.

The concern was raised and the user chose to leave the repo alone. Recorded so the
state is deliberate rather than overlooked: the repo stays public, and Sumanth's
public account continues to serve another person's named code with no license and
no attribution. Revisit only if the user reopens it.

## Decisions locked with the user

| Question | Decision |
|---|---|
| Session goal | Recruiter-facing polish across the public GitHub surface |
| Dead-weight repos | Make private, not delete |
| Repo ownership | Only `Sumanthreddy-DE`-owned repos; ask per repo before changing it |
| `Production-Engineering-Data-Automation` | Out of scope, not touched (user decision) |
| Unpushed commits | Review the diffs, then push |
| Hiwi repos | Keep 2 public with real READMEs, 2 private |
| 6 coursework repos | Keep public, add descriptions and topics |
| License | MIT on `cortex`, `ai-eng-tracker`, `anny-booking-bot` |
| Availability wording | MSc Computational Engineering completed August 2026, available immediately |
| Thesis dates | Submitted February 2026, defended March 2026 |
| sprachlog | Private, not deleted |
| Em-dash sweep | Profile README and newly written prose only |
| Pinned six | User picks from the candidate list in Phase 7 |
| AI questionnaire site | Future work, separate session, already captured |

## Target state

**16 public repos** (down from 27), each with a description, topics, and a real
README. `Production-Engineering-Data-Automation` is the sixteenth and is left
exactly as it is, per the out-of-scope decision above.

**Keep public and improve (15):**

| Tier | Repos |
|---|---|
| Flagship | `PINN-for-composite-interface-identification`, `simready`, `Master-Thesis` |
| Shipped tools | `cortex`, `ai-eng-tracker`, `anny-booking-bot` |
| Profile | `Sumanthreddy-DE` |
| Hiwi / applied CAE | `NX-Constraints-training`, `Export-NX-CAD-files-to-CREO` |
| Coursework | `Peak-Power-Minimization`, `Topology-Optimization-of-a-Reservoir`, `Predicting-the-Bulk-Modulus-of-Inorganic-Crystals`, `Simulation-of-Diffusion-using-Finite-Differences`, `Named-Entity-Recognition`, `Feed-Forward-Neural-Network` |

**Make private (10), each with the reason:**

| Repo | Reason |
|---|---|
| `The-Dumpster-App` | Lovable boilerplate README plus a live lovable.dev project link |
| `AI-Intro` | Publicly documents the LinkedIn AI-video outreach strategy; bad discovery order for a recruiter |
| `sprachlog` | 9 KB, no README, dead |
| `nxopen-cad-extractor` | 0 KB, empty shell |
| `Solidity` | 0 KB, empty shell |
| `My-Resume-Template` | 4 KB, title-only README |
| `Streamlit-project` | Title-only README |
| `DSSS` | README reads "Just a basic assignment of push and pull repos" |
| `ML-project` | 4 KB, one-line README |
| `github-readme-stats` | Fork, not our work, clutters the profile |

**Open decision at execution time:** `Sumanthreddy-DE.github.io` is public,
archived, empty, and 2 KB. The AI questionnaire site that would fill it is months
away. Recommendation is to make it private now and flip it back to public when the
site actually exists. Confirm before acting.

## Phases

### Phase 0 — Prerequisites and safety

1. `git fetch` in every local repo before touching anything. `Sumanthreddy-DE` is
   edited via the browser between sessions; the STATE.md landmine says so
   explicitly. Check `git rev-list --left-right --count <branch>...origin/<branch>`.
2. Confirm the `gh` account in use is `Sumanthreddy-DE`.
3. Record the current visibility and archive state of all 37 repos to a file in
   the scratchpad, so every change in this plan is reversible from a known
   baseline.

### Phase 1 — Shrink the public surface

All ten repos here are inert: empty shells, boilerplate, a fork, or superseded
docs. No ordering constraint between them. Ask per repo before each one.

Pattern per repo (archived repos need the unarchive step first):

```
gh repo unarchive Sumanthreddy-DE/<name>      # only if currently archived
gh repo edit Sumanthreddy-DE/<name> --visibility private --accept-visibility-change-consequences
gh repo archive Sumanthreddy-DE/<name>        # restore archive state
```

Apply to all 10 repos in the private list above. `AI-Intro` is handled in Phase 2
instead, because it must be pushed before it goes private.

Note: making a repo private breaks any existing external link to it and drops its
stars. Only `github-readme-stats` and `Sumanthreddy-DE.github.io` are plausible
link targets, and neither matters.

### Phase 2 — Push the stale commits

Three repos hold unpushed work. Review each diff before pushing; the point of the
review is to catch secrets, personal data, and anything belonging to someone else,
which is the same class of problem Phase 1 exists to fix.

| Repo | Commits | Handling |
|---|---|---|
| `cortex` | 7 (public) | Review `git log -p origin/main..HEAD`, then push |
| `AI-Intro` | 8 (public, archived) | Unarchive, review, push, then make private, then re-archive |
| `self-talk-coach` | 1 (private) + 1 dirty file | Review, commit the dirty file if it belongs, push |

`career-ops` and `weekly-digest` each have one dirty file on a feature branch.
Inspect and report, but do not commit; they belong to their own projects.

Per the global rule, `git push` is hook-blocked for the agent. Commits are made
here; the push line is printed for the user to run.

### Phase 3 — Sync the facts

Every public claim about dates and availability must match the CV.

| File | Change |
|---|---|
| `Sumanthreddy-DE/README.md` | "available from **June 2026**" becomes "MSc Computational Engineering completed August 2026, available immediately." Also sweep em-dashes from the README body, and reword the "just weebing" line, which reads oddly to a DACH Berechnung recruiter. |
| GitHub profile bio (via `gh api`) | Replace "Wanna be Computational Engineer" (STATE.md pipeline item). It undersells a completed MSc. |
| `Master-Thesis/README.md` | "Status: Defended March 2026" becomes "Submitted February 2026, defended March 2026" |
| `PINN.../README.md` | Fix the `License-MIT` badge to Apache-2.0, matching the actual `LICENSE` |
| `cortex/README.md` | "Telegram Capture" is stale; Discord capture is what shipped. Verify against the 7 unpushed commits from Phase 2 before editing. |

Also reconcile the profile README repo list against the Phase 1 result, so it does
not link to repos that are now private.

### Phase 4 — Descriptions and topics on the 15 in-scope public repos

Two `gh repo edit` calls per repo. This is the highest ratio of recruiter impact
to effort in the whole plan, and it is the phase to complete first if the session
is cut short.

Topic vocabulary, kept small so the profile reads as one coherent body of work:

```
computational-engineering  scientific-ml  physics-informed-neural-networks
finite-element-method      topology-optimization  composites
cad-automation             nx-open        machine-learning
pytorch  tensorflow  python  typescript  fea  simulation  automation
```

Rules: 3 to 6 topics per repo, drawn only from that vocabulary; every repo carries
at least one domain topic and one technology topic. Descriptions run 10 to 20
words, stating what it does, not what it is made of.

Four repos already have good descriptions and need topics only: `PINN...`,
`simready`, `cortex`, `ai-eng-tracker`.

### Phase 5 — Real READMEs

Ordered by payoff. New prose contains no em-dashes and no cherry-picked metrics,
per the standing rules.

1. **`NX-Constraints-training`** (highest payoff). It already contains
   `ML_README.md`, `PROJECT_SUMMARY.md`, `USAGE_GUIDE.md`, and
   `FILES_OVERVIEW.txt`. The work is mostly promoting and condensing existing
   content into `README.md`, not writing from scratch. Cover the problem (predicting
   NX assembly joint constraints from CAD feature data), the approach, how to run
   `predict_joint.py`, and what `confusion_matrix.png` shows. Do not quote a headline
   accuracy figure; describe the evaluation method instead.
2. **`Export-NX-CAD-files-to-CREO`**. Short repo, short README: what an NX Open
   journal is, what this one converts, how to run it, and the FAU KTmfk Hiwi context.
3. **`Topology-Optimization-of-a-Reservoir`**. Its README is currently raw build
   notes with no heading. Restructure into title, what it does, the toolchain
   (CFS, ParaView), and the run sequence. The existing content is accurate and can
   be kept nearly verbatim under headings.
4. **`anny-booking-bot`**, **`Master-Thesis`**, **`Peak-Power-Minimization`**,
   and the three remaining coursework repos already have adequate READMEs. Light
   pass only: confirm the first paragraph states what the repo does.

### Phase 6 — Licenses

Add `LICENSE` (MIT, 2026, Sumanth Reddy Settipalli) to `cortex`, `ai-eng-tracker`,
`anny-booking-bot`, plus a one-line License section at the bottom of each README.

The two Hiwi repos are deliberately excluded: work produced for FAU KTmfk is not
ours to license. See the risk item below.

### Phase 7 — Pinned six

Pin after Phases 1 through 6, so the pinned repos are the polished ones. Candidates,
for the user to choose from at this point:

- **Balanced:** `PINN...`, `simready`, `Master-Thesis`, `NX-Constraints-training`,
  `cortex`, `ai-eng-tracker`. Two thesis and CAE flagships, the CAD-ML Hiwi repo,
  and two shipped tools. Reads as a computational engineer who also ships software.
- **Pure Berechnung:** swap `cortex` and `ai-eng-tracker` for
  `Topology-Optimization-of-a-Reservoir` and
  `Predicting-the-Bulk-Modulus-of-Inorganic-Crystals`. Stronger single-domain
  signal, no evidence of shipping software.

### Phase 8 — Bookkeeping

- Rewrite `Sumanthreddy-DE/STATE.md`: widen the What section from "profile README
  repo" to "GitHub public presence," log what this session did, and correct the
  false "dropped sprachlog" claim under Done.
- Update the `Sumanthreddy-DE` row in `Projects/PROJECTS.md` with a new Now to
  Next and a fresh Last-touched date. Its Age flag is currently red at 2026-05-28.
- Add the reversal commands (unarchive, set public, re-archive) to the plan file in
  `docs/exec-plans/active/`, so any privacy change can be undone without a rerun.

## Future work, not this session

**Ask-My-GitHub site.** Captured at `Projects/_ideas/ask-my-github-site.md` with a
row in `PROJECTS.md` under Loose ideas. A visitor to `Sumanthreddy-DE.github.io`
gets a questionnaire answered by a self-hosted model grounded in Sumanth's data and
repos.

Open issues recorded there, to settle in its own session:

- GitHub Pages is static hosting, so no model can run on it. A backend is required.
  The existing VPS at `37.60.234.210` (Ollama-compatible, `qwen3:8b`) could serve
  it, but that makes the job-search landing page depend on VPS uptime.
- Hallucination about career facts is worse than having no site. Hard grounding and
  a genuine refusal path are required.
- Recruiters skim. A questionnaire is friction where a page of facts is not.
- Recommended shape: a static facts page that always loads, with the AI chat below
  the fold as an optional demo. The chat then functions as a portfolio piece
  demonstrating RAG and self-hosted inference, rather than as the only route to
  information.

## Verification

1. **Public surface count.**
   `gh repo list Sumanthreddy-DE --limit 100 --json name,visibility --jq '[.[]|select(.visibility=="PUBLIC")]|length'`
   must return **16** (the 15 improved repos plus the untouched
   `Production-Engineering-Data-Automation`).
2. **No public repo lacks a description.**
   `gh repo list Sumanthreddy-DE --limit 100 --json name,visibility,description --jq '.[]|select(.visibility=="PUBLIC" and (.description|length)==0)|.name'`
   must return nothing, except `Production-Engineering-Data-Automation`, which is
   out of scope and expected to appear.
3. **No public repo lacks topics.** Same query shape against `repositoryTopics`;
   must return nothing.
4. **No public repo has a stub README.** For each public repo,
   `gh api repos/Sumanthreddy-DE/<name>/readme --jq '.size'` must exceed 300 bytes.
5. **The out-of-scope repo is genuinely untouched.**
   `gh api repos/Sumanthreddy-DE/Production-Engineering-Data-Automation --jq '"\(.visibility) \(.pushed_at)"'`
   must still return `public 2025-08-09T...`, unchanged from the Phase 0 baseline.
6. **Local and remote are in sync.** For `cortex`, `AI-Intro`, and
   `self-talk-coach`, `git rev-list --left-right --count <branch>...origin/<branch>`
   must return `0 0` after the user pushes.
7. **Facts agree.** Grep the profile README, `Master-Thesis/README.md`, and the CV
   for the availability and thesis dates; all three must state August 2026
   completion, immediate availability, February submission, March defense.
8. **Recruiter pass.** Open `github.com/Sumanthreddy-DE` in a browser and read it
   cold for thirty seconds. Every visible repo should be self-explanatory from its
   name plus description alone.

## Risks and open items

- **FAU KTmfk clearance is unresolved.** `NX-Constraints-training` contains
  `Constraint_dataset.xlsx`, which is FAU data, and both retained Hiwi repos are
  employer work. They are already public, so this plan does not increase exposure,
  but writing prominent READMEs does raise their visibility. Recommended action:
  one email to KTmfk confirming publication is acceptable. Until it is answered,
  write the READMEs but hold the pin on `NX-Constraints-training`.
- **Third-party code stays public by user decision.** `Bhanu's code.txt` and the
  German business-data JSON files remain world-readable from Sumanth's account.
  Documented above, deliberately not acted on.
- **Visibility changes are reversible but not free.** Going private drops stars and
  breaks inbound links. Only `github-readme-stats` and `Sumanthreddy-DE.github.io`
  could plausibly have inbound links, and neither matters.
- **`Sumanthreddy-DE` drifts through browser edits.** Always fetch first. This has
  already caused divergence in a previous session.
- **STATE.md is not trustworthy as a record.** It claims completed work that `gh`
  contradicts. Verify against the GitHub API, and fix STATE.md in Phase 8.
- **Phase ordering matters.** Phase 4 (descriptions and topics) delivers the most
  recruiter impact per minute. If the session is cut short, Phases 0, 1, 2, and 4
  are the ones that must be finished.
