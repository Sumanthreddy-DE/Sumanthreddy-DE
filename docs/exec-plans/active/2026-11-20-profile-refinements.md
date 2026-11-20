# Profile refinements

**Status:** done
**Last verified:** 2026-11-20

## Approved design

Continue the user's approved option B: adaptive dark/light cards, concise personal
copy, purple titles and pink accents. Preserve existing uncommitted milestone
colour, card sizing, activity-chart deletions and Connect SVGs.

Approach: reuse Markdown, picture sources and local SVG buttons. Rebuilding all
cards as custom SVGs would sacrifice live data and the user's working stats
deployment. Keep the three requested live stats cards; remove only the duplicate
yearly activity chart. Provider typography is not identical.

Exact copy: remove based_in; include motto "Ship it. Open-source it. Move on.",
team "All employees are AI.", focus "AI agents that actually do things".
Retain the personal anime/manga line. Add two restrained Tech Stack badges
(Python, AI Agents). Use heading "Connect with me", existing button assets,
and a Komarev view counter near them. Counter measures image requests, not unique
visitors. No education, job search or Solo founder text.

## Execution

- [x] Inspect working diff, live README, account bio and reference README.
- [x] Update README.md copy, two badges and counter; preserve all three stats tiles.
- [x] Verify provider SVGs actually honour dark/light colours, and correct URLs if
      unsupported customisation is found.
- [x] Render GitHub-sanitised Markdown with local assets in desktop/mobile,
      dark/light browser contexts; inspect screenshots and overflow/image checks.
- [x] Review diff and preserve all prior edits. Leave commit approval to the user;
      never push.

## Verification / publication

Use GitHub's Markdown API for rendering, existing cached Playwright CLI for browser
checks, and temporary files under /tmp/opencode. Check link destinations, picture
source selection, image loads and mobile width. No software installation.

Initial remote main was f83e702; during this session it advanced to 726752d through
an external save/publication. That commit includes the previous local refinements:
single-colour 1B+, smaller cards, Connect SVG buttons and deleted activity charts.
Fresh live browser inspection confirms those changes and the native calendar.
Live API bio is already "Building simulation
tools and AI agents" (no terminal period). Do not retry account writes.

Only README.md and this execution record have new edits. All previous asset changes
are now committed and live in 726752d. The user subsequently approved a local
commit of the README refinements and this record. Publication remains user-only.

## Verification results

- Nine provider URLs returned HTTP 200 and valid SVG; all three live card providers
  returned the requested dark/light backgrounds and title colours.
- GitHub Markdown API rendered the actual README. Embedded only local assets for
  verification, then injected the result into the real profile DOM with GitHub CSS.
- Six browser cases passed: 1440, 390 and 320 pixel viewports, each dark and light.
  All images loaded, all four pictures selected the right source, all three button
  targets matched, and no page-wide horizontal overflow occurred.
- Visually inspected desktop dark/light and mobile screenshots. Buttons wrap cleanly.
  The code block scrolls horizontally on narrow screens; wide milestone/stat SVGs
  scale down and their small print is correspondingly small. Provider fonts and
  weights differ; widths do not make them identical.
- Verification harness correction: fresh navigation per theme avoids stale
  GitHub themed-picture component state after repeated injected theme switches.
- README checks and git diff --check passed. Final review was self-review;
  no subagents were requested. Evidence: /tmp/opencode/profile-refined-*.png,
  profile-refinements-providers.json and profile-refinements-browser-results.txt.
