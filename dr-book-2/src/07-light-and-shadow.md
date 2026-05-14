# Light and Shadow

A dungeon should feel dark. In this chapter we build a real-time lighting system using additive blend modes and a render target — no shaders required yet. Corridors stay dim; point lights glow around the player, enemies, and projectiles.

## Additive Blending

<!-- TODO: blendmode 2 — two overlapping additive sprites get brighter, not occluded.
         Why this is perfect for lights. Quick visual demo with a circle sprite. -->

## The Light Layer

<!-- TODO: :light_layer render target, filled black each tick, then additive light sprites drawn on top.
         Multiply-blend the light layer onto the game world. -->

## The Player Light

<!-- TODO: soft radial gradient sprite at player position, sized to the player's "vision radius" -->

## Projectile Lights

<!-- TODO: small bright light following each fireball — tiny cost, huge atmosphere improvement -->

## Enemy Lights

<!-- TODO: dim red glow on enemies — makes them readable in dark corridors -->

## Performance

<!-- TODO: light sprites are cheap; the main cost is the render target pass.
         Keep the target small (match game resolution, not world size). -->

## Dev Tool: Light Probe

<!-- TODO: in dev mode, click anywhere to place a temporary test light.
         Shows radius, intensity. Useful for tuning level atmosphere before committing. -->

## Extra Credit

<!-- TODO: flicker effect on torches, colored lights -->

## Summary

<!-- TODO -->

## What's Next

The dungeon looks atmospheric. Now let's make it feel alive — particles for explosions, impacts, and muzzle flash.
