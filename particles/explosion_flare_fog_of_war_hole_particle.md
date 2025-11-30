---
title: Explosion Flare Fog of War Hole Particle
category: particles
---

# Explosion Flare Fog of War Hole Particle

This document describes the configuration for a particle effect used in Noita, specifically an explosion flare that creates a "fog of war" hole.

## Sprite Configuration

The `Sprite` element defines the visual appearance and animation of the particle.

### Key Attributes:

*   **`default_animation`**: Specifies the name of the default animation to play. Here, it's set to `"explosion"`.
*   **`filename`**: The path to the sprite sheet containing the animation frames.
    *   `data/particles/explosion_flare_fog_of_war_hole.png`
*   **`offset_x`**: Horizontal offset for the sprite.
    *   `16`
*   **`offset_y`**: Vertical offset for the sprite.
    *   `16`

## RectAnimation Configuration

The `RectAnimation` element defines the specific animation sequence.

### Key Attributes:

*   **`name`**: The name of this animation, referenced by `default_animation`.
    *   `"explosion"`
*   **`frame_count`**: The total number of frames in the animation.
    *   `3`
*   **`frame_width`**: The width of each individual frame.
    *   `33`
*   **`frame_height`**: The height of each individual frame.
    *   `33`
*   **`frames_per_row`**: How many frames are arranged horizontally in the sprite sheet.
    *   `3`
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before advancing.
    *   `0.02`
*   **`loop`**: Whether the animation should loop. `0` indicates no looping.
    *   `0`
*   **`pos_x`**: X-coordinate within the sprite sheet for the animation's starting position.
    *   `0`
*   **`pos_y`**: Y-coordinate within the sprite sheet for the animation's starting position.
    *   `1`
*   **`shrink_by_one_pixel`**: A flag indicating if frames should shrink by one pixel.
    *   `1`