---
title: Green Grenade Projectile Graphics
category: projectiles_gfx
---

---

# Green Grenade Projectile Graphics

This document details the graphical assets for the "green grenade" projectile in Noita, as defined in `grenade_green.xml`.

## Sprite Definition

The primary sprite for the green grenade is defined by the `<Sprite>` element.

### Key Attributes:

*   **filename**: `data/projectiles_gfx/grenade_green.png` - Specifies the texture file used for the projectile.
*   **offset_x**: `4` - Horizontal offset for the sprite's origin.
*   **offset_y**: `4` - Vertical offset for the sprite's origin.
*   **default_animation**: `fireball` - Sets the default animation to be played.

## Animation: `fireball`

The projectile utilizes a `RectAnimation` to define its visual sequence.

### Key Attributes:

*   **name**: `fireball` - The identifier for this animation.
*   **pos_x**: `0` - Starting X position within the sprite sheet for the animation.
*   **pos_y**: `0` - Starting Y position within the sprite sheet for the animation.
*   **frame_count**: `4` - The total number of frames in the animation.
*   **frame_width**: `8` - The width of each individual frame.
*   **frame_height**: `8` - The height of each individual frame.
*   **frame_wait**: `0.04` - The duration (in seconds) each frame is displayed before transitioning.
*   **frames_per_row**: `4` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop continuously.