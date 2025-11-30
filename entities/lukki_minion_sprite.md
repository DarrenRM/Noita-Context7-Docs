---
title: Lukki Minion Sprite
category: entities
---

---

# Lukki Minion Sprite

This document describes the sprite data for the Lukki Minion entity in Noita.

## Sprite

The primary sprite for the Lukki Minion is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/entities/animals/lukki/lukki_feet/lukki_sprite_minion.png` - Specifies the image file used for the sprite.
*   **offset_x**: `10` - Horizontal offset of the sprite.
*   **offset_y**: `10` - Vertical offset of the sprite.

## RectAnimation

The `<RectAnimation>` tag defines the animation frames for the sprite.

### Key Attributes:

*   **name**: `stand` - The name of this animation state.
*   **pos_x**: `0` - Starting X position of the animation frames within the sprite sheet.
*   **pos_y**: `0` - Starting Y position of the animation frames within the sprite sheet.
*   **frame_count**: `1` - The total number of frames in this animation.
*   **frame_width**: `20` - The width of each individual animation frame.
*   **frame_height**: `20` - The height of each individual animation frame.
*   **frame_wait**: `0.14` - The duration (in seconds) each frame is displayed before transitioning.
*   **frames_per_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates if the animation should loop (1 for true, 0 for false).