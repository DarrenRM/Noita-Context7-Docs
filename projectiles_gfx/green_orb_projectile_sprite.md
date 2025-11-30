---
title: Green Orb Projectile Sprite
category: projectiles_gfx
---

---

# Green Orb Projectile Sprite

This documentation describes the sprite and animation data for the "green orb" projectile in Noita, intended for AI-assisted modding.

## Sprite Definition

The primary sprite for the green orb projectile is defined by the `<Sprite>` tag.

### Key Attributes:

*   **`filename`**: Specifies the texture file used for the sprite.
    *   `data/projectiles_gfx/orb_green.png`
*   **`offset_x`**: Horizontal offset for the sprite's origin.
    *   `5`
*   **`offset_y`**: Vertical offset for the sprite's origin.
    *   `5`
*   **`default_animation`**: The name of the animation to play by default.
    *   `fireball`

## Animation Definition

The projectile utilizes a rectangular animation for its visual effect.

### Key Attributes of `RectAnimation` (named "fireball"):

*   **`name`**: The identifier for this animation.
    *   `fireball`
*   **`pos_x`**: Starting X position within the sprite sheet.
    *   `0`
*   **`pos_y`**: Starting Y position within the sprite sheet.
    *   `0`
*   **`frame_count`**: Total number of frames in the animation.
    *   `4`
*   **`frame_width`**: Width of each individual frame.
    *   `10`
*   **`frame_height`**: Height of each individual frame.
    *   `10`
*   **`frame_wait`**: Time in seconds to wait between frames.
    *   `0.09`
*   **`frames_per_row`**: Number of frames arranged horizontally in the sprite sheet.
    *   `4`
*   **`loop`**: Indicates if the animation should loop.
    *   `1` (true)