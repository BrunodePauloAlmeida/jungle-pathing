# Roadmap

**Where this is going:** pick two junglers, see each one's best opening route against the other, and understand why: the fight they want, or the fight they avoid.

## Constraints that shape this plan (November 2026)

- **Built and tested offline.** The map, camps and numbers are made up; no game publisher's data or art.
- **Search and game theory, not machine learning.**

## Phase 1: Map and data model

- [ ] Map format: points, paths with walking times, camps with spawn and respawn times, gold and experience.
- [ ] A made-up mirrored map with a dozen camps per side.
- [ ] Validation: every camp reachable, the map really mirrored.

## Phase 2: Route search

- [ ] Branch and bound over camp orders with time windows (a camp can't be cleared before it spawns).
- [ ] Goals: fastest level 3, fastest level 4, or arrive at a lane by a given time.
- [ ] Keep only routes not beaten on every measure.
- [ ] Checked against brute force on small maps.

## Phase 3: Encounters

- [ ] Each route as a path through space and time.
- [ ] Find when and where two routes meet.
- [ ] Power curves and the outcome of each meeting.

## Phase 4: The two-jungler game

- [ ] Candidate routes for each side and the payoff table.
- [ ] Solve the zero-sum game with linear programming; show mixed strategies.
- [ ] Best responses: "if you know they start bottom, start here".

## Phase 5: Map view

- [ ] SVG map with both routes animated over time.
- [ ] Sliders for the power curves and clear speeds.
- [ ] Explanations: why this route, and what changes it.

## Done means

- On small maps, the route search finds the same best route as brute force.
- On the full map, the search answers in under a second.
- Meeting detection is exact on hand-built cases.
- Neither jungler can gain by changing route alone in the computed solution.
- Across power curves: the stronger early jungler finishes on the enemy's side; the weaker one finishes on the opposite side.

## Open decisions

- Model health and recall, or only time, gold and experience?
- Does a fight outcome depend on time, level or both?
- How many candidate routes per side in the game?

## Later

- Scuttle and objective timers.
- Vision: what each side knows about the other's route.
- Laners' pressure on where a jungler can safely go.
