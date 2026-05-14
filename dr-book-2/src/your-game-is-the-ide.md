# Your Game is the IDE

A running thread through this book is that the best tools for developing a game are often _inside_ the game itself. This appendix collects all the dev tools we built, explains the philosophy behind them, and suggests where to take the idea further.

## The Thread

Each chapter left behind something useful:

| Chapter | Dev Tool |
|---------|----------|
| 1 — Movement | Debug state overlay (F1) |
| 2 — The World | Tile inspector (click to inspect) |
| 3 — Shoot and Hit | Slow-motion toggle |
| 4 — Enemies | Spawn-at-cursor, entity counter |
| 5 — Pathfinding | A* visualizer |
| 6 — Render Targets | Full-size debug map mode |
| 7 — Light and Shadow | Light probe tool |
| 8 — Particles | Particle emitter playground |
| 9 — Game Juice | Juice intensity slider |
| 10 — Shaders | Shader parameter tweaker |
| 11 — Level Editor | The whole chapter |

## Why In-Game Tools

<!-- TODO: iteration speed argument — not switching to an external tool, not restarting the game.
         The console as REPL, DR's live reload, simulation speed control.
         These aren't nice-to-haves; they're the difference between a two-second iteration loop and a thirty-second one. -->

## The DEV Constant

<!-- TODO: wrapping all of this behind `DEV = $gtk.args.gtk.platform? :development` or a similar check,
         so none of it ships to players. -->

## Going Further

<!-- TODO: network inspection tools, replay recording, automated testing with headless DR,
         the idea of building a "developer mode" that external contributors can use. -->
