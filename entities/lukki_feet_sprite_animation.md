---
title: Lukki Feet Sprite Animation
category: entities
---

# Lukki Feet Sprite Animation

This document describes the sprite animation data for the Lukki's feet in Noita, intended for AI-assisted modding.

## Sprite Definition

The primary `<Sprite>` element defines the visual asset and its positioning.

### Key Attributes:

*   **filename**: The path to the sprite image file.
    *   `data/entities/animals/lukki/lukki_feet/lukki_sprite.png`
*   **offset_x**: Horizontal offset of the sprite.
    *   `10`
*   **offset_y**: Vertical offset of the sprite.
    *   `10`

## Animation: `stand`

The `<RectAnimation>` element defines a specific animation sequence.

### Key Attributes:

*   **name**: The identifier for this animation.
    *   `stand`
*   **pos_x**: Starting X position within the sprite sheet for this animation.
    *   `0`
*   **pos_y**: Starting Y position within the sprite sheet for this animation.
    *   `0`
*   **frame_count**: The total number of frames in this animation.
    *   `1`
*   **frame_width**: The width of each individual frame.
    *   `20`
*   **frame_height**: The height of each individual frame.
    *   `20`
*   **frame_wait**: The duration (in seconds) each frame is displayed before advancing.
    *   `0.14`
*   **frames_per_row**: The number of frames arranged horizontally in the sprite sheet.
    *   `1`
*   **loop**: Indicates if the animation should loop.
    *   `1` (True)