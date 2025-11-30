---
title: Verlet Chain Segment 4 Sprite
category: entities
---

# Verlet Chain Segment 4 Sprite

This document describes the sprite data for the fourth segment of the Verlet chain used by the boss centipede in Noita.

## Sprite

The primary sprite for this entity is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/entities/animals/boss_centipede/verlet_chains/verlet_piece_4.png` - Specifies the image file used for the sprite.
*   **offset_x**: `0` - Horizontal offset of the sprite.
*   **offset_y**: `0` - Vertical offset of the sprite.
*   **default_animation**: `stand` - The animation to play by default.

## Animations

### `stand` Animation

This animation defines the visual appearance and behavior of the sprite when in its default state.

#### Key Attributes:

*   **name**: `stand` - The name of the animation.
*   **pos_x**: `0` - X-coordinate of the sprite's top-left corner within the sprite sheet.
*   **pos_y**: `0` - Y-coordinate of the sprite's top-left corner within the sprite sheet.
*   **frame_count**: `1` - The total number of frames in this animation.
*   **frame_width**: `7` - The width of each individual frame in pixels.
*   **frame_height**: `7` - The height of each individual frame in pixels.
*   **frame_wait**: `1` - The number of game frames to wait before advancing to the next frame.
*   **frames_per_row**: `8` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates that the animation should loop (1 for true, 0 for false).