# Jungle Pathing

**Plan a jungler's opening route on a MOBA map, and choose it against the enemy jungler.**

A jungler's first minutes are a route: which camps, in what order, ending where. The fastest clear is only half the answer. If you are stronger than the enemy jungler early, you want to finish your route where they finish theirs and fight. If they are stronger, you want to finish on the opposite side of the map and stay out of their way. And they are making the same choice about you.

Jungle Pathing models that. It finds the best opening routes on a map, then treats the two junglers' choices as a game and computes how each should play it, including when the best answer is to keep the other side guessing.

## Status

Early days: the project is set up and planned, and the code comes next. See the [roadmap](ROADMAP.md).

## How it will work

1. **Map as a graph.** Camps, lanes and river points connected by paths with walking times. Each camp has a spawn time, gold, experience and a clear time that depends on the jungler.
2. **Route search.** The fastest routes to level 3 or 4, or to a gank window in a chosen lane, found by branch and bound with time windows.
3. **Encounters.** Each route becomes a path through space and time. Two routes meet when the junglers are close at the same moment, and each jungler's power curve decides who wins that fight.
4. **The two-jungler game.** Each jungler's candidate routes form a payoff table against the other's. Solving that zero-sum game gives each side's best mix of routes and the expected result.
5. **Map view.** Both routes animated on the map, with sliders for the power curves and a "what if they invade" mode.

The map, camps and numbers are made up. No game publisher's data or art is used.

Statistics, search and game theory: no machine learning.

## Built with

Python 3.12, NumPy and SciPy (linear programming), FastAPI with an SVG map in the browser, and pytest. The model is described in [docs/model.md](docs/model.md).

## Setup

Nothing runs yet beyond the test suite.

```bash
python -m venv .venv
.venv/bin/pip install -e ".[dev]"
.venv/bin/python -m pytest -q
```

## License

[MIT](LICENSE). Not affiliated with any game publisher.
