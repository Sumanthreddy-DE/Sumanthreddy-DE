# GitHub profile refresh: hybrid positioning and AI tooling

**Status:** active
**Last verified:** 2026-10-10

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:executing-plans (or superpowers:subagent-driven-development) to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Reposition the GitHub profile as a hybrid of computational engineering and applied LLM engineering, and surface the AI tools already used in public repos (badges, bio, About Me, topics, pins).

**Architecture:** Mostly copy and metadata. One file rewrite (the profile `README.md` in this repo), `gh` CLI edits for repo metadata and the account bio, two small commits in other repos (resume-assistant LICENSE, simready untracking session files), and one browser-only step for pins that the user does.

**Tech Stack:** `gh` CLI (token already has `repo`, `user`, `workflow` scopes), git, curl, shields.io badges.

## Start here

Launch Claude Code from `C:\Users\suman\Desktop\Docs\Job\Projects\Sumanthreddy-DE`, then paste:
*"Read `docs/exec-plans/active/2026-10-10-github-profile-ai-refresh.md` and execute it."*

Everything this plan needs is in this file; the chat that produced it is not needed. All decisions below were made by the user on 2026-10-10. Do not re-ask them.

## Global Constraints

- Recruiter-facing copy: **no em-dashes (`—`)**, no cherry-picked metrics (no "VSR 0.88", no percentages), no AI tells (no "passionate", "leveraging", "cutting-edge", no emoji bullets beyond the two listed below).
- README layout stays as it is (header, typing banner, About Me, tools, two-column Featured table, stats, connect). Only content changes.
- Emojis: keep only 🎓 and 📍 in About Me. Remove 👋, 🔬, 🛠️, 🌱, 🧮, 🤖.
- **No Claude Code badge.** No separate "AI skills" section.
- Every badge must correspond to a dependency in a public repo (verified 2026-10-10, see the table in Task 1).
- `git push` is blocked for agents. Commit, then the `print-push-line` hook prints the push line for the user. Never chain `git commit && git push`.
- Stage and commit in the same Bash call (another session may share a repo).
- No `Co-Authored-By` or any AI attribution in commits.
- Do not hand-edit `STATE.md` (machine-maintained). It is updated by `/save-session` at the end.
- Settled, do not reopen (from `STATE.md`): Master-Thesis stays unpinned; `Production-Engineering-Data-Automation` is out of scope entirely; `github-readme-stats` fork stays public.
- `anny-booking-bot` is currently **private** (history purge, waiting on GitHub Support). The user decided: keep it pinned and featured as it is. Do not treat its 404 for anonymous visitors as a defect, and do not touch that repo.

## Decisions (user, 2026-10-10)

| Item | Decision |
|---|---|
| Positioning | Hybrid: Scientific ML / computational engineering + applied LLM engineering |
| Pins (6) | PINN-for-composite-interface-identification, simready, resume-assistant, NX-Constraints-training, anny-booking-bot, self-talk-coach |
| README Featured | Left: PINN, SimReady, NX-Constraints-training, Bulk-Modulus. Right: resume-assistant, self-talk-coach, cortex, anny-booking-bot. Drop ai-eng-tracker and Peak-Power |
| Badges | Remove NumPy, Jupyter, Git, Node.js. Add Claude API, QLoRA, FastAPI, edge-tts, pythonOCC, GitHub Actions, Electron. Keep Playwright |
| Bio | Exact text in Task 2 |
| SimReady session files | Untrack them from `main` |
| resume-assistant license | MIT |

## Out of scope (do not do)

- Archiving the `ai-eng-tracker` repo. It is only removed from the README. (Open question for the user.)
- The Pages site (`Sumanthreddy-DE.github.io`), which links to `anny-booking-bot`. It has its own project.
- resume-assistant's README link to `fragen.html` (404 until the chat page ships). That belongs to the resume-assistant project.
- Purging the SimReady session files from git history. This plan only stops tracking them.

---

### Task 0: Preflight

**Files:** none

- [ ] **Step 1: Sync this repo.** The README is sometimes edited in the browser.

```bash
cd "C:/Users/suman/Desktop/Docs/Job/Projects/Sumanthreddy-DE"
git fetch && git status -sb
```

Expected: `## main...origin/main` with no `[behind N]`. If behind: `git pull --ff-only`.

- [ ] **Step 2: Confirm token scopes.**

```bash
gh auth status 2>&1 | grep -i scopes
```

Expected: includes `repo` and `user`. If `user` is missing, stop and ask the user to run `! gh auth refresh -s user`.

- [ ] **Step 3: Snapshot the baseline** to the session scratchpad (for the final diff).

```bash
gh api users/Sumanthreddy-DE --jq '{bio}' 
gh api graphql -f query='{user(login:"Sumanthreddy-DE"){pinnedItems(first:6){nodes{... on Repository{name}}}}}' --jq '.data.user.pinnedItems.nodes[].name'
for r in resume-assistant simready self-talk-coach; do echo "$r: $(gh api repos/Sumanthreddy-DE/$r --jq '[.topics[]]|join(",")')"; done
```

Expected on 2026-10-10: 5 pins (PINN, Bulk-Modulus, simready, Peak-Power, cortex); resume-assistant has no topics.

---

### Task 1: Rewrite the profile README

**Files:**
- Modify: `README.md` (whole file, in this repo)

**Badge evidence (do not add anything not in this table):**

| Badge | Public repo evidence |
|---|---|
| Claude API | `anthropic` in resume-assistant `requirements.txt`, self-talk-coach `pyproject.toml` |
| QLoRA | simready `notebooks/gencad_train_qwen.ipynb` (PEFT + Unsloth, Qwen2.5-VL-3B) |
| FastAPI | resume-assistant `requirements.txt` |
| edge-tts | self-talk-coach `pyproject.toml` |
| pythonOCC | simready `environment.yml` |
| Playwright | anny-booking-bot, cortex, simready `scripts/package.json` |
| GitHub Actions | smartrecruiters-job-alerts, anny-booking-bot, simready CI |
| Electron | cortex `package.json` |
| Streamlit | simready `requirements.txt` |

Note: shields.io has no `playwright` logo (checked 2026-10-10, renders without an icon), so that badge uses a plain colour like the FEM badge.

- [ ] **Step 1: Replace `README.md` with exactly this content.**

````markdown
<h1 align="center">Hi, I'm Sumanth Reddy</h1>

<p align="center">
  <a href="https://github.com/Sumanthreddy-DE">
    <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&size=22&duration=3500&pause=800&color=58A6FF&center=true&vCenter=true&width=620&lines=ML+%26+Computational+Engineer;Neural+Networks+%7C+FEM+%7C+Materials;LLM+tools%2C+evaluated" alt="typing tagline" />
  </a>
</p>

---

### About Me

- 🎓 MSc Computational Engineering, **FAU Erlangen-Nürnberg**, completed **August 2026**
- Building **SimReady** (FEA pre-processing: a GNN on B-Rep geometry, an LLM tool-use agent and QLoRA-tuned CAD generation) and **Physics-Informed Neural Networks** for composite material interfaces (thesis area)
- Build LLM tools with evaluation built in: **resume-assistant**, a grounded CV chatbot with a hand-graded eval set, and **self-talk-coach**, a spoken-German conversation partner
- 📍 Open to **Scientific ML / Computational Engineer (Berechnung)** and **applied LLM** roles in DACH, available **immediately**
- When not building, I'm deep in anime and manga

---

### Languages & Tools

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat&logo=typescript&logoColor=white)
![MATLAB](https://img.shields.io/badge/MATLAB-0076A8?style=flat&logo=mathworks&logoColor=white)
![LaTeX](https://img.shields.io/badge/LaTeX-008080?style=flat&logo=latex&logoColor=white)

![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat&logo=pytorch&logoColor=white)
![TensorFlow](https://img.shields.io/badge/TensorFlow-FF6F00?style=flat&logo=tensorflow&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat&logo=scikit-learn&logoColor=white)
![SciPy](https://img.shields.io/badge/SciPy-8CAAE6?style=flat&logo=scipy&logoColor=white)
![FEM](https://img.shields.io/badge/FEM-5A5A5A?style=flat)
![NX Open API](https://img.shields.io/badge/NX%20Open%20API-00A1E0?style=flat&logo=siemens&logoColor=white)
![pythonOCC](https://img.shields.io/badge/pythonOCC-5A5A5A?style=flat)

![Claude API](https://img.shields.io/badge/Claude%20API-D97757?style=flat&logo=anthropic&logoColor=white)
![QLoRA](https://img.shields.io/badge/QLoRA-FFD21E?style=flat&logo=huggingface&logoColor=black)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat&logo=fastapi&logoColor=white)
![edge-tts](https://img.shields.io/badge/edge--tts-0078D4?style=flat)
![Playwright](https://img.shields.io/badge/Playwright-2EAD33?style=flat)
![GitHub Actions](https://img.shields.io/badge/GitHub%20Actions-2088FF?style=flat&logo=githubactions&logoColor=white)
![Electron](https://img.shields.io/badge/Electron-47848F?style=flat&logo=electron&logoColor=white)
![Streamlit](https://img.shields.io/badge/Streamlit-FF4B4B?style=flat&logo=streamlit&logoColor=white)

---

### Featured Projects

<table>
<tr>
<td valign="top" width="50%">

**Computational & ML**

- **[PINN – Composite Interface ID](https://github.com/Sumanthreddy-DE/PINN-for-composite-interface-identification)**
  <br><sub>Physics-Informed Neural Network recovering equivalent extended-interface parameters from 3-layer interphase configurations (CSA approach + Mori–Tanaka).</sub>

- **[SimReady](https://github.com/Sumanthreddy-DE/simready)**
  <br><sub>FEA pre-processing for STEP files: OCC geometry checks and a GraphSAGE GNN fused into one readiness score, a multi-turn LLM tool-use agent, and a QLoRA-tuned Qwen2.5-VL-3B for CAD generation.</sub>

- **[NX Constraints Training](https://github.com/Sumanthreddy-DE/NX-Constraints-training)**
  <br><sub>ML classifier predicting Siemens NX assembly joint constraints from CAD feature data: Keras tabular model (Hiwi @ KTmfk, FAU).</sub>

- **[Predicting Bulk Modulus of Inorganic Crystals](https://github.com/Sumanthreddy-DE/Predicting-the-Bulk-Modulus-of-Inorganic-Crystals)**
  <br><sub>ML prediction of inorganic-crystal bulk modulus: Matminer/Magpie features, regression + feature-selection model comparison (scikit-learn).</sub>

</td>
<td valign="top" width="50%">

**AI & Automation**

- **[resume-assistant](https://github.com/Sumanthreddy-DE/resume-assistant)**
  <br><sub>Grounded CV chatbot: FastAPI + Claude, whole CV in the prompt with no retrieval, a hand-graded eval set with traps and prompt injection, rate limits and a fallback when the API is down.</sub>

- **[self-talk-coach](https://github.com/Sumanthreddy-DE/self-talk-coach)**
  <br><sub>Spoken German practice from the terminal: Deepgram speech-to-text, an LLM conversation partner and edge-tts voice, with a help ladder that steps in when you freeze.</sub>

- **[cortex](https://github.com/Sumanthreddy-DE/cortex)**
  <br><sub>Local-first desktop app: priority-Kanban link/idea capture, Chrome extension, Discord capture, and system-tray reminders.</sub>

- **[anny-booking-bot](https://github.com/Sumanthreddy-DE/anny-booking-bot)**
  <br><sub>Daily booking-calendar automation: headless Playwright scraper + Gmail SMTP digest, scheduled via GitHub Actions (pytest-tested, CI).</sub>

</td>
</tr>
</table>

---

### GitHub Stats

<p align="center">
  <img src="https://github-readme-stats-omega-lemon.vercel.app/api?username=Sumanthreddy-DE&show_icons=true&theme=radical" alt="GitHub Stats" height="165" />
  <img src="https://github-readme-stats-omega-lemon.vercel.app/api/top-langs/?username=Sumanthreddy-DE&layout=compact&theme=radical" alt="Top Languages" height="165" />
</p>
<p align="center">
  <img src="https://streak-stats.demolab.com/?user=Sumanthreddy-DE&theme=radical" alt="GitHub Streak" />
</p>

---

### Connect with Me

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/sumanthreddys)
[![Email](https://img.shields.io/badge/Email-D14836?style=flat&logo=gmail&logoColor=white)](mailto:sumanthreddy.settipalli@gmail.com)
````

Write it with the Write tool (not a heredoc), so Windows line endings and backslashes are not mangled.

- [ ] **Step 2: Check copy rules.**

```bash
cd "C:/Users/suman/Desktop/Docs/Job/Projects/Sumanthreddy-DE"
grep -c '—' README.md                                     # expect 0
grep -cE '👋|🔬|🛠|🌱|🧮|🤖' README.md                     # expect 0
grep -cE 'ai-eng-tracker|Peak-Power|NumPy|Jupyter|Node\.js|badge/Git-' README.md   # expect 0
grep -c 'img.shields.io/badge' README.md                  # expect 21 (19 tools + 2 connect)
```

Positive control for the zero checks: `grep -c 'PINN' README.md` must be non-zero, which proves grep reads the file.

- [ ] **Step 3: Check every badge renders.** Each must return HTTP 200 and an SVG.

```bash
grep -oE 'https://img\.shields\.io/badge/[^)]+' README.md | while read u; do printf '%s %s\n' "$(curl -s -o /dev/null -w '%{http_code}' "$u")" "$u"; done
```

Expected: every line starts with `200`. For the logo badges (anthropic, huggingface, fastapi, githubactions, electron), `curl -s "<url>" | grep -c '<image'` returns 1.

- [ ] **Step 4: Check every repo link resolves.**

```bash
grep -oE 'github\.com/Sumanthreddy-DE/[A-Za-z0-9._-]+' README.md | sort -u | sed 's#github.com/##' | while read r; do printf '%s %s\n' "$(gh api "repos/$r" --jq .visibility 2>&1 | head -1)" "$r"; done
```

Expected: `public` for every repo except `anny-booking-bot` (`private`, accepted by the user) and the bare profile link `Sumanthreddy-DE` (which is the user, not a repo, so an error there is fine).

- [ ] **Step 5: Preview the render.**

```bash
gh api -X POST markdown -f mode=gfm -f context=Sumanthreddy-DE/Sumanthreddy-DE -F text=@README.md > "$TMP/readme-preview.html"
```

Open it or grep it for `<table>`. Expected: one table with two cells and three badge paragraphs.

- [ ] **Step 6: Commit.**

```bash
git add README.md && git commit -m "docs: hybrid positioning, AI tooling badges, refreshed featured projects"
```

Then point the user at the push line the hook prints.

- [ ] **Step 7: Update the profile repo description.**

```bash
gh repo edit Sumanthreddy-DE/Sumanthreddy-DE --description "Source of the github.com/Sumanthreddy-DE profile README: Scientific ML and Computational Engineer, available immediately for Berechnung and applied LLM roles in DACH"
gh repo view Sumanthreddy-DE/Sumanthreddy-DE --json description --jq .description
```

Expected: the new string comes back exactly.

---

### Task 2: Sidebar bio

**Files:** none (account setting)

- [ ] **Step 1: Set the bio.** It must be 160 characters or fewer; this one is 121.

```bash
gh api -X PATCH user -f bio="MSc Computational Engineering (FAU). Scientific ML, FEM and CAD automation. I also build LLM tools and test them with evals."
```

- [ ] **Step 2: Verify against state, not exit status.**

```bash
gh api users/Sumanthreddy-DE --jq .bio
```

Expected: the exact string above. Name, location, blog and hireable must be unchanged (`Sumanth Reddy Settipalli`, `Reutlingen, Germany`, `https://sumanthreddy-de.github.io`, `true`).

---

### Task 3: Topics

**Files:** none (repo metadata)

- [ ] **Step 1: Add topics.**

```bash
gh repo edit Sumanthreddy-DE/resume-assistant --add-topic python,fastapi,llm,anthropic,evals
gh repo edit Sumanthreddy-DE/simready --add-topic llm-agents,rag,qlora
gh repo edit Sumanthreddy-DE/self-talk-coach --add-topic llm
```

- [ ] **Step 2: Verify.**

```bash
for r in resume-assistant simready self-talk-coach; do echo "$r: $(gh api repos/Sumanthreddy-DE/$r --jq '[.topics[]]|join(",")')"; done
```

Expected: resume-assistant shows the 5 new topics; simready keeps its 6 old topics plus the 3 new ones; self-talk-coach keeps its 6 plus `llm`.

---

### Task 4: MIT license for resume-assistant

**Files:**
- Create: `LICENSE` in `Sumanthreddy-DE/resume-assistant` (branch `main`)

The local clone at `Projects/resume-assistant` was active on 2026-10-10 and may have another session open in it. Work in a fresh clone in the session scratchpad instead.

- [ ] **Step 1: Clone.**

```bash
cd "$TMP" && gh repo clone Sumanthreddy-DE/resume-assistant ra-license && cd ra-license && git log --oneline -1
```

- [ ] **Step 2: Write `LICENSE`** with the Write tool, with this exact text. The copyright line matches cortex's LICENSE.

```
MIT License

Copyright (c) 2026 Sumanth Reddy Settipalli

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

- [ ] **Step 3: Commit.**

```bash
git add LICENSE && git commit -m "chore: add MIT license"
```

The user pushes with the line the hook prints.

- [ ] **Step 4: Verify after the user pushes.**

```bash
gh api repos/Sumanthreddy-DE/resume-assistant --jq .license.spdx_id
```

Expected: `MIT`. GitHub's license detection can lag a minute; retry once before reporting a failure.

---

### Task 5: Stop tracking SimReady session files

**Files (repo `Sumanthreddy-DE/simready`, branch `main`):**
- Untrack: `Archive/sessions/2026-04-21-SimReady-session.tmp`, `...-04-22-...`, `...-04-23-...`, `...-04-24-...`
- Modify: `.gitignore` (append one rule)

Why: these are Claude Code session dumps in a pinned, recruiter-facing repo. cortex removed its equivalent on 2026-10-07.

Context: the local SimReady clones are on other branches (`Projects/Mech/SimReady` on `sp1-bench`, `Projects/Mech/SimReady-gencad` on `gencad`), and other sessions use them. Do not touch them. Work in a fresh clone. Archive files are move-only and never deleted, so back them up first: once those branches merge the new `main`, git deletes the files from their working trees.

- [ ] **Step 1: Back up the files.** `Projects/_archive/` is the existing graveyard folder.

```bash
mkdir -p "C:/Users/suman/Desktop/Docs/Job/Projects/_archive/SimReady-sessions-2026-04"
cp "C:/Users/suman/Desktop/Docs/Job/Projects/Mech/SimReady/Archive/sessions/"2026-04-2*-SimReady-session.tmp "C:/Users/suman/Desktop/Docs/Job/Projects/_archive/SimReady-sessions-2026-04/"
ls "C:/Users/suman/Desktop/Docs/Job/Projects/_archive/SimReady-sessions-2026-04/" | wc -l
```

Expected: `4`. If the source files are not in that checkout, copy them from the fresh clone after Step 2 instead.

Then append one line to `Projects/_archive/README.md` with the Edit tool (match the file's existing entry format):
`SimReady-sessions-2026-04/: four April 2026 SimReady session dumps, untracked from the public simready repo on 2026-10-10.`

- [ ] **Step 2: Clone and untrack.**

```bash
cd "$TMP" && gh repo clone Sumanthreddy-DE/simready sr-untrack && cd sr-untrack
git ls-files 'Archive/sessions/*.tmp'      # expect the 4 files
git rm --cached -q Archive/sessions/*.tmp
```

- [ ] **Step 3: Ignore them going forward.** Append to `.gitignore` with the Edit tool:

```
# Claude Code session dumps: local only (public repo)
Archive/sessions/*.tmp
```

Check the rule works with a positive control:

```bash
git check-ignore -v Archive/sessions/2026-04-21-SimReady-session.tmp   # expect a match on the new rule
```

- [ ] **Step 4: Commit.**

```bash
git add .gitignore && git commit -m "chore: stop publishing local session dumps, gitignore them"
git show --stat HEAD     # expect 4 deletions + .gitignore
```

Note in the report: the files remain in git history. Purging them would mean rewriting history, which is out of scope.

---

### Task 6: Pins (user does this in the browser)

GitHub has no API for profile pins. The agent asks the user to do this:

- [ ] **Step 1: Hand the user these steps.**
  1. Open https://github.com/Sumanthreddy-DE, click **Customize your pins**.
  2. Select exactly these six: `PINN-for-composite-interface-identification`, `simready`, `resume-assistant`, `NX-Constraints-training`, `anny-booking-bot`, `self-talk-coach`. Untick everything else.
  3. Drag them into that order. Save.

- [ ] **Step 2: Verify after the user confirms.**

```bash
gh api graphql -f query='{user(login:"Sumanthreddy-DE"){pinnedItems(first:6){nodes{... on Repository{name}}}}}' --jq '.data.user.pinnedItems.nodes[].name'
```

Expected: the six names in the order above. The query runs as the owner, so private anny-booking-bot is listed. Anonymous visitors see 5 pins; the user accepted that.

---

### Task 7: Final verification and close-out

- [ ] **Step 1: Confirm the pushes landed** (after the user ran each push line):

```bash
cd "C:/Users/suman/Desktop/Docs/Job/Projects/Sumanthreddy-DE" && git fetch && git rev-list --left-right --count main...origin/main   # expect 0 0
gh api repos/Sumanthreddy-DE/simready/contents/Archive/sessions 2>&1 | head -3      # expect no .tmp entries (or 404 if the folder is now empty)
gh api repos/Sumanthreddy-DE/resume-assistant --jq .license.spdx_id                 # expect MIT
```

- [ ] **Step 2: Check the live profile.**

```bash
gh api repos/Sumanthreddy-DE/Sumanthreddy-DE/readme --jq .content | base64 -d | grep -c 'resume-assistant'   # expect >= 2
```

- [ ] **Step 3: Close the plan.** Set `**Status:** done` and `**Last verified:**` to today's date at the top of this file, then move it:

```bash
git mv docs/exec-plans/active/2026-10-10-github-profile-ai-refresh.md docs/exec-plans/completed/ && git commit -m "docs: close the profile AI refresh plan"
```

- [ ] **Step 4: Report to the user**, then suggest `/save-session` so `STATE.md` records the result. Include:
  - Each task: done or skipped, with the verification output.
  - Open question: archive the `ai-eng-tracker` repo too, or leave it unarchived and just unfeatured?
  - Reminder: the SimReady files are still in git history, and the backup is in `Projects/_archive/SimReady-sessions-2026-04/`.
