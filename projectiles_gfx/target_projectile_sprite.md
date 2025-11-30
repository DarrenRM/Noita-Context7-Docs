---
title: Target Projectile Sprite
category: projectiles_gfx
---

# Target Projectile Sprite

This document describes the sprite definition for the "target" projectile in Noita. It outlines the visual appearance and animation of this projectile.

## Sprite Definition

The `<Sprite>` element defines the base visual properties of the projectile.

### Key Attributes:

*   **filename**: `data/projectiles_gfx/target.png` - The path to the image file containing the projectile's sprite.
*   **offset\_x**: `12` - The horizontal offset of the sprite's origin.
*   **offset\_y**: `12` - The vertical offset of the sprite's origin.
*   **default\_animation**: `"fireball"` - The name of the animation to be used by default.

## Animation Definition

The `<RectAnimation>` element defines the animation sequence for the projectile.

### Key Attributes:

*   **name**: `"fireball"` - The identifier for this animation, matching the `default_animation` in the `<Sprite>` tag.
*   **pos\_x**: `"0"` - The starting X position within the sprite sheet for the animation.
*   **pos\_y**: `"0"` - The starting Y position within the sprite sheet for the animation.
*   **frame\_count**: `"2"` - The total number of frames in this animation.
*   **frame\_width**: `"24"` - The width of each individual frame in pixels.
*   **frame\_height**: `"24"` - The height of each individual frame in pixels.
*   **frame\_wait**: `"0.2"` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **frames\_per\_row**: `"4"` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `"1"` - Indicates whether the animation should loop (1 for true, 0 for false).