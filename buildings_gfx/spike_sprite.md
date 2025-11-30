---
title: Spike Sprite
category: data/buildings_gfx
---

# Spike Sprite

This documentation describes the sprite definition for the "spike" building in Noita.

## Sprite Definition

The primary `Sprite` element defines the visual asset for the spike.

### Key Attributes

*   **filename**: `data/buildings_gfx/spike.png` - Specifies the path to the sprite image file.
*   **offset_x**: `2.5` - The horizontal offset of the sprite from its origin.
*   **offset_y**: `31` - The vertical offset of the sprite from its origin.
*   **default_animation**: `stand` - The animation to play by default when the sprite is active.

## Animations

The `Sprite` element contains one or more animation definitions.

### `stand` Animation

This animation defines the default "standing" state of the spike sprite.

#### Key Attributes

*   **name**: `stand` - The identifier for this animation.
*   **pos_x**: `0` - The starting X position within the sprite sheet for this animation.
*   **pos_y**: `0` - The starting Y position within the sprite sheet for this animation.
*   **frame_count**: `1` - The total number of frames in this animation.
*   **frame_width**: `5` - The width of each individual frame in pixels.
*   **frame_height**: `32` - The height of each individual frame in pixels.
*   **frame_wait**: `0.15` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **frames_per_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `1` - Indicates whether the animation should loop (1 for true, 0 for false).