# STATE — Sumanthreddy-DE

<!-- Machine-maintained by save-session Step 6b. Do not hand-edit. -->

Status: active
Last touched: 2026-09-01

## What
The GitHub public presence as a whole, not just one README. Covers the profile README repo
(github.com/Sumanthreddy-DE), the account sidebar fields, repo visibility, descriptions, topics,
licenses and pins across all repos owned by the account, plus the Pages site at
sumanthreddy-de.github.io. Managed with the `gh` CLI, tracked in
`docs/exec-plans/active/2026-09-01-github-presence-sweep.md`.

## Done
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
- Nothing in progress

## Pipeline
- Reconsider pinning Master-Thesis. It was left unpinned only because the repo shipped no
  compiled PDF; that reason is gone as of 2026-09-01. Pinning it would mean dropping one of
  the current six
- Pin NX-Constraints-training once KTmfk clears publication. It has the strongest README of the
  Hiwi work and is directly on-target for DACH Berechnung roles, but the clearance is open
- Email KTmfk to confirm publishing the two Hiwi repos (NX-Constraints-training,
  Export-NX-CAD-files-to-CREO) is acceptable. Deferred by the user on 2026-09-01; the plan
  advised holding the NX-Constraints-training pin until answered, but the user chose the
  balanced pin set including it, accepting the risk knowingly. Both repos were already public
  before this session, so the sweep did not increase exposure
- github-readme-stats stays public: it is a fork, GitHub does not allow forks to be made private,
  and the profile README's stats cards are served from a Vercel deployment tied to it

## Resume here
`git fetch` FIRST (repo drifts via browser edits). The sweep is complete, verified, and its
plan is in docs/exec-plans/completed/. Every gap found by the closing verification is closed and
the thesis PDF is published, so nothing is half-done.

Two things gate the remaining Pipeline items, and both are decisions rather than work: whether
to email KTmfk about the two Hiwi repos, and whether Master-Thesis now displaces one of the six
pins. Neither is urgent.

Verification one-liners, if you want to confirm the surface is still clean:

```
gh repo list Sumanthreddy-DE --limit 100 --json visibility --jq '[.[]|select(.visibility=="PUBLIC")]|length'
gh repo list Sumanthreddy-DE --limit 100 --json name,visibility,description,repositoryTopics --jq '.[]|select(.visibility=="PUBLIC" and (((.description//"")|length)==0 or ((.repositoryTopics//[])|length)==0))|.name'
```

Expect **18** and only `Production-Engineering-Data-Automation` (out of scope) plus
`github-readme-stats` (a fork, topics cannot be set usefully).

## Landmines
- Edited outside CC (browser) between sessions — ALWAYS fetch + check @{u}..HEAD before committing
- Recruiter-facing: no cherry-picked metrics, no em-dashes, no AI tells
- STATE.md previously claimed sprachlog was "dropped" in May 2026. It was archived, still public,
  and was only made private on 2026-09-01. Verify claims against `gh`, not against this file
- Archived repos reject every setting change including visibility. Unarchive, change, re-archive
- Production-Engineering-Data-Automation is deliberately out of scope by user decision and still
  serves another person's named code publicly
- Seven repos (NX-Constraints-training, Export-NX-CAD-files-to-CREO,
  Topology-Optimization-of-a-Reservoir, ai-eng-tracker, anny-booking-bot, Master-Thesis,
  Sumanthreddy-DE.github.io) have NO local clone under Projects/. The 2026-09-01 commits were
  made in session-temp scratchpad clones that are now gone. Clone fresh before editing them
- ai-eng-tracker and anny-booking-bot default to branch `master`, not `main`. A loop that
  hardcodes `main` will fail on those two
