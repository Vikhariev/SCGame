# Orbit Merge

A casual **merge** game on a deterministic grid, with two modes:

- **🧩 Puzzles** — 12 hand-designed levels. Each gives a specific goal and a
  limited number of drops, so every move is a decision.
- **🌋 Survival** — lava rises in real time and only your merges cool it. Stand
  still and you melt down; survive as long as you can for a high score.

- **💎 Match-3** — a juicy gem board: swap two neighbouring gems to line up 3+ of
  the same shape/colour, set off cascading chains, and score before your moves run out.
- **📅 Daily Challenge** — a Survival run seeded by the date, so everyone gets the
  same run today; chase your daily best.

Connect 2+ of the same number and they merge into the next one (chains score more).
The board only changes when *you* act — no mode can play itself.

A **day-streak**, **achievements**, and a **Stats** screen give reasons to come
back — all saved locally.

## Install it (PWA)

It's an installable Progressive Web App: open the link on your phone and choose
**Add to Home Screen**. It then launches full-screen like a native app and
**works offline**. An in-progress run is saved automatically, so you can close
and **resume** from the mode screen.

## Play

Open `index.html` in any modern browser — no build step, no dependencies, one
self-contained file. Works on desktop (mouse) and mobile (touch).

Live: https://vikhariev.github.io/SCGame/

## How to play

- **Tap a column** to drop the current orb; it falls to the bottom.
- Orbs of the **same number** that connect (up/down/left/right) **merge** into the
  next number — and merges can **chain** for bonus points.
- Each level has a **goal**: make a target number, reach a score, or **clear all
  stones** (stones break when a merge happens next to them).
- You have a fixed number of **drops**. Hit the goal before you run out to win;
  finish with drops to spare for **2–3 stars**.
- 12 levels with a rising difficulty curve; stars and unlocks are saved locally.

### Survival mode

- Lava rises continuously and **accelerates** the longer you last.
- Every **merge cools** the lava (bigger merges & chains cool more) — so you must
  keep merging to stay alive.
- Meltdown (lava reaches the top) or a jammed board ends the run. Idle = you lose,
  you never gain score for doing nothing. Best survival score saved locally.

## Why it's a real puzzle (design notes)

- **Deterministic** — each level's orb sequence is seeded, so it's the same every
  attempt: solvable and fair, not luck. (Visual randomness is kept separate from
  the gameplay RNG.)
- **The board only changes on your input** — there is no Reactor/timer feeding the
  board, so the game cannot "play itself."
- **Move limits + goals + obstacles** create the challenge; all 12 levels are
  verified solvable, and random mashing only wins the early tutorial levels.

## Tech / features

- Deterministic grid engine: drop → flood-fill same-tier components → merge →
  gravity → cascade, all resolved on each move.
- Stones as breakable obstacles; goals: reach-tier / score / clear.
- Combo/chain scoring, particle bursts, shockwave rings, screen shake.
- WebAudio sound — musical merge scale + chain pitch ladder + win jingle (toggle).
- Level select with stars, progress saved to localStorage (safe fallback if blocked).
- Fully responsive canvas. No frameworks, no assets — pure HTML/CSS/JS.

> The earlier physics "drop & merge" / Reactor experiments live in the git history.
