---
title: Ghost Crystal Sprite
category: buildings_gfx
---

# Ghost Crystal Sprite

This document describes the sprite data for the Ghost Crystal in Noita.

## Sprite Definition

The main `Sprite` element defines the visual asset and its default animation.

### Key Attributes:

*   **filename**: `data/buildings_gfx/ghost_crystal.png` - The path to the sprite image file.
*   **offset_x**: `12` - Horizontal offset for the sprite's origin.
*   **offset_y**: `22` - Vertical offset for the sprite's origin.
*   **default_animation**: `"stand"` - The animation to play by default.

## Animations

### `stand` Animation

This animation defines the standing pose for the Ghost Crystal.

#### Key Attributes:

*   **name**: `"stand"` - The name of this animation.
*   **pos_x**: `"0"` - X-coordinate of the animation's starting position within the sprite sheet.
*   **pos_y**: `"0"` - Y-coordinate of the animation's starting position within the sprite sheet.
*   **frame_count**: `"8"` - The total number of frames in this animation.
*   **frame_width**: `"24"` - The width of each individual frame.
*   **frame_height**: `"24"` - The height of each individual frame.
*   **frame_wait**: `"0.25"` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **frames_per_row**: `"8"` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `"1"` - Indicates that the animation should loop (1 for true, 0 for false).