# Render Targets

A render target is an off-screen canvas you can draw into and then use like any other sprite. That one idea unlocks a surprising number of things: the minimap, the lighting layer, post-effect shaders, UI that doesn't scroll with the world. This chapter introduces render targets through the most immediately useful application: a live minimap.

## What is a Render Target?

<!-- TODO: mental model — a texture you can render into, then treat as a sprite.
         DR7 API: args.outputs[:target_name].sprites << ..., display with args.outputs.sprites << {path: :target_name, ...} -->

## Your First Render Target

<!-- TODO: simple example — render a colored rect to a target, display it in the corner.
         Establish the pattern before the minimap complexity. -->

## Building the Minimap

<!-- TODO: each tick, draw scaled-down tile map to :minimap target.
         Draw player dot, enemy dots.
         Display in HUD corner with a border. -->

## Minimap Performance

<!-- TODO: don't redraw every tile every tick.
         Render the static tile layer once (or on map load), update only entity dots each tick.
         Two-layer approach: :minimap_tiles (static) + :minimap_entities (dynamic). -->

## Dev Tool: Debug Map Mode

<!-- TODO: in dev mode, expand the minimap to a larger overlay showing full map, pathfinding info, spawn points.
         Same render target, different display size. -->

## Extra Credit

<!-- TODO: fog of war on the minimap — only show tiles the player has visited -->

## Summary

<!-- TODO -->

## What's Next

We know how to render to a texture. In the next chapter we use that to build a dynamic lighting system — dark corridors with point lights following the player and enemies.
