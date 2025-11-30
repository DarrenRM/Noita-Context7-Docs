---
title: Explosion Particle 016
category: particles
---

---

# Explosion Particle 016

This document describes the configuration for a specific explosion particle effect in Noita, identified as `explosion_016`.

## Sprite Configuration

The primary sprite for this particle is defined by the `<Sprite>` tag.

### Key Attributes:

*   **`filename`**: `data/particles/explosion_016.png` - Specifies the image file used for the particle's visual representation.
*   **`default_animation`**: `explosion` - Sets the default animation to be played.
*   **`offset_x`**: `8` - Horizontal offset for the sprite.
*   **`offset_y`**: `8` - Vertical offset for the sprite.

## Animation Details

The `<RectAnimation>` tag defines the animation sequence for the sprite.

### Key Attributes:

*   **`name`**: `explosion` - The name of this specific animation.
*   **`frame_count`**: `9` - The total number of frames in the animation.
*   **`frame_width`**: `17` - The width of each individual frame.
*   **`frame_height`**: `17` - The height of each individual frame.
*   **`frames_per_row`**: `8` - The number of frames arranged horizontally in the sprite sheet.
*   **`frame_wait`**: `0.021` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **`loop`**: `0` - Indicates that the animation does not loop (plays only once).
*   **`pos_x`**: `0` - X-coordinate of the top-left corner of the animation within the sprite sheet.
*   **`pos_y`**: `1` - Y-coordinate of the top-left corner of the animation within the sprite sheet.
*   **`shrink_by_one_pixel`**: `1` - A flag that might affect how the sprite is rendered or scaled.