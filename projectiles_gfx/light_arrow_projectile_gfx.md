---
title: Light Arrow Projectile GFX
category: projectiles_gfx
---

---

# Light Arrow Projectile GFX

This documentation describes the graphical assets for the "light_arrow" projectile in Noita, as defined in `light_arrow.xml`.

## Sprite Definition

The primary sprite for the light arrow is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/projectiles_gfx/light_arrow.png` - Specifies the texture file used for the projectile's appearance.
*   **offset_x**: `1` - Horizontal offset for the sprite's position.
*   **offset_y**: `2.5` - Vertical offset for the sprite's position.
*   **default_animation**: `fireball` - The name of the default animation to be used.

## Animation Definition

The projectile utilizes a simple animation defined by the `<RectAnimation>` tag.

### Key Attributes:

*   **name**: `fireball` - The identifier for this animation.
*   **pos_x**: `0` - Starting X position within the sprite sheet for the animation frames.
*   **pos_y**: `0` - Starting Y position within the sprite sheet for the animation frames.
*   **frame_count**: `1` - The total number of frames in this animation.
*   **frame_width**: `9` - The width of each individual animation frame.
*   **frame_height**: `5` - The height of each individual animation frame.
*   **frame_wait**: `0.2` - The duration (in seconds) each frame is displayed before advancing.
*   **frames_per_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).

This configuration defines a static, single-frame sprite that is displayed as the "fireball" animation.