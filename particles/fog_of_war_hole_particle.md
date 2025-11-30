---
title: Fog of War Hole Particle
category: particles
---

---

# Fog of War Hole Particle

This document describes the `fog_of_war_hole.xml` file, which defines a particle effect used in Noita. This particle is likely responsible for creating the visual effect of a "hole" or clearing in the fog of war.

## Sprite Definition

The primary element is the `<Sprite>` tag, which defines the visual appearance and animation of the particle.

### Key Sprite Attributes:

*   **`default_animation`**: Specifies the name of the default animation to play. In this case, it's "explosion".
*   **`filename`**: The path to the image file used for the sprite.
    *   `data/particles/fog_of_war_hole.png`
*   **`offset_x`**: Horizontal offset for the sprite.
    *   `16`
*   **`offset_y`**: Vertical offset for the sprite.
    *   `16`

## Animation Details

The `<RectAnimation>` tag defines the specific animation sequence for the sprite.

### Key RectAnimation Attributes:

*   **`name`**: The name of this animation, matching the `default_animation` in the `<Sprite>` tag.
    *   `explosion`
*   **`frame_count`**: The total number of frames in the animation.
    *   `1` (This suggests a single-frame animation, likely a static image or a very short, non-looping effect).
*   **`frame_height`**: The height of each individual frame in pixels.
    *   `33`
*   **`frame_width`**: The width of each individual frame in pixels.
    *   `33`
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before advancing.
    *   `0.02`
*   **`frames_per_row`**: How many frames are arranged horizontally in the sprite sheet.
    *   `3`
*   **`loop`**: Whether the animation should loop.
    *   `0` (Indicates the animation does not loop).
*   **`pos_x`**: The X-coordinate of the top-left corner of the animation frame within the sprite sheet.
    *   `0`
*   **`pos_y`**: The Y-coordinate of the top-left corner of the animation frame within the sprite sheet.
    *   `1`
*   **`shrink_by_one_pixel`**: A flag that might affect how the sprite is rendered or scaled.
    *   `1`

This particle definition is straightforward, indicating a single, non-looping frame with specific dimensions and offsets, likely used to create a brief visual cue for fog of war manipulation.