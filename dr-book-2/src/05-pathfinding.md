# Pathfinding

Enemies that can only walk in straight lines stop being threatening the moment you stand behind a wall. A* search solves this — it finds the shortest navigable path through the tile grid. In this chapter we implement A*, hook it into the enemy AI, and add a visualizer so you can watch it think.

## Why Naive Seek Breaks

<!-- TODO: show enemies getting stuck on corners, the problem with direct-line AI -->

## A* Search

<!-- TODO: explain open/closed sets, heuristic (Manhattan vs Euclidean), the algorithm step by step -->

## Implementing A* on a Tile Grid

<!-- TODO: Ruby implementation, neighbor function, obstacle check from tile map -->

## Caching Paths

<!-- TODO: don't run A* every tick — recalculate on a timer or when player moves significantly.
         Performance note: hundreds of enemies each pathfinding every frame = bad time. -->

## Smooth Movement Along a Path

<!-- TODO: following waypoints, corner cutting, not jerky tile-to-tile snapping -->

## Dev Tool: Pathfinding Visualizer

<!-- TODO: in dev mode, highlight open set (yellow), closed set (blue), current path (green) for selected enemy.
         Click an enemy to select it. This becomes genuinely useful for debugging map layouts. -->

## Extra Credit

<!-- TODO: flow fields as an alternative for many enemies sharing the same target -->

## Summary

<!-- TODO -->

## What's Next

Enemies can now find you. The dungeon is starting to feel like a real place. Let's talk about render targets — the key to the minimap, lighting, and everything visual coming up next.
