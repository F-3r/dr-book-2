# What's New in DragonRuby 7

Before we start building, let's take a fast tour of what changed in DR7 and DR6. Some of it changes how we write code. All of it changes what's possible.

## The SDL3 Upgrade

DragonRuby 7 swaps out its graphics backend for SDL3. For most of your game code, this is invisible — your sprites, labels, and sounds work exactly as before. But the upgrade unlocks several capabilities that weren't feasible across all platforms before.

### Post-Effect Shaders

<!-- TODO: screenshot comparing with/without shader -->

DR7 ships with true cross-platform post-effect shaders written in a single codebase. Previous versions required platform-specific workarounds to get consistent visual output; now you write one shader and it runs the same on Windows, macOS, Linux, web, and mobile.

We'll use shaders in [Chapter 10](./10-shaders.md) for chromatic aberration, screen distortion on hit, and a CRT scanline mode.

### Raw Geometry and Affine Transforms

DR7 adds the ability to render raw geometry — triangles and quads with fine-grained control over texture coordinates via affine transforms. This powers effects that would have required pixel arrays before, at much higher performance.

### Pixel-Perfect Rendering

SDL3 provides pixel-perfect rendering natively, including improved font scaling on Windows (historically the worst offender for blurry text). You get crisp pixels without extra configuration.

## StrictEntity

<!-- TODO: code comparison -->

DR6 introduced `args.state.new_entity_strict`. Where `new_entity` gives you a flexible OpenStruct-like object, `new_entity_strict` requires you to declare all properties upfront in exchange for significantly faster property access.

For anything that gets rendered — bullets, enemies, particles — use `new_entity_strict`. The performance difference becomes noticeable once you have hundreds of entities on screen. We'll use it throughout this book.

```ruby
# OpenEntity — flexible, slower
bullet = args.state.new_entity(:bullet) do |b|
  b.x = 100
  b.y = 200
end

# StrictEntity — faster, properties declared upfront
bullet = args.state.new_entity_strict(:bullet) do |b|
  b.x = 100
  b.y = 200
  b.w = 8
  b.h = 8
  b.angle = 0
  b.active = true
end
```

## Blend Modes

DR6 formalized blend mode support across all license tiers. Every sprite and render target accepts a `blendmode` key:

| Value | Mode |
|-------|------|
| `0` | No blending |
| `1` | Alpha (default) |
| `2` | Additive |
| `3` | Modulo |
| `4` | Multiply |

Additive blending is the key to our lighting system in [Chapter 7](./07-light-and-shadow.md). Two overlapping additive sprites get _brighter_, not occluded — exactly what you want for a point light.

## Render Targets

Render targets (render-to-texture) existed before DR6 but the API was improved significantly: infinite virtual canvas, primitives cached until invalidated, full sprite attributes (color, blendmode, rotation, flip) applied to the target as a whole when you display it.

We dedicate [Chapter 6](./06-render-targets.md) to them. The minimap, the lighting layer, and the post-effect pipeline all rely on render targets.

## Input Normalization

DR6 added built-in input normalization. The engine tracks the last active input device and provides unified helpers that work regardless of whether the player is using a keyboard, gamepad, or touch screen. WASD and arrow keys are automatically aliased. Gamepad analog sticks have well-tuned dead zones.

In practice, this means our input handling code gets shorter and works correctly across devices without us doing anything special.

## Pixel Arrays — Now on All Tiers

Pixel arrays (direct byte-level texture manipulation) moved from Indie/Pro-only to all tiers in DR6. We use them in the lighting chapter for the shadow map.

## The In-Game Dev Console

DR6 ships with a full Ruby console accessible inside the running game. This isn't a limited subset — it's a full eval loop. You can inspect game state, call methods, spawn enemies, or change variables while the game is running.

Hit the backtick (`` ` ``) key in any DR game to open it.

We lean on this throughout the book. When we introduce a new system, we'll show how to poke at it from the console instead of writing a throwaway test file.

## What's Next

That's the landscape. Now let's make the game.
