# Building Games with DragonRuby: Dragon's Keep — Session Handover

## What This Is

A second edition of the open-source book "Building Games with DragonRuby" by Brett Chalupa.

- **Book title:** Building Games with DragonRuby: Dragon's Keep
- **Game built throughout the book:** Dragon's Keep — a top-down dungeon shooter
- **Engine target:** DragonRuby Game Toolkit 7 (DR7, SDL3 backend, rolling out now)
- **Format:** mdBook, same toolchain as book 1 (`/home/user/dr-book`)
- **Audience:** Mid-level — assumes reader finished book 1 and spent a few months tinkering with DR on their own

## Book 1 Reference

The first book lives at `/home/user/dr-book`. Read a few chapters there before drafting anything here — the voice and structure must match closely. Key traits:

- Warm, personal, mildly irreverent tone (Brett Chalupa's voice)
- Explains concepts *while building*, never in a vacuum
- One mechanic per chapter, always advancing the same game
- `## Extra Credit` section at end of each chapter (optional challenges)
- `## Summary` then `## What's Next` to close each chapter
- Code shown incrementally, not all at once
- `{{#include code/chapter_NN/...}}` directives for mdBook to pull in real runnable code
- Screenshots at key visual milestones

## Philosophy

**"Fix it when it hurts."** Don't build abstractions ahead of need. When a single method and `args.state` global state gets the job done, use it. Reach for classes or modules when duplication genuinely hurts. Faithful to DR's pragmatic style — not building a meta-framework on top of DR.

**"Your game is the IDE."** Every chapter adds a small developer tool *inside the game itself* — debug overlays, spawn-at-cursor, slow-motion, A* visualizer, etc. The level editor in chapter 11 is the payoff. Strip all dev tools for release builds behind a `DEV` constant.

## DR7 Key Features to Cover

Research was done in this session. Key new things for the book:

- **StrictEntity** (`args.state.new_entity_strict`) — faster property access, declare all props upfront. Use for all rendered entities (bullets, enemies, particles). Introduced in DR6.
- **Blend modes 0–4** — no blend, alpha, additive, modulo, multiply. Additive is the key to the lighting system (ch7).
- **Render targets** — improved DR6 API: infinite virtual canvas, cached primitives, full sprite attrs on the target. Used for minimap (ch6), lighting (ch7), post-effect pipeline.
- **Input normalization** (DR6) — last active device tracking, WASD/arrow alias, gamepad dead zones. Simplifies cross-device input code.
- **Post-effect shaders** (DR7/SDL3) — true cross-platform, single codebase. Used in ch10 for chromatic aberration, screen distortion, CRT mode.
- **Raw geometry + affine transforms** (DR7) — fine-grained texture control.
- **Pixel arrays** — now all tiers (DR6). Used in lighting chapter for shadow map.
- **In-game console** — full Ruby eval, backtick to open. Reference throughout as a dev tool.
- **Simulation speed control** — built into DR6 dev tools. Tie into ch3 slow-motion dev tool.

## Chapter Map

| File | Chapter | Core mechanic | Dev tool left behind |
|------|---------|--------------|---------------------|
| `00-whats-new.md` | What's New in DR7 | DR7/6 feature tour | Console patterns |
| `01-movement.md` | Top-Down Movement | 8-dir movement, input normalization, StrictEntity | Debug state overlay (F1) |
| `02-the-world.md` | The World | Tile maps, camera/viewport transform, culling, tile collision | Tile inspector |
| `03-shoot-and-hit.md` | Shoot and Hit | Mouse/stick aiming, angle math, projectiles, tile collision | Slow-motion toggle |
| `04-enemies.md` | Enemies | Spawning, health, multiple types, basic seek AI | Spawn-at-cursor + entity counter |
| `05-pathfinding.md` | Pathfinding | A* on tile grid, path caching, smooth follow | A* visualizer (open/closed/path) |
| `06-render-targets.md` | Render Targets | RTT intro → live minimap, two-layer approach | Minimap → full debug map in dev mode |
| `07-light-and-shadow.md` | Light and Shadow | Additive blend, light layer RTT, point lights | Light probe tool |
| `08-particles.md` | Particles | StrictEntity pool, explosions, muzzle flash, impact sparks | Particle emitter playground |
| `09-game-juice.md` | Game Juice | Screen shake (trauma), hit freeze, hit flash, camera punch | Juice intensity toggle |
| `10-shaders.md` | Post-Effect Shaders | DR7 shader API, chromatic aberration, distortion, CRT | Shader param tweaker in overlay |
| `11-level-editor.md` | The Level Editor | In-game tile painter, undo, save/load JSON | The whole chapter is the dev tool |
| `12-ship-it.md` | Ship It! | Strip dev tools, polish, publish | — |

Plus appendices: `your-game-is-the-ide.md`, `outro.md`, `dragonruby-resources.md`.

## State of the Repo

**Done:**
- Full mdBook scaffold (book.toml, SUMMARY.md, GitHub Actions deploy workflow)
- `src/introduction.md` — fully drafted
- `src/00-whats-new.md` — fully drafted (DR6/7 feature tour)
- All 12 chapter stubs with section headings and `<!-- TODO -->` markers
- Appendix stubs

**Not done:**
- No real chapter content yet (all stubs)
- No code samples in `src/code/`
- No screenshots in `src/img/`
- No GitHub remote (repo is local only at `/home/user/dr-book-2`)

## Immediate Next Step

Draft Chapter 1: `src/01-movement.md`. This is the highest priority because it:
- Establishes the code style and StrictEntity pattern everything else builds on
- Sets up the project structure readers will use for the rest of the book
- Introduces the debug overlay pattern that recurs every chapter

Before drafting code, you'll want to verify the actual DR7 API by checking:
- `https://docs.dragonruby.org` — official docs
- `https://docs.dragonruby.org/changelog.txt` — exact version notes
- The sample apps that ship with DR7 (input normalization samples especially)

## Game Details

- **Name:** Dragon's Keep
- **Genre:** Top-down dungeon shooter
- **Protagonist:** A dragon defending their dungeon from adventurers
- **Map:** Large tile-based dungeon, multiple rooms, larger than the screen
- **Tone:** Matches book 1 — fun, not grimdark

## GitHub

No remote set up yet. When creating the GitHub repo, suggested name: `dr-book-2` under the DragonRidersUnite org or Brett's personal account. The Actions workflow is already configured and will deploy to GitHub Pages automatically on push to `main`.
