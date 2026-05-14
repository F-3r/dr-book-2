# Introduction

<!-- TODO: cover image -->

_Building Games with DragonRuby: Dragon's Keep_ is the follow-up to _Building Games with DragonRuby_. If you haven't read that one yet, go do that first. We'll be here when you get back.

This book is aimed at developers who have already shipped at least one game with DragonRuby Game Toolkit and want to go further. We'll build a complete top-down action game called _Dragon's Keep_ — a dungeon shooter with huge maps, smart enemies, dynamic lighting, post-effect shaders, and the kind of game feel that makes hitting an enemy actually satisfying.

## What We'll Make

<!-- TODO: screenshot of finished Dragon's Keep -->

_Dragon's Keep_ is a top-down dungeon shooter. You're a dragon. Adventurers keep invading your keep. You breathe fire at them until they stop. It's that kind of game.

Over the course of the book you'll build:

- A scrolling tile-based world larger than the screen
- A camera that follows the player through it
- Mouse and gamepad aiming with directional projectiles
- Enemies that navigate around walls using A* pathfinding
- A minimap powered by render targets
- A dynamic lighting system using blend modes
- A particle system for explosions and muzzle flash
- Vlambeer-style game juice: screen shake, hit freeze, hit flash
- Post-effect shaders for chromatic aberration and screen distortion
- An in-game level editor to design and save your own dungeons

Every chapter adds both a new game system _and_ a developer tool you can use while building the game. By the end, the game itself is your IDE.

## Who This Is For

You've finished _Building Games with DragonRuby_ (or equivalent). You've spent a few months playing around with DragonRuby on your own. You know what `tick` is and why it runs 60 times a second. You've made at least one game that you shipped, even if it was small and a little rough.

You don't need to be a Ruby expert. You don't need computer science credentials. But you should be comfortable reading and writing Ruby, and not frightened by a method that's more than five lines long.

## DragonRuby 7

This book targets DragonRuby Game Toolkit 7, which ships with an SDL3 backend. The headline features — post-effect shaders, raw geometry rendering, affine texture transforms, pixel-perfect rendering — open up techniques that simply weren't practical before. We'll use them.

The first chapter is a tour of what's new. If you're already on DR7, skim it. If you're still on DR6, read it closely.

## The Philosophy: Fix It When It Hurts

We're not building a framework on top of DragonRuby. We're not going to add abstraction layers "for cleanliness." When a single method and some state on `args.state` gets the job done, that's what we use. When the code genuinely starts to hurt — when the same logic is duplicated in three places, when a method is doing six different things, when you can't remember what a variable is for — _that's_ when we reach for classes or modules.

Ruby is expressive enough that we don't need much scaffolding. DragonRuby is fast enough that we don't need to over-engineer. Trust the engine. Fix it when it hurts.

## How to Read This Book

Each chapter builds on the last. Don't skip around on a first read. The game won't work if you jump to the pathfinding chapter without the tile map from chapter two.

[All source code is on GitHub](https://github.com/DragonRidersUnite/dr-book-2/tree/main/src/code) organized by chapter if you want to check your work or copy-paste something.

Let's build something.
