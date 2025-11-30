---
title: Plasma Explosion 016 (Red) Particle
category: particles
---

# Plasma Explosion 016 (Red) Particle

This document describes the `explosion_016_plasma_red.xml` particle definition, used for a specific red plasma explosion effect in Noita.

## Sprite Definition

The `Sprite` element defines the visual appearance and animation of the particle.

### Key Attributes:

*   **`filename`**: `data/particles/explosion_016_plasma_red.png` - Specifies the texture file for the sprite.
*   **`offset_x`**: `8` - Horizontal offset for the sprite's origin.
*   **`offset_y`**: `8` - Vertical offset for the sprite's origin.

### Animation: `explosion`

The `RectAnimation` element defines the sprite sheet animation.

#### Key Attributes:

*   **`name`**: `explosion` - The name of this animation.
*   **`frame_count`**: `9` - The total number of frames in the animation.
*   **`frame_width`**: `17` - The width of each individual frame.
*   **`frame_height`**: `17` - The height of each individual frame.
*   **`frames_per_row`**: `8` - The number of frames arranged horizontally in the sprite sheet.
*   **`frame_wait`**: `0.021` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **`loop`**: `0` - Indicates that the animation does not loop (plays once).
*   **`shrink_by_one_pixel`**: `1` - Suggests a visual effect where the sprite shrinks by one pixel per frame.
*   **`pos_x`**: `0` - X-coordinate within the sprite sheet for the animation's starting frame.
*   **`pos_y`**: `1` - Y-coordinate within the sprite sheet for the animation's starting frame.