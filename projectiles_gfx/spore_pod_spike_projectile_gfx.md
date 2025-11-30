---
title: Spore Pod Spike Projectile GFX
category: projectiles_gfx
---

---

# Spore Pod Spike Projectile GFX

This documentation describes the graphical assets for the "spore_pod_spike" projectile in Noita, intended for AI-assisted modding.

## Sprite

The main sprite definition for the projectile.

### Key Attributes:

*   **filename**: `data/projectiles_gfx/spore_pod_spike.png` - The path to the sprite image file.
*   **offset\_x**: `3.5` - Horizontal offset for the sprite.
*   **offset\_y**: `2.5` - Vertical offset for the sprite.
*   **default\_animation**: `"fireball"` - The name of the default animation to use.

## RectAnimation

Defines a rectangular animation for the sprite.

### Key Attributes:

*   **name**: `"fireball"` - The name of this animation.
*   **pos\_x**: `"0"` - Starting X position of the animation frame within the sprite sheet.
*   **pos\_y**: `"0"` - Starting Y position of the animation frame within the sprite sheet.
*   **frame\_count**: `"1"` - The total number of frames in the animation.
*   **frame\_width**: `"5"` - The width of each individual frame.
*   **frame\_height**: `"5"` - The height of each individual frame.
*   **frames\_per\_row**: `"1"` - The number of frames in a single row of the sprite sheet.
*   **loop**: `"0"` - Indicates if the animation should loop (0 for no loop, 1 for loop).