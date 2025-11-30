---
title: Shine Confusion Particle
category: particles
---

# Shine Confusion Particle

This document describes the configuration for the "shine_confusion" particle effect in Noita, used for visual feedback.

## Sprite Configuration

The primary visual representation of the particle is defined by the `<Sprite>` element.

### Key Attributes:

*   **`default_animation`**: Specifies the default animation to play. Here, it's set to "explosion".
*   **`filename`**: The path to the sprite sheet used for the animation.
    *   `data/particles/shine_confusion.png`

### Animation: `explosion`

The "explosion" animation defines how the sprite sheet is used to create the visual effect.

#### Key Attributes:

*   **`name`**: The name of the animation, referenced by `default_animation`.
*   **`frame_count`**: The total number of frames in the animation.
    *   `3`
*   **`frame_width`**: The width of a single frame in pixels.
    *   `6`
*   **`frame_height`**: The height of a single frame in pixels.
    *   `6`
*   **`frames_per_row`**: How many frames are arranged horizontally in the sprite sheet.
    *   `3`
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before advancing.
    *   `0.08`
*   **`loop`**: Determines if the animation should loop. `0` indicates no looping.
    *   `0`
*   **`pos_x`**: The starting X position of the animation frames within the sprite sheet (in frames).
    *   `0`
*   **`pos_y`**: The starting Y position of the animation frames within the sprite sheet (in frames).
    *   `1`
*   **`shrink_by_one_pixel`**: A flag indicating if frames should shrink by one pixel each iteration.
    *   `1`

```xml
<Sprite 
  default_animation="explosion" 
  filename="data/particles/shine_confusion.png" 
  offset_x="2.5" 
  offset_y="2.5" >

  <RectAnimation 
    frame_count="3" 
    frame_height="6" 
    frame_wait="0.08" 
    frame_width="6" 
    frames_per_row="3" 
    loop="0" 
    name="explosion" 
    pos_x="0" 
    pos_y="1" 
    shrink_by_one_pixel="1" >

  </RectAnimation>

</Sprite>
```