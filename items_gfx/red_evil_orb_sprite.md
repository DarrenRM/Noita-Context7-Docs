---
title: Red Evil Orb Sprite
category: items_gfx
---

---

# Red Evil Orb Sprite

This documentation describes the sprite definition for the "Red Evil Orb" item in Noita, focusing on its visual representation and animation.

## Sprite Definition

The `<Sprite>` tag defines the primary visual asset for the item.

### Key Attributes:

*   **`filename`**: Specifies the path to the sprite image file.
    *   `data/items_gfx/orbs/orb_red_evil.png`
*   **`offset_x`**: Horizontal offset for the sprite's position.
    *   `20`
*   **`offset_y`**: Vertical offset for the sprite's position.
    *   `48`
*   **`default_animation`**: The name of the animation to play by default.
    *   `default`

## Animation Definition

The `<RectAnimation>` tag defines how the sprite animates.

### Key Attributes:

*   **`name`**: The identifier for this animation.
    *   `default`
*   **`pos_x`**: Starting X-coordinate within the sprite sheet for the animation.
    *   `0`
*   **`pos_y`**: Starting Y-coordinate within the sprite sheet for the animation.
    *   `0`
*   **`frame_count`**: The total number of frames in the animation.
    *   `7`
*   **`frame_width`**: The width of each individual animation frame.
    *   `40`
*   **`frame_height`**: The height of each individual animation frame.
    *   `50`
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before advancing.
    *   `0.12`
*   **`frames_per_row`**: The number of frames arranged horizontally in the sprite sheet.
    *   `7`
*   **`loop`**: Determines if the animation should repeat.
    *   `1` (meaning it loops)