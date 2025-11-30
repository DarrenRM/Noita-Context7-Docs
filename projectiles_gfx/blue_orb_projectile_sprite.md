---
title: Blue Orb Projectile Sprite
category: projectiles_gfx
---

# Blue Orb Projectile Sprite

This documentation describes the sprite definition for the "blue orb" projectile in Noita. It focuses on the visual representation and animation of this projectile.

## Sprite Definition

The primary `Sprite` element defines the base image and its properties.

### Key Attributes

*   **filename**: `data/projectiles_gfx/orb_blue.png` - Specifies the image file used for the sprite.
*   **offset\_x**: `5` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `5` - Vertical offset for the sprite's origin.
*   **default\_animation**: `fireball` - The name of the animation that plays by default.

## Animation Definition

The `RectAnimation` element defines the animation sequence for the sprite.

### Key Attributes

*   **name**: `fireball` - The identifier for this animation, referenced by `default_animation`.
*   **pos\_x**: `0` - Starting X coordinate within the sprite sheet for the animation frames.
*   **pos\_y**: `0` - Starting Y coordinate within the sprite sheet for the animation frames.
*   **frame\_count**: `4` - The total number of frames in the animation.
*   **frame\_width**: `10` - The width of each individual animation frame.
*   **frame\_height**: `10` - The height of each individual animation frame.
*   **frame\_wait**: `0.09` - The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: `4` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop continuously (1 for true, 0 for false).