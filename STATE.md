# STATE — Sumanthreddy-DE

<!-- Machine-maintained by save-session Step 6b. Do not hand-edit. -->

Status: active
Last touched: 2026-10-10

## What
The GitHub public presence as a whole, not just one README. Covers the profile README repo
(github.com/Sumanthreddy-DE), the account sidebar fields, repo visibility, descriptions, topics,
licenses and pins across all repos owned by the account, plus the Pages site at
sumanthreddy-de.github.io. Managed with the `gh` CLI, tracked in
`docs/exec-plans/active/2026-09-01-github-presence-sweep.md`.

## Done
- 2026-10-10: folder moved back from `_archive/` (registry repointed). Repo audit + hand-off plan for the profile refresh: hybrid positioning, AI-tool badges, new bio, 6 pins, resume-assistant MIT, SimReady session files untracked. Plan: `docs/exec-plans/active/2026-10-10-github-profile-ai-refresh.md`
- 2026-10-07: local clone archived to `Projects/_archive/Sumanthreddy-DE/` (done, nothing open). The profile README stays live on GitHub; clone again to edit, and fetch first
- Recruiter-POV profile rewrite: hybrid positioning, current projects, stats (2026-05-26/27)
- Featured anny-booking-bot; Topology-Opt → Bulk-Modulus swap in Computational column (2026-05-28)
- 12 old repos archived, Hiwi/coursework descriptions, Master-Thesis link live
- GitHub presence sweep (2026-09-01):
  - Public surface 27 → 18. Nine repos made private (The-Dumpster-App, sprachlog,
    nxopen-cad-extractor, Solidity, My-Resume-Template, Streamlit-project, DSSS, ML-project,
    AI-Intro), each via unarchive → private → re-archive
  - Topics added to all 15 in-scope public repos, from a shared vocabulary plus six tool-side
    terms (electron, playwright, github-actions, llm, web-scraping, nlp)
  - Descriptions: added to Feed-Forward-Neural-Network and the Pages repo, em-dashes swept from
    ai-eng-tracker and the profile repo, Export-NX corrected (it exports one part to STEP AP214,
    it is not a batch Creo converter)
  - Facts synced to the CV: availability now "completed August 2026, available immediately",
    Master-Thesis states both submission and defence dates, PINN license badge corrected to
    Apache-2.0, cortex README documents Discord capture instead of the removed Telegram route
  - READMEs written for NX-Constraints-training, Export-NX-CAD-files-to-CREO and
    Topology-Optimization-of-a-Reservoir
  - MIT LICENSE added to cortex, ai-eng-tracker, anny-booking-bot
  - sumanthreddy-de.github.io rewritten from a placeholder page ("Wannabe Computational Material
    Scientist") into a real summary, and left unarchived so it stays editable
  - Six pins set in the browser: PINN-for-composite-interface-identification, simready, cortex,
    Predicting-the-Bulk-Modulus-of-Inorganic-Crystals, Peak-Power-Minimization, anny-booking-bot.
    This departs from the balanced set in the plan: Master-Thesis was dropped because the repo
    has no compiled PDF, and NX-Constraints-training because KTmfk clearance is still open
  - Account sidebar set: name, bio, location and blog now match the CV
  - sumanthreddy.settipalli@gmail.com added and verified on the account, which retroactively
    attributed the commits made under it during this session
- Gap-closure pass (2026-09-01, verified independently):
  - Profile repo topics fixed: `config` + `github-config` replaced with `profile-readme`,
    `computational-engineering`, `scientific-ml`
  - `cortex` repo description corrected to "Discord capture" (the README had been fixed
    during the sweep, the description had not)
  - Profile README hobby line reworded from "just weebing" to "I'm deep in anime and manga"
  - Stale Pipeline entry claiming the account sidebar fields were unset deleted; the fields
    were already set and the API confirms it
  - `ai-eng-tracker` local clone pulled back in sync with `origin/master`
  - `Settipalli-MSc-Thesis-FAU-2026.pdf` (2.29 MB) added to the Master-Thesis repo, which
    previously shipped only `main.tex`

## Doing
- Profile AI refresh: plan written and committed (`4cae703`), not executed yet

## Settled — do not reopen

Closed by the user on 2026-09-01. Recorded here so no future session re-raises them as
open questions.

- **KTmfk clearance: resolved, no email needed.** The user already spoke to the contact at
  KTmfk in person. Publishing `NX-Constraints-training` and `Export-NX-CAD-files-to-CREO`
  publicly is fine, including `Constraint_dataset.xlsx`. Both stay public. The pin gate that
  depended on this clearance is therefore removed; whether to actually pin
  `NX-Constraints-training` is a free choice, not a blocked one.
- **Master-Thesis stays unpinned, PDF or no PDF.** The user considered it after the PDF
  shipped and decided it does not earn a slot. The compiled PDF still made the repo worth
  publishing on its own. Do not re-propose this.
- **`Production-Engineering-Data-Automation`: ignore entirely.** Not a task, not a risk item,
  not a question. Do not raise it again in any form.
- **`github-readme-stats` stays public.** It is a fork, GitHub does not permit making a public
  fork of a public repository private, and the profile README's stats cards are served from a
  Vercel deployment tied to it. Removing it would mean deleting the fork and repointing Vercel.

## Pipeline
- Nothing open. The next piece of work here is the Ask-My-GitHub site, which is a separate
  project rather than a presence-sweep item: `Projects/_ideas/ask-my-github-site.md`

## Resume here
`git fetch` FIRST (repo drifts via browser edits). Then execute `docs/exec-plans/active/2026-10-10-github-profile-ai-refresh.md`
task by task. All decisions are in the plan; do not re-ask them. Task 6 (pins) is a browser step for the user.
Open question for the user: archive the ai-eng-tracker repo, or only drop it from the README.

## Landmines
- Edited outside CC (browser) between sessions — ALWAYS fetch + check @{u}..HEAD before committing
- Recruiter-facing: no cherry-picked metrics, no em-dashes, no AI tells
- STATE.md previously claimed sprachlog was "dropped" in May 2026. It was archived, still public,
  and was only made private on 2026-09-01. Verify claims against `gh`, not against this file
- Archived repos reject every setting change including visibility. Unarchive, change, re-archive
- Production-Engineering-Data-Automation is deliberately out of scope by user decision and still
  serves another person's named code publicly
- Most of the seven repos listed below have NO local clone under Projects/, so the 2026-09-01
  commits were made in session-temp scratchpad clones that are now gone. Clone fresh before
  editing: NX-Constraints-training, Export-NX-CAD-files-to-CREO,
  Topology-Optimization-of-a-Reservoir, anny-booking-bot, Sumanthreddy-DE.github.io.
  TWO EXCEPTIONS, both verified 2026-09-02: Master-Thesis is cloned at
  `~/Desktop/Docs/Job/Thesis/Thesis_Final/Master-Thesis` (under Thesis/, not Projects/, which is
  why it was missed) and ai-eng-tracker at `~/Desktop/Docs/Job/Projects/_archive/ai-eng-tracker` (archived 2026-10-07). Use
  those, do not re-clone them
- ai-eng-tracker and anny-booking-bot default to branch `master`, not `main`. A loop that
  hardcodes `main` will fail on those two
