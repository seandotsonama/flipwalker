# FlipWalker

A random walk coin-flip simulator that visualizes the classic "drunkard's walk" problem on a 2D city grid.

## The Concept

You start at HOME (0, 0) and walk one block north. At every intersection you flip a coin:

- **Heads** — turn left (relative to the direction you're facing)
- **Tails** — turn right (relative to the direction you're facing)

Then walk one block in your new direction. Repeat until you either **return home** or hit the **maximum number of flips**.

The question: *How often do you actually make it back?*

## Features

- **Interactive grid** with pan (click-drag) and zoom (scroll wheel or buttons)
- **Dynamic grid expansion** — the grid grows in 20-unit chunks as the walker explores
- **Animated or instant mode** — watch step-by-step with a configurable delay, or run thousands of trials instantly
- **Multi-trial support** — run N simulations back-to-back with all paths overlaid in different colors
- **Start / Pause / Resume / Reset** controls
- **"Avg Point of No Return" circle** — a dashed red circle showing the average farthest distance reached by walkers who never made it home. Once you cross it, odds are you're lost.

## Stats Tracked

| Stat | Description |
|------|-------------|
| Trial | Current trial / total trials |
| Flips | Coin flips in the current trial |
| Blocks Walked | Steps taken in the current trial |
| Farthest from Home | Max straight-line distance from (0,0) in the current trial (Euclidean, rounded) |
| % Made It Home | Percentage of completed trials that returned to (0,0), with counts |
| Avg Point of No Return | Average max distance of "lost" trials (hit max flips without returning) |
| Position | Current (x, y) coordinates |
| Facing | Current compass direction (N/E/S/W) |

## Graphs

1. **Blocks Walked per Trial** — Green bars = returned home, Red bars = hit max flips
2. **Farthest Distance per Trial** — Purple bars showing peak distance from home for each trial
3. **Reserved** — Empty graph with axes ready for a future metric

## Controls

| Control | Description |
|---------|-------------|
| Max Flips | Maximum coin flips before a trial is terminated |
| Delay (ms) | Milliseconds between each step during animated runs (0 = frame-by-frame) |
| Trials | Number of simulations to run |
| Start | Begin animated simulation |
| Instant Run | Run all trials as fast as possible with no animation |
| Pause | Pause / Resume the current animated run |
| Reset | Clear all data and return to initial state |

## How to Run

Just open `index.html` in any modern browser. No build step, no dependencies, no server required.

```bash
open index.html
```

Or host it with GitHub Pages — push to a repo, enable Pages on the `main` branch, and share the link.

## Tech

Single self-contained HTML file with vanilla JavaScript and Canvas rendering. No frameworks or libraries.

## License

MIT
