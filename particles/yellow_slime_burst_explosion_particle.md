---
title: Yellow Slime Burst Explosion Particle
category: particles
---

# Yellow Slime Burst Explosion Particle

This document describes the configuration for a yellow slime burst explosion particle effect in Noita, intended for AI-assisted modding.

## Sprite Configuration

The `Sprite` element defines the visual appearance and animation of the particle.

### Key Attributes:

*   `default_animation`: Specifies the name of the default animation to play.
    *   Value: `explosion`
*   `filename`: The path to the sprite sheet containing the particle's frames.
    *   Value: `data/particles/explosion_032_slimeburst_yellow.png`
*   `offset_x`: Horizontal offset for the sprite's origin.
    *   Value: `16`
*   `offset_y`: Vertical offset for the sprite's origin.
    *   Value: `16`

### RectAnimation: `explosion`

This nested element defines the parameters for the rectangular animation sequence.

#### Key Attributes:

*   `frame_count`: The total number of frames in the animation.
    *   Value: `7`
*   `frame_height`: The height of each individual frame.
    *   Value: `33`
*   `frame_wait`: The duration (in seconds) each frame is displayed before advancing.
    *   Value: `0.04`
*   `frame_width`: The width of each individual frame.
    *   Value: `33`
*   `frames_per_row`: The number of frames arranged horizontally in the sprite sheet.
    *   Value: `7`
*   `loop`: Determines if the animation should loop. `0` indicates no looping.
    *   Value: `0`
*   `name`: The name of this specific animation.
    *   Value: `explosion`
*   `pos_x`: The starting X-coordinate of the animation frames within the sprite sheet.
    *   Value: `0`
*   `pos_y`: The starting Y-coordinate of the animation frames within the sprite sheet.
    *   Value: `1`
*   `shrink_by_one_pixel`: A flag to indicate if frames should shrink by one pixel.
    *   Value: `1`