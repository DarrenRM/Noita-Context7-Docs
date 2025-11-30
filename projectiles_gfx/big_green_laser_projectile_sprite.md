---
title: Big Green Laser Projectile Sprite
category: projectiles_gfx
---

# Big Green Laser Projectile Sprite

This documentation describes the sprite and animation data for the "big green laser" projectile in Noita.

## Sprite Definition

The primary sprite for this projectile is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/projectiles_gfx/laser_green_big.png` - Specifies the image file used for the sprite.
*   **offset\_x**: `2` - Horizontal offset of the sprite's origin.
*   **offset\_y**: `2.5` - Vertical offset of the sprite's origin.
*   **default\_animation**: `fireball` - The name of the animation to be used by default.

## Animation: `fireball`

The `<RectAnimation>` tag defines the animation sequence for the projectile.

### Key Attributes:

*   **name**: `fireball` - The identifier for this animation.
*   **pos\_x**: `0` - Starting X position of the animation frames within the sprite sheet.
*   **pos\_y**: `0` - Starting Y position of the animation frames within the sprite sheet.
*   **frame\_count**: `2` - The total number of frames in the animation.
*   **frame\_width**: `8` - The width of each individual animation frame.
*   **frame\_height**: `5` - The height of each individual animation frame.
*   **frame\_wait**: `0.02` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **frames\_per\_row**: `2` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop continuously (1 for true, 0 for false).