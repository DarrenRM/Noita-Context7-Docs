---
title: Crystal Particle Sprite Animation
category: particles
---

# Crystal Particle Sprite Animation

This document describes the sprite animation for the "crystal" particle in Noita, focusing on its visual representation and animation properties.

## Sprite Definition

The primary sprite for the crystal particle is defined by the `<Sprite>` tag.

### Key Attributes:

*   **`filename`**: `data/particles/crystal_animated.png` - Specifies the image file containing the sprite frames.
*   **`offset_x`**: `8.5` - Horizontal offset for the sprite's origin.
*   **`offset_y`**: `12` - Vertical offset for the sprite's origin.
*   **`default_animation`**: `fade` - Sets the default animation to be played.

## Animation Details: `fade`

The `fade` animation is a rectangular animation, meaning frames are arranged in a grid within the sprite sheet.

### Key Attributes:

*   **`name`**: `fade` - The name of this animation.
*   **`frame_count`**: `7` - The total number of frames in this animation.
*   **`frame_width`**: `18` - The width of each individual frame.
*   **`frame_height`**: `25` - The height of each individual frame.
*   **`frames_per_row`**: `8` - The number of frames arranged horizontally in the sprite sheet.
*   **`frame_wait`**: `0.025` - The duration (in seconds) each frame is displayed before transitioning to the next.
*   **`loop`**: `0` - Indicates that the animation does not loop (plays once).
*   **`shrink_by_one_pixel`**: `1` - Suggests a visual effect where the sprite might appear to shrink slightly.
*   **`pos_x`**: `0` - The starting X position of the animation frames within the sprite sheet.
*   **`pos_y`**: `1` - The starting Y position of the animation frames within the sprite sheet.