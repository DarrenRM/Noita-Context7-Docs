---
title: Pollen Projectile Graphics
category: projectiles_gfx
---

# Pollen Projectile Graphics

This documentation describes the graphical assets for the "pollen" projectile in Noita, as defined in `pollen.xml`.

## Sprite Definition

The primary sprite for the pollen projectile is defined by the `<Sprite>` tag.

### Key Attributes

*   **filename**: `data/projectiles_gfx/pollen.png` - Specifies the texture file used for the sprite.
*   **offset\_x**: `5.5` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `5.5` - Vertical offset for the sprite's origin.
*   **default\_animation**: `fireball` - The name of the animation to be used by default.

## Animation Definition

The projectile utilizes a `RectAnimation` for its visual effect.

### Key Attributes

*   **name**: `fireball` - The identifier for this animation.
*   **pos\_x**: `0` - Starting X position within the sprite sheet for the animation.
*   **pos\_y**: `0` - Starting Y position within the sprite sheet for the animation.
*   **frame\_count**: `4` - The total number of frames in the animation.
*   **frame\_width**: `11` - The width of each individual frame.
*   **frame\_height**: `16` - The height of each individual frame.
*   **frame\_wait**: `0.09` - The duration (in seconds) each frame is displayed before transitioning.
*   **frames\_per\_row**: `4` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).