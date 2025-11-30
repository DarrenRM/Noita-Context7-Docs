---
title: Holy Lance Projectile Sprite
category: projectiles_gfx
---

# Holy Lance Projectile Sprite

This documentation describes the sprite and animation data for the "Holy Lance" projectile in Noita.

## Sprite Data

The primary sprite for the holy lance projectile is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/projectiles_gfx/lance_holy.png` - Specifies the image file used for the sprite.
*   **offset\_x**: `8` - Horizontal offset of the sprite's origin.
*   **offset\_y**: `3.5` - Vertical offset of the sprite's origin.
*   **default\_animation**: `fireball` - The name of the animation to be used by default.

## Animation Data

The animation for the holy lance projectile is defined by the `<RectAnimation>` tag.

### Key Attributes:

*   **name**: `fireball` - The identifier for this animation.
*   **pos\_x**: `0` - Starting X position of the animation frame within the sprite sheet.
*   **pos\_y**: `0` - Starting Y position of the animation frame within the sprite sheet.
*   **frame\_count**: `1` - The total number of frames in the animation.
*   **frame\_width**: `18` - The width of each individual animation frame.
*   **frame\_height**: `7` - The height of each individual animation frame.
*   **frame\_wait**: `0.2` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **frames\_per\_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).