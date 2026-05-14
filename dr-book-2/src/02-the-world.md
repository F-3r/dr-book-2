# The World

A dragon in an empty void is sad. Let's give it a dungeon to fly through — a tile-based map larger than the screen, with a camera that follows the player and walls that actually stop you.

## Tile Maps

<!-- TODO: 2D array representation, tile types, loading from a simple array literal -->

## Rendering the Map

<!-- TODO: naive render-all, then visible-tile culling (only draw what's in the viewport) -->

## World Coordinates vs Screen Coordinates

<!-- TODO: the core transform: screen_x = world_x - camera_x, why this matters everywhere -->

## The Camera

<!-- TODO: camera that follows the player, clamped to map bounds, smooth follow -->

## Tile Collision

<!-- TODO: AABB vs tile, separate x and y axes to avoid corner-sticking -->

## Dev Tool: Tile Inspector

<!-- TODO: click any tile in dev mode to print its world coords and type to the console/overlay -->

## Extra Credit

<!-- TODO -->

## Summary

<!-- TODO -->

## What's Next

The dungeon exists. Now the dragon needs to defend it — let's add shooting.
