# Post-Effect Shaders

DR7 brings true cross-platform post-effect shaders. One codebase, consistent output everywhere. In this chapter we learn how shaders work in DR7, write our first one, and build the effects that give Dragon's Keep its visual signature: chromatic aberration on hit, screen distortion when the player takes damage, and an optional CRT scanline mode.

## What is a Post-Effect Shader?

<!-- TODO: shader runs on the GPU after the scene is rendered, operates per-pixel on the final image.
         Contrast with what we've been doing (CPU-side geometry manipulation).
         DR7 API overview: how to attach a shader to a render target. -->

## DR7 Shader API

<!-- TODO: args.outputs.shaders, GLSL basics oriented at DR game devs not graphics engineers,
         uniforms as the knobs we control from Ruby. -->

## Chromatic Aberration

<!-- TODO: split RGB channels slightly — classic "screen hit" effect.
         Controlled by a uniform: 0.0 at rest, spikes on damage, decays over ~15 frames.
         Tie into the trauma system from ch9 for free. -->

## Screen Distortion on Hit

<!-- TODO: radial distortion wave emanating from impact point — UV displacement shader.
         Short duration, high impact. -->

## CRT Scanlines (Optional Mode)

<!-- TODO: horizontal scanline overlay, vignette, slight pixel rounding.
         Toggle in settings — some players love it, some hate it.
         Good example of a purely cosmetic shader with no gameplay impact. -->

## Dev Tool: Shader Parameter Tweaker

<!-- TODO: in dev mode, expose shader uniforms in the debug overlay.
         Increment/decrement with keyboard. See changes live without restarting. -->

## Extra Credit

<!-- TODO: palette swap shader for hit/invincibility state, bloom via blur shader -->

## Summary

<!-- TODO -->

## What's Next

We have a great-looking, great-feeling game. The last major system is the level editor — and it's where the "your game is the IDE" philosophy pays off completely.
