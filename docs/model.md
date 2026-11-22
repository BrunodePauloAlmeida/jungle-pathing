# The model

Starting definitions. Each one is a decision to revisit as the project grows. All numbers are made up.

## Map

- A graph of named points: camps, lane points, river points and the two bases.
- Edges carry walking time in seconds at a base movement speed.
- The map is mirrored, so both sides have the same camps and distances.

## Camps and junglers

- A camp has a first spawn time, a respawn time, gold, experience, and a base clear time.
- A jungler has a clear speed (multiplies clear times), a movement speed and a power curve: fighting strength as a function of game time, or of level and gold.
- Levels come from experience thresholds.

## Routes

- A route is an ordered list of camps from the starting point, ending at a point on the map.
- Its result: the time it reaches level 3 or 4, gold and experience at that time, health left if modeled, and where it ends.
- The search drops routes that are worse on every measure than another route ending in the same place.

## Encounters

- A route is a path through space and time: where the jungler is at every second.
- Two junglers meet when they are within a chosen distance at the same moment.
- The outcome of a meeting comes from the two power curves at that time: who is favored, and by how much.

## The game

- Each jungler picks one route from a short list of good candidates.
- The payoff of a pair of routes is the expected swing of the meeting (or no meeting) plus the difference in farm.
- This is a two-player zero-sum game. Its solution, found with linear programming, can be a mix of routes: sometimes the best play is to be unpredictable.
- Expected behavior to test: a jungler that is stronger early picks routes that finish where the enemy finishes; a jungler that is weaker early picks routes that finish on the other side.
