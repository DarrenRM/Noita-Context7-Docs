---
title: Lukki Dark Sprite Emissive
category: entities
---

---

# Lukki Dark Sprite Emissive

This document describes the `lukki_dark_sprite_emissive.xml` file, which defines the visual appearance and animation for the emissive sprite of a dark lukki's feet in Noita.

## Sprite Definition

The core of this file is the `<Sprite>` element, which specifies the image file and its positioning.

### Key Attributes:

*   **filename**: `data/entities/animals/lukki/lukki_feet/lukki_dark_sprite_emissive.png`
    *   The path to the sprite image file.
*   **offset_x**: `16`
    *   Horizontal offset for the sprite's origin.
*   **offset_y**: `16`
    *   Vertical offset for the sprite's origin.

## Animation: Stand

The `<RectAnimation>` element defines the animation sequence for the sprite.

### Key Attributes:

*   **name**: `stand`
    *   The name of this animation state.
*   **pos_x**: `0`
    *   The starting X position of the animation frames within the sprite sheet.
*   **pos_y**: `0`
    *   The starting Y position of the animation frames within the sprite sheet.
*   **frame_count**: `1`
    *   The total number of frames in this animation.
*   **frame_width**: `32`
    *   The width of each individual animation frame.
*   **frame_height**: `32`
    *   The height of each individual animation frame.
*   **frame_wait**: `0.14`
    *   The duration (in seconds) each frame is displayed before transitioning to the next.
*   **frames_per_row**: `1`
    *   The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1`
    *   Indicates whether the animation should loop (1 for true, 0 for false).

This animation defines a single, static frame for the emissive sprite, suggesting it's a constant visual effect rather than a dynamic animation.