---
title: Big Pink Smoke Cloud Particle
category: guides
---

<Sprite 
  default_animation="explosion" 
  filename="data/particles/smoke_cloud_big_pink.png" 
  offset_x="12" 
  offset_y="12" >

  <RectAnimation 
    frame_count="12" 
    frame_height="25" 
    frame_wait="0.045" 
    frame_width="25" 
    frames_per_row="12" 
    loop="0" 
    name="explosion" 
    pos_x="0" 
    pos_y="1" 
    shrink_by_one_pixel="1" >

  </RectAnimation>

</Sprite>
```

---
title: Big Pink Smoke Cloud Particle
category: particles
---

# Big Pink Smoke Cloud Particle

This document describes the configuration for a "Big Pink Smoke Cloud" particle effect in Noita, intended for AI-assisted modding.

## Sprite Configuration

The primary sprite configuration defines the visual appearance and animation of the particle.

### Key Attributes:

*   **`default_animation`**: Specifies the name of the default animation to play. Here, it's set to `"explosion"`.
*   **`filename`**: The path to the sprite sheet containing the particle's frames. In this case, it's `"data/particles/smoke_cloud_big_pink.png"`.
*   **`offset_x`**: The horizontal offset of the sprite's origin. Set to `12`.
*   **`offset_y`**: The vertical offset of the sprite's origin. Set to `12`.

## RectAnimation: "explosion"

This section details the parameters for the `"explosion"` animation, which dictates how the sprite frames are sequenced.

### Key Attributes:

*   **`name`**: The identifier for this animation, `"explosion"`.
*   **`frame_count`**: The total number of frames in the animation. Set to `12`.
*   **`frame_width`**: The width of each individual frame in pixels. Set to `25`.
*   **`frame_height`**: The height of each individual frame in pixels. Set to `25`.
*   **`frames_per_row`**: The number of frames arranged horizontally in the sprite sheet. Set to `12`.
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before transitioning to the next. Set to `0.045`.
*   **`loop`**: Determines if the animation should loop. `0` indicates no looping (it plays once).
*   **`pos_x`**: The starting X position of the animation frames within the sprite sheet. Set to `0`.
*   **`pos_y`**: The starting Y position of the animation frames within the sprite sheet. Set to `1`.
*   **`shrink_by_one_pixel`**: A boolean-like attribute (represented by `1` for true) that causes each frame to shrink by one pixel after each animation cycle. This creates a fading or shrinking effect.