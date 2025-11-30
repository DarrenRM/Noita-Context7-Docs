---
title: Big Blue Orb Projectile Sprite
category: projectiles_gfx
---

---

# Big Blue Orb Projectile Sprite

This document describes the sprite and animation data for the "Big Blue Orb" projectile in Noita, intended for AI-assisted modding.

## Sprite Definition

The primary sprite for the projectile is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/projectiles_gfx/orb_blue_big.png` - Specifies the image file used for the sprite.
*   **offset\_x**: `8` - Horizontal offset of the sprite's origin.
*   **offset\_y**: `8` - Vertical offset of the sprite's origin.
*   **default\_animation**: `fireball` - The name of the animation that plays by default.

## Animation: `fireball`

The projectile utilizes a `RectAnimation` for its visual effect.

### Key Attributes:

*   **name**: `fireball` - The identifier for this animation.
*   **pos\_x**: `0` - Starting X position within the sprite sheet for the animation frames.
*   **pos\_y**: `0` - Starting Y position within the sprite sheet for the animation frames.
*   **frame\_count**: `4` - The total number of frames in the animation.
*   **frame\_width**: `16` - The width of each individual animation frame.
*   **frame\_height**: `16` - The height of each individual animation frame.
*   **frame\_wait**: `0.05` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **frames\_per\_row**: `4` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop continuously (1 for true, 0 for false).