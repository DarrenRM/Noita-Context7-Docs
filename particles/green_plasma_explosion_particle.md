---
title: Green Plasma Explosion Particle
category: particles
---

---

# Green Plasma Explosion Particle

This document describes the configuration for a green plasma explosion particle effect in Noita, intended for AI-assisted modding.

## Sprite Configuration

The primary visual representation of the particle is defined by the `<Sprite>` element.

### Key Attributes:

*   `default_animation`: Specifies the default animation to use, which is "explosion" in this case.
*   `filename`: The path to the sprite sheet containing the animation frames.
*   `offset_x`, `offset_y`: Adjustments to the sprite's position.

### Animation Details (`RectAnimation`):

The `<RectAnimation>` element defines the animation sequence.

#### Key Attributes:

*   `name`: The name of the animation, "explosion".
*   `frame_count`: The total number of frames in the animation (9).
*   `frame_width`, `frame_height`: Dimensions of each individual frame (9x9 pixels).
*   `frame_wait`: The duration each frame is displayed (0.01 seconds).
*   `frames_per_row`: How many frames are arranged horizontally on the sprite sheet (8).
*   `loop`: Whether the animation should loop (0 indicates no loop).
*   `pos_x`, `pos_y`: The starting position of the animation frames within the sprite sheet.
*   `shrink_by_one_pixel`: A visual effect applied to the frames (1 indicates enabled).