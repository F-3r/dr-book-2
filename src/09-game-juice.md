# Game Juice

Vlambeer made games that felt incredible to play — every action had weight, every hit was satisfying, every death felt earned. They were generous about explaining how: screen shake, hit freeze, camera punch, hit flash. It's not magic, it's craft. This chapter implements all of it.

## What is Game Juice?

<!-- TODO: the Vlambeer talk reference, juice vs. feel, the principle: reactions should be bigger than the action -->

## Screen Shake

<!-- TODO: trauma system (0.0-1.0), trauma decays each tick, shake magnitude = trauma^2,
         offset camera render by random * magnitude. Add trauma on hit/death/explosion. -->

## Hit Freeze

<!-- TODO: on impact, pause simulation for 2-4 frames. The most counter-intuitive juice technique.
         Implementation: freeze_frames counter, skip all update logic when > 0. -->

## Hit Flash

<!-- TODO: enemy sprite flashes white (or bright color) for 3-5 frames on damage.
         Implementation: r/g/b/a modulation on the sprite. -->

## Camera Punch

<!-- TODO: on firing, nudge camera briefly in the opposite direction of the shot.
         Different from shake — directional, single impulse, not random. -->

## Death Effects

<!-- TODO: slow-motion death (reduce simulation speed for 10 frames on kill), scale-up then fade sprite -->

## Combining Effects

<!-- TODO: the stack — a big kill: hit freeze + shake trauma + particles + enemy death slow-mo.
         Each layer is cheap; together they're devastating in a good way. -->

## Dev Tool: Juice Preview Mode

<!-- TODO: J key cycles through "dry / wet / drenched" — scales all juice intensities.
         Lets you tune without editing numbers. Also useful to show players who disable shake for accessibility. -->

## Extra Credit

<!-- TODO: controller rumble via DR's haptic API, screen flash (full-screen white frame) on boss hit -->

## Summary

<!-- TODO -->

## What's Next

The game feels great. In the next chapter we push the visual style even further with DR7's post-effect shaders.
