---
title: Teleport Center Sprite
category: data/buildings_gfx
---

---

# Teleport Center Sprite

This document describes the sprite definition for the Teleport Center building in Noita, focusing on key attributes relevant for AI-assisted modding.

## Sprite Definition

The `<Sprite>` element defines the visual representation of the Teleport Center.

### Key Attributes:

*   **`default_animation`**: Specifies the animation to play by default.
    *   Value: `"stand"`
*   **`filename`**: The path to the sprite image file.
    *   Value: `"data/buildings_gfx/teleport_center.png"`
*   **`offset_x`**: Horizontal offset for the sprite's origin.
    *   Value: `"48"`
*   **`offset_y`**: Vertical offset for the sprite's origin.
    *   Value: `"48"`

## Animation: `stand`

The `<RectAnimation>` element defines the "stand" animation.

### Key Attributes:

*   **`name`**: The name of this animation.
    *   Value: `"stand"`
*   **`frame_count`**: The total number of frames in the animation.
    *   Value: `"1"`
*   **`frame_width`**: The width of each individual frame.
    *   Value: `"96"`
*   **`frame_height`**: The height of each individual frame.
    *   Value: `"96"`
*   **`frame_wait`**: The time in seconds to wait between frames.
    *   Value: `"0.001"`
*   **`loop`**: Whether the animation should loop.
    *   Value: `"1"` (true)
*   **`frames_per_row`**: How many frames are arranged horizontally in the sprite sheet.
    *   Value: `"1"`
*   **`pos_x`**: The X-coordinate of the top-left corner of the animation's frame within the sprite sheet.
    *   Value: `"0"`
*   **`pos_y`**: The Y-coordinate of the top-left corner of the animation's frame within the sprite sheet.
    *   Value: `"0"`