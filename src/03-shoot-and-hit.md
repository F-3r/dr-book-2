# Shoot and Hit

A dragon that can't breathe fire is just a large lizard. In this chapter we add mouse and gamepad aiming, a directional projectile system, and collision detection. We'll also add slow-motion to the dev toolkit — an indispensable tool for debugging fast-moving objects.

## Aiming

<!-- TODO: mouse position to world position (un-project through camera), right stick for gamepad, angle_to helper -->

## Spawning Projectiles

<!-- TODO: StrictEntity for bullets, pool vs array, fire-and-forget push to args.state.fireballs -->

## Moving Projectiles

<!-- TODO: velocity from angle, delta time mention, wrapping in a method -->

## Projectile-Tile Collision

<!-- TODO: reuse tile collision logic from ch2, destroy on hit, wall impact effect placeholder -->

## Projectile Lifetime

<!-- TODO: max distance or tick TTL to prevent infinite projectiles -->

## Dev Tool: Slow Motion Toggle

<!-- TODO: S key in dev mode halves simulation speed, lets you see what's happening frame by frame.
         Tying into DR6's simulation speed control. -->

## Extra Credit

<!-- TODO -->

## Summary

<!-- TODO -->

## What's Next

Fireballs need targets. Time to populate the dungeon with enemies.
