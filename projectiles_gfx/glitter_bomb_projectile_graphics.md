---
title: Glitter Bomb Projectile Graphics
category: projectiles_gfx
---

# Glitter Bomb Projectile Graphics

This documentation describes the graphical assets for the "glitter_bomb" projectile in Noita.

## Sprite

The primary sprite definition for the glitter bomb projectile.

### Key Attributes:

*   **filename**: `data/projectiles_gfx/glitter_bomb.png` - The path to the image file used for the projectile's appearance.
*   **offset\_x**: `4` - Horizontal offset for the sprite's position.
*   **offset\_y**: `5.5` - Vertical offset for the sprite's position.

## RectAnimation

Defines the animation for the projectile's sprite.

### Key Attributes:

*   **name**: `default` - The name of this animation state.
*   **frame\_count**: `1` - The total number of frames in the animation.
*   **frame\_width**: `10` - The width of each individual animation frame.
*   **frame\_height**: `10` - The height of each individual animation frame.
*   **frame\_wait**: `0.2` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `10` - The number of frames arranged horizontally within the sprite sheet.
*   **loop**: `0` - Indicates whether the animation should loop (0 for no, 1 for yes). In this case, it does not loop.