---
title: Boss Ghost Body Sprite
category: entities
---

# Boss Ghost Body Sprite

This documentation describes the sprite definition for the Boss Ghost's body in Noita.

## Sprite Definition

The `Sprite` element defines the visual appearance and animations for the Boss Ghost's body.

### Key Attributes:

*   **`filename`**: `data/entities/animals/boss_ghost/body.png` - Specifies the texture file used for the sprite.
*   **`offset_x`**: `24` - Horizontal offset of the sprite's origin.
*   **`offset_y`**: `31` - Vertical offset of the sprite's origin.
*   **`default_animation`**: `"stand"` - The animation that plays by default when the entity is spawned.

### Animations

#### `stand` Animation

This animation defines the "standing" pose for the Boss Ghost.

*   **`name`**: `"stand"`
*   **`pos_x`**: `0` - Starting X coordinate within the sprite sheet.
*   **`pos_y`**: `0` - Starting Y coordinate within the sprite sheet.
*   **`frame_count`**: `3` - The total number of frames in this animation.
*   **`frame_width`**: `48` - The width of each individual frame.
*   **`frame_height`**: `64` - The height of each individual frame.
*   **`frame_wait`**: `0.09` - The time in seconds to wait between frames.
*   **`frames_per_row`**: `4` - The number of frames that fit horizontally in a single row of the sprite sheet.
*   **`loop`**: `1` - Indicates that the animation should loop (1 for true, 0 for false).