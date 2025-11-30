---
title: Puff Particle 02
category: particles
---

---

# Puff Particle 02

This document describes the configuration for `puff_02.xml`, a particle effect in Noita.

## Sprite Configuration

The primary sprite for this particle is defined by the `<Sprite>` tag.

### Key Attributes:

*   **`filename`**: `data/particles/puff_02.png` - Specifies the image file used for the particle's animation.
*   **`offset_x`**: `3` - Horizontal offset for the sprite.
*   **`offset_y`**: `3` - Vertical offset for the sprite.

## Animation Details

The particle utilizes a `RectAnimation` for its visual sequence.

### Key Attributes:

*   **`name`**: `explosion` - The name of this specific animation.
*   **`frame_count`**: `3` - The total number of frames in the animation.
*   **`frame_width`**: `7` - The width of each individual frame.
*   **`frame_height`**: `7` - The height of each individual frame.
*   **`frames_per_row`**: `3` - How many frames are arranged horizontally in the sprite sheet.
*   **`frame_wait`**: `0.19` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **`loop`**: `0` - Indicates that the animation does not loop (plays once).
*   **`shrink_by_one_pixel`**: `1` - A visual effect where the particle shrinks by one pixel per frame.