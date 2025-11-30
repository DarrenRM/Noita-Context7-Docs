---
title: Bomb Projectile Sprite
category: projectiles_gfx
---

# Bomb Projectile Sprite

This documentation describes the sprite and animation data for the "bomb" projectile in Noita.

## Sprite Data

This section details the visual representation of the bomb projectile.

### Key Attributes

*   **filename**: `data/projectiles_gfx/bomb.png` - The path to the image file used for the sprite.
*   **offset\_x**: `6` - Horizontal offset of the sprite's origin.
*   **offset\_y**: `9` - Vertical offset of the sprite's origin.
*   **default\_animation**: `default` - Specifies the name of the animation to be used by default.

## Animation Data

This section defines the animation sequence for the bomb projectile.

### Default Animation (`default`)

*   **name**: `default` - The identifier for this animation.
*   **pos\_x**: `0` - Starting X position within the sprite sheet for the animation.
*   **pos\_y**: `0` - Starting Y position within the sprite sheet for the animation.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `12` - The width of each individual frame.
*   **frame\_height**: `12` - The height of each individual frame.
*   **frame\_wait**: `0.2` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates whether the animation should loop (0 for no loop, 1 for loop).