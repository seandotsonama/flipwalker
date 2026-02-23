# FlipWalker

A random walk simulator that visualizes the classic "drunkard's walk" problem on a 2D city grid — with two modes of randomness.

## The Concept

You start at HOME (0, 0) and walk one block north. At every intersection, randomness decides your next move:

### Coin Flip Mode
- **Heads** — turn left (relative to the direction you're facing)
- **Tails** — turn right (relative to the direction you're facing)

### D4 Dice Mode
Roll a 4-sided die:
- **1** — go straight (keep current direction)
- **2** — turn left
- **3** — turn right
- **4** — turn backward (180°)

Walk one block in your new direction. Repeat until you either **return home** or hit the **maximum number of flips/rolls**.

The question: *How often do you actually make it back? And does a D4 change the odds?*

## Features

- **Two walk modes** — Coin Flip (left/right only) or D4 Dice (straight/left/right/backward) via dropdown selector
- **Interactive grid** with pan (click-drag) and zoom (scroll wheel or buttons)
- **Dynamic grid expansion** — the grid grows in 20-unit chunks as the walker explores
- **Animated or instant mode** — watch step-by-step with a configurable delay, or run thousands of trials instantly
- **Multi-trial support** — run N simulations back-to-back with all paths overlaid in different colors
- **Start / Pause / Resume / Reset** controls
- **"Avg Point of No Return" circle** — a dashed red circle showing the average farthest distance reached by walkers who never made it home. Once you cross it, odds are you're lost.
- **Color-coded graphs** — quickly see which trials made it home in 4 blocks (the minimum), which took longer, and which got lost

## Stats Tracked

| Stat | Description |
|------|-------------|
| Trial | Current trial / total trials |
| Flips/Rolls | Coin flips or dice rolls in the current trial |
| Blocks Walked | Steps taken in the current trial |
| Farthest from Home | Max straight-line distance from (0,0) in the current trial (Euclidean, rounded) |
| % Made It Home | Percentage of completed trials that returned to (0,0), with counts |
| Avg Point of No Return | Average max distance of "lost" trials (hit max flips/rolls without returning) |
| Position | Current (x, y) coordinates |
| Facing | Current compass direction (N/E/S/W) |

## Graphs

1. **Blocks Walked per Trial** — Green = 4 blocks (minimum round trip), Yellow = made it home (> 4 blocks), Red = hit max flips/rolls
2. **Farthest Distance per Trial** — Green for 4-block trips, Purple for everything else
3. **Reserved** — Empty graph with axes ready for a future metric

## Controls

| Control | Description |
|---------|-------------|
| Mode | Switch between Coin Flip and D4 Dice |
| Max Flips/Rolls | Maximum flips or rolls before a trial is terminated |
| Delay (ms) | Milliseconds between each step during animated runs (0 = frame-by-frame) |
| Trials | Number of simulations to run (default: 100) |
| Start | Begin animated simulation |
| Instant Run | Run all trials as fast as possible with no animation |
| Pause | Pause / Resume the current animated run |
| Reset | Clear all data and return to initial state |

## How to Run

Just open `index.html` in any modern browser. No build step, no dependencies, no server required.

Or public at:

https://seandotsonama.github.io/flipwalker/

```bash
open index.html
```

## Tech

Single self-contained HTML file with vanilla JavaScript and Canvas rendering. No frameworks or libraries.

## License

MIT
