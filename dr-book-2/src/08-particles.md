# Particles

Everything looks better with particles. An enemy dying is fine; an enemy dying with a burst of sparks flying outward, fading, and disappearing is satisfying. In this chapter we build a lightweight particle system and use it for explosions, muzzle flash, and impact sparks.

## What Makes a Particle

<!-- TODO: position, velocity, lifetime, color, size — StrictEntity for performance -->

## The Particle Pool

<!-- TODO: pre-allocate a fixed array, reuse dead particles instead of allocating new ones.
         Why allocation inside tick is the enemy of smooth framerates. -->

## Emitting Particles

<!-- TODO: emit(x, y, count, opts) helper method — randomized velocity cone, color range, lifetime range -->

## Explosion on Enemy Death

<!-- TODO: burst of 12-20 particles, outward spread, fade alpha over lifetime -->

## Muzzle Flash

<!-- TODO: 3-5 particles forward from firing direction, short lifetime, bright color -->

## Impact Sparks

<!-- TODO: projectile hits wall or enemy — ricochet particles -->

## Particles and the Light Layer

<!-- TODO: brief — each particle could also emit a tiny light, but the cost adds up.
         Selective approach: only explosion particles get a light. -->

## Dev Tool: Particle Emitter Playground

<!-- TODO: in dev mode, left-click emits a burst at cursor. Number keys change emitter type.
         Live-tweak count, spread, lifetime, speed from the console while watching results. -->

## Extra Credit

<!-- TODO: smoke trail on projectiles, ambient dust floating in dungeon -->

## Summary

<!-- TODO -->

## What's Next

The game is starting to feel good. In the next chapter we push the feel further with Vlambeer-style game juice.
