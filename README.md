# Field General

A beginner-to-advanced training guide for reading coverages, blitzes, and personnel — built for football fans who also want to be a sweat in Madden and College Football on the highest difficulty.

**[Open the live page](https://claude.ai/artifact/QG6nkirT4iJ1Qe9iBZbLbW)** or open `index.html` directly.

## What's inside

Five levels, Rookie through Legend:

1. **Rookie** — formations, personnel groupings (11/12/21/10), the four-step pre-snap routine
2. **Starter** — reading coverage shells: safety count, Cover 0/1/2/3, corner alignment tells
3. **Varsity** — box count, blitz recognition, pass protection, hot routes & audibles
4. **All-Pro** — Cover 4 (quarters), Cover 6, match/pattern-match coverage, route concepts that beat each shell (mesh, four verticals, smash, dagger)
5. **Legend** — disguised coverage, situational football, and a Madden 27 / EA Sports College Football 27 controls cheat sheet

Every lesson includes a hand-drawn formation/coverage/concept diagram and an embedded checkpoint quiz. A floating "Pop Quiz" button opens an adaptive trainer that pulls questions from the full bank, scaling difficulty up or down with your streak, and tracking a running Football IQ score.

Built as a single self-contained HTML file — no build step, no dependencies beyond two Google Fonts. Progress is saved to `localStorage` in your own browser.

### In progress: Live Reps scenario trainer

A second interactive trainer, layered on top of the five levels above: instead of a fixed question bank, it procedurally generates a fresh pre-snap read every time — a formation/coverage/blitz combo you've likely never seen in that exact mix — and asks you to identify the blitzer, call the protection, or pick the hot route. Fully client-side, same as everything else here: no server, no database. See the Changelog below for build progress.

## Changelog

Each entry is one build session. Newest first.

### Phase 1 — Live Reps scenario data model (2026-09-22)
- Added the data backbone for the Live Reps trainer: 9 formations, the 6 existing coverage shells, 6 blitz packages (each with a pre-snap tell and a named free rusher), 5 protection calls, 4 hot-route pressure-beaters.
- Added `generateScenario(level, forceType)` — combines those into a scenario object (prompt, 4 shuffled choices, correct answer, explanation) and remembers the last 6 combos so you don't see an exact repeat back-to-back.
- Not wired into the page UI yet (that's Phase 2) — verified standalone with a 1,000-run integrity check (no crashes, no duplicate answer choices, correct index always valid) plus a manual review pass that caught and fixed two real bugs: a bad ordinal ("3nd and 8") and a blitz-frequency leak where the "no blitz" outcome could get drawn even when the dice said to throw pressure.
- Commit: `573f795`

### Setup — initial guide (2026-09-20)
- Five-level training guide, ~13 hand-drawn SVG diagrams, 40-question adaptive quiz bank, checkpoint quizzes per lesson, floating Pop Quiz trainer with Football IQ tracking.
- Commit: `7cd1cf2`

## Sources

Grounded in public coaching fundamentals (safety-shell reads, box counts, blitz tells, personnel groupings, pattern-match/quarters coverage) and current Madden NFL 27 / EA Sports College Football 27 mechanics. Coverage rules vary by scheme and every playbook has exceptions — treat this as a mental framework, then confirm what your own game and opponent actually show you.
