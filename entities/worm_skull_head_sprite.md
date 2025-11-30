---
title: Worm Skull Head Sprite
category: entities
---

# Worm Skull Head Sprite

This documentation describes the sprite definition for the "worm_skull_head" enemy in Noita.

## Sprite Definition

The primary sprite for the worm skull head is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/enemies_gfx/worm_skull_head.png` - The path to the sprite image file.
*   **offset_x**: `12` - Horizontal offset for the sprite's position.
*   **offset_y**: `16` - Vertical offset for the sprite's position.
*   **default_animation**: `"stand"` - The animation to play by default.

## Animations

The sprite includes definitions for various animations.

### `eat` Animation

*   **name**: `"eat"`
*   **pos_x**: `0` - Starting X position within the sprite sheet for this animation.
*   **pos_y**: `0` - Starting Y position within the sprite sheet for this animation.
*   **frame_count**: `1` - Total number of frames in this animation.
*   **frame_width**: `24` - Width of each individual frame.
*   **frame_height**: `32` - Height of each individual frame.
*   **frame_wait**: `0.082` - Time in seconds to wait between frames.
*   **frames_per_row**: `1` - Number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates if the animation should loop (1 for true, 0 for false).