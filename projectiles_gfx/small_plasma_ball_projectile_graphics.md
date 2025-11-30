---
title: Small Plasma Ball Projectile Graphics
category: projectiles_gfx
---

---

# Small Plasma Ball Projectile Graphics

This document describes the graphical assets for the "small plasma ball" projectile in Noita, as defined in `plasmaball_small.xml`.

## Sprite Definition

The primary sprite definition for the projectile.

### Key Attributes:

*   **filename**: `data/projectiles_gfx/plasmaball_small.png` - The path to the texture file.
*   **offset\_x**: `2` - Horizontal offset for the sprite.
*   **offset\_y**: `2` - Vertical offset for the sprite.
*   **default\_animation**: `fireball` - The name of the default animation to play.

## Animation Definition

Defines the animation sequence for the projectile.

### RectAnimation: `fireball`

*   **name**: `fireball` - The identifier for this animation.
*   **pos\_x**: `0` - Starting X position within the sprite sheet.
*   **pos\_y**: `0` - Starting Y position within the sprite sheet.
*   **frame\_count**: `4` - The total number of frames in the animation.
*   **frame\_width**: `4` - The width of each individual frame.
*   **frame\_height**: `4` - The height of each individual frame.
*   **frame\_wait**: `0.02` - The duration (in seconds) each frame is displayed.
*   **frames\_per\_row**: `4` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).