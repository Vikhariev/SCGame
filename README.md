# Orbit Merge: Reactor

A juicy, instantly-playable casual **merge roguelite**. Drop orbs, merge matching
pairs — but the **Reactor** keeps pushing new rows up from below and **speeds up**
over time, so you can never sit still. Survive waves, draft **perks** between them,
earn **Bombs** with big chains, and see how far you get before the jar overflows.

## Play

Open `index.html` in any modern browser — no build step, no dependencies, one
self-contained file. Works on desktop (mouse / keyboard) and mobile (touch).

Live: https://vikhariev.github.io/SCGame/

## How to play

- **Move** your finger / mouse to aim, **release** to drop.
- Two orbs of the **same tier merge** into the next one (number shown on each orb).
- The **Reactor** sends a rising **surge** of orbs from the floor on a timer that
  accelerates — keep merging to hold the line. If settled orbs cross the red line,
  the jar **overflows** and the run ends.
- Survive a wave's surges → **draft 1 of 3 perks**. Perks stack across the run.
- Chain **4+ merges** to earn a **💣 Bomb** — tap the bomb button to arm it, then
  drop it to blast a cluster (great for emergencies).

## Roguelite systems

- **Reactor surges** — the board fills itself; difficulty escalates within and
  across waves. This is what makes every drop a decision under pressure (and what
  removes the old "merge forever" equilibrium).
- **Waves + perk drafts** — between waves pick one of three perks:
  Coolant (slower surges), Bigger Bombs, Trigger Finger (bombs on shorter chains),
  Wild Spawns, Greed (+score), Stockpile (bombs each wave), Shield (survive an
  overflow), Quick Hands (faster drops). Builds create real run-to-run variety.
- **Special orbs** — **Bombs** (earned via chains) and **Wild** orbs (from the
  Wild perk) that match any neighbour.
- **Stars** — forge the top tier; two Stars **annihilate** for a huge bonus.

## Tech / features

- Custom lightweight 2D circle physics (gravity, collisions, restitution, substeps).
- Combo multiplier on chained merges, particle bursts, shockwave rings, screen shake.
- WebAudio sound — musical merge scale, combo pitch ladder, Star stinger (toggleable).
- First-run interactive tutorial, pause/restart, predictive landing marker.
- Lightweight analytics layer (`window.OrbitMerge.analytics.log()`; `?debug=1` to log).
- Single `CONFIG` object holds all balance knobs. Best score saved locally.
- Fully responsive canvas — scales to phone or desktop.

No frameworks, no assets — pure HTML/CSS/JS.
