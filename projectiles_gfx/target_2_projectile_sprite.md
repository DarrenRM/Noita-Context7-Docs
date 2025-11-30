---
title: Target 2 Projectile Sprite
category: projectiles_gfx
---

# Target 2 Projectile Sprite

This document describes the sprite definition for the "target2" projectile in Noita. It details the visual assets and animation properties used for this projectile.

## Sprite Definition

The `<Sprite>` element defines the primary visual component of the projectile.

### Key Attributes:

*   **filename**: `data/projectiles_gfx/target2.png` - Specifies the path to the sprite image file.
*   **offset\_x**: `12` - The horizontal offset of the sprite's origin.
*   **offset\_y**: `12` - The vertical offset of the sprite's origin.
*   **default\_animation**: `fireball` - The name of the animation to be used by default.

## Animation Definition

The `<RectAnimation>` element defines the animation sequence for the projectile.

### Key Attributes:

*   **name**: `fireball` - The identifier for this animation, referenced by `default_animation`.
*   **pos\_x**: `0` - The starting X-coordinate of the animation frames within the sprite sheet.
*   **pos\_y**: `0` - The starting Y-coordinate of the animation frames within the sprite sheet.
*   **frame\_count**: `2` - The total number of frames in the animation.
*   **frame\_width**: `24` - The width of each individual animation frame.
*   **frame\_height**: `24` - The height of each individual animation frame.
*   **frame\_wait**: `0.2` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **frames\_per\_row**: `4` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates whether the animation should loop (1 for true, 0 for false).