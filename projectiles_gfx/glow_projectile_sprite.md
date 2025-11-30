---
title: Glow Projectile Sprite
category: projectiles_gfx
---

---

# Glow Projectile Sprite

This document describes the sprite definition for the "glow" projectile in Noita, focusing on its visual representation and animation.

## Sprite Definition

The main `<Sprite>` element defines the base image and its properties.

### Key Attributes:

*   **filename**: `data/projectiles_gfx/glow.png` - Specifies the texture file used for the sprite.
*   **offset\_x**: `32` - The horizontal offset of the sprite's origin.
*   **offset\_y**: `32` - The vertical offset of the sprite's origin.
*   **default\_animation**: `fireball` - The name of the animation to play by default.

## Animation Definition

The `<RectAnimation>` element defines how the sprite animates.

### Key Attributes:

*   **name**: `fireball` - The identifier for this animation.
*   **pos\_x**: `0` - The starting X coordinate within the sprite sheet for the animation.
*   **pos\_y**: `0` - The starting Y coordinate within the sprite sheet for the animation.
*   **frame\_count**: `1` - The total number of frames in this animation.
*   **frame\_width**: `64` - The width of each individual frame.
*   **frame\_height**: `64` - The height of each individual frame.
*   **frame\_wait**: `0.2` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `4` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates whether the animation should loop (1 for true, 0 for false).

This animation defines a single frame that is 64x64 pixels, with a frame wait of 0.2 seconds, and it loops indefinitely.