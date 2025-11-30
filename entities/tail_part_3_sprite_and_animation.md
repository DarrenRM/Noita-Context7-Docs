---
title: Tail Part 3 Sprite and Animation
category: entities
---

# Tail Part 3 Sprite and Animation

This document describes the sprite and animation data for a specific tail part entity in Noita.

## Sprite

The `Sprite` element defines the visual appearance of the tail part.

### Key Attributes:

*   **filename**: `data/entities/verlet_chains/tail/tail_parts/tail.png` - The texture file used for the sprite.
*   **offset_x**: `0` - Horizontal offset for the sprite.
*   **offset_y**: `2` - Vertical offset for the sprite.
*   **default_animation**: `stand` - The animation that plays by default.

## Animation

The `RectAnimation` element defines the "stand" animation for this tail part.

### Key Attributes:

*   **name**: `stand` - The name of this animation.
*   **pos_x**: `3` - The starting X position within the sprite sheet for this animation frame.
*   **pos_y**: `0` - The starting Y position within the sprite sheet for this animation frame.
*   **frame_count**: `1` - The total number of frames in this animation.
*   **frame_width**: `2` - The width of each animation frame.
*   **frame_height**: `4` - The height of each animation frame.
*   **frame_wait**: `1` - The duration (in game ticks) each frame is displayed.
*   **frames_per_row**: `8` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).