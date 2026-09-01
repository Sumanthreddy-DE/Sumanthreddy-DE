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

## Doing
- Nothing in progress

## Pipeline
- Pin the six repos (Phase 7 of the sweep plan, awaiting the user's pick between the balanced
  and pure-Berechnung sets)
- Account sidebar fields (name, bio, location, blog) still unset: the `gh` token lacks the `user`
  scope. Run `gh auth refresh -h github.com -s user`, then apply
- Email KTmfk to confirm publishing the two Hiwi repos is acceptable. Until answered, hold the
  pin on NX-Constraints-training
- github-readme-stats stays public: it is a fork, GitHub does not allow forks to be made private,
  and the profile README's stats cards are served from a Vercel deployment tied to it

## Resume here
`git fetch` FIRST (repo drifts via browser edits). Then Phase 7 pins and the sidebar fields once
the token has the `user` scope.

## Landmines
- Edited outside CC (browser) between sessions — ALWAYS fetch + check @{u}..HEAD before committing
- Recruiter-facing: no cherry-picked metrics, no em-dashes, no AI tells
- STATE.md previously claimed sprachlog was "dropped" in May 2026. It was archived, still public,
  and was only made private on 2026-09-01. Verify claims against `gh`, not against this file
- Archived repos reject every setting change including visibility. Unarchive, change, re-archive
- Production-Engineering-Data-Automation is deliberately out of scope by user decision and still
  serves another person's named code publicly
