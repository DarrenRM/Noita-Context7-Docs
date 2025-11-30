---
title: Pollen Ball Projectile Graphics
category: projectiles_gfx
---

---

# Pollen Ball Projectile Graphics

This documentation describes the graphical assets for the "pollen_ball" projectile in Noita, as defined in its XML configuration file.

## Sprite Definition

The primary sprite for the pollen ball is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/projectiles_gfx/pollen_ball.png` - Specifies the path to the image file containing the projectile's visual representation.
*   **offset_x**: `7` - The horizontal offset of the sprite's origin.
*   **offset_y**: `7` - The vertical offset of the sprite's origin.
*   **default_animation**: `fireball` - The name of the default animation to be used for this sprite.

## Animation Definition

The projectile utilizes a single animation named "fireball", defined by the `<RectAnimation>` tag.

### Key Attributes:

*   **name**: `fireball` - The identifier for this animation.
*   **pos_x**: `0` - The starting X-coordinate for the animation frames within the sprite sheet.
*   **pos_y**: `0` - The starting Y-coordinate for the animation frames within the sprite sheet.
*   **frame_count**: `1` - The total number of frames in this animation.
*   **frame_width**: `14` - The width of each individual animation frame.
*   **frame_height**: `14` - The height of each individual animation frame.
*   **frame_wait**: `0.2` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **frames_per_row**: `4` - The number of animation frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop continuously (1 for true, 0 for false).