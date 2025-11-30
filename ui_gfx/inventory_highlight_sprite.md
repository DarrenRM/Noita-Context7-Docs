---
title: Inventory Highlight Sprite
category: ui_gfx
---

# Inventory Highlight Sprite

This document describes the `highlight.xml` file, which defines the visual appearance and animation for the inventory highlight in Noita. This is used to indicate the currently selected item in the player's inventory.

## Sprite Definition

The main `<Sprite>` element defines the base image and its properties.

### Key Attributes:

*   **`default_animation`**: Specifies the name of the animation to play by default. In this case, it's `"highlight"`.
*   **`filename`**: The path to the image file containing the sprite frames.
    *   `data/ui_gfx/inventory/highlight.png`
*   **`offset_x`**: Horizontal offset for the sprite.
    *   `9`
*   **`offset_y`**: Vertical offset for the sprite.
    *   `9`

## RectAnimation Definition

The `<RectAnimation>` element defines the specific animation sequence for the highlight.

### Key Attributes:

*   **`name`**: The name of this animation, which is referenced by `default_animation` in the `<Sprite>` tag.
    *   `highlight`
*   **`frame_count`**: The total number of frames in the animation.
    *   `2`
*   **`frame_width`**: The width of each individual frame in pixels.
    *   `19`
*   **`frame_height`**: The height of each individual frame in pixels.
    *   `19`
*   **`frames_per_row`**: How many frames are arranged horizontally in the sprite sheet.
    *   `2`
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before transitioning to the next.
    *   `0.23`
*   **`pos_x`**: The X-coordinate of the top-left corner of the animation's frame area within the sprite sheet.
    *   `0`
*   **`pos_y`**: The Y-coordinate of the top-left corner of the animation's frame area within the sprite sheet.
    *   `1`
*   **`shrink_by_one_pixel`**: A flag indicating if frames should be shrunk by one pixel.
    *   `1` (True)