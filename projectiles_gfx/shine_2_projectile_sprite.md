---
title: Shine 2 Projectile Sprite
category: projectiles_gfx
---

# Shine 2 Projectile Sprite

This document describes the sprite and animation data for the "shine_2" projectile in Noita.

## Sprite Definition

The primary sprite for this projectile is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/projectiles_gfx/shine_2.png` - The path to the image file containing the projectile's visual assets.
*   **offset\_x**: `9.5` - The horizontal offset of the sprite's origin.
*   **offset\_y**: `9.5` - The vertical offset of the sprite's origin.
*   **default\_animation**: `fireball` - Specifies the default animation to be used for this sprite.

## Animation Definition

The projectile utilizes a `RectAnimation` for its visual sequence.

### Key Attributes:

*   **name**: `fireball` - The identifier for this specific animation.
*   **pos\_x**: `0` - The starting X-coordinate of the animation frames within the sprite sheet.
*   **pos\_y**: `0` - The starting Y-coordinate of the animation frames within the sprite sheet.
*   **frame\_count**: `4` - The total number of frames in this animation.
*   **frame\_width**: `19` - The width of each individual animation frame.
*   **frame\_height**: `19` - The height of each individual animation frame.
*   **frame\_wait**: `0.09` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **frames\_per\_row**: `4` - The number of animation frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop continuously (1 for true, 0 for false).