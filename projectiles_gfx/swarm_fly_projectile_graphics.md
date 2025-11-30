---
title: Swarm Fly Projectile Graphics
category: data/projectiles_gfx
---

# Swarm Fly Projectile Graphics

This document details the graphical assets for the "swarm_fly" projectile in Noita, as defined in `swarm_fly.xml`.

## Sprite Definition

The primary sprite for the swarm fly projectile is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/projectiles_gfx/swarm_fly.png` - Specifies the texture file used for the sprite.
*   **offset\_x**: `4.5` - The horizontal offset of the sprite's origin.
*   **offset\_y**: `4.5` - The vertical offset of the sprite's origin.
*   **default\_animation**: `"fly"` - The name of the animation to be used by default.

## Animations

The projectile utilizes a single animation named "fly".

### RectAnimation: "fly"

This animation defines how the sprite cycles through its frames.

#### Key Attributes:

*   **name**: `"fly"` - The identifier for this animation.
*   **pos\_x**: `"0"` - The starting X position of the animation frames within the sprite sheet.
*   **pos\_y**: `"0"` - The starting Y position of the animation frames within the sprite sheet.
*   **frame\_count**: `"4"` - The total number of frames in the animation.
*   **frame\_width**: `"9"` - The width of each individual frame.
*   **frame\_height**: `"9"` - The height of each individual frame.
*   **frame\_wait**: `"0.05"` - The duration (in seconds) each frame is displayed before transitioning.
*   **frames\_per\_row**: `"4"` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `"1"` - Indicates that the animation should loop continuously.