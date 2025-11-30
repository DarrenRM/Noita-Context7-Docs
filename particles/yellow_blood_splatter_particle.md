---
title: Yellow Blood Splatter Particle
category: guides
---

<Sprite 
  default_animation="smoke" 
  filename="data/particles/bloodsplatters/bloodsplatter_yellow_2.png" 
  offset_x="8" 
  offset_y="8" >

  <RectAnimation 
    frame_count="4" 
    frame_height="17" 
    frame_wait="0.025" 
    frame_width="17" 
    frames_per_row="8" 
    loop="0" 
    name="smoke" 
    pos_x="0" 
    pos_y="1" 
    shrink_by_one_pixel="1" >

  </RectAnimation>

</Sprite>
```

---
title: Yellow Blood Splatter Particle
category: particles
---

# Yellow Blood Splatter Particle

This document describes the configuration for a yellow blood splatter particle effect in Noita, intended for AI-assisted modding.

## Sprite Configuration

The primary configuration is handled by the `<Sprite>` tag, defining the visual appearance and animation of the particle.

### Key Attributes:

*   **`default_animation`**: Specifies the name of the default animation to play. Here, it's set to `"smoke"`.
*   **`filename`**: The path to the sprite sheet containing the particle's visual frames.
    *   `data/particles/bloodsplatters/bloodsplatter_yellow_2.png`
*   **`offset_x`**: Horizontal offset for the sprite's origin.
    *   `8`
*   **`offset_y`**: Vertical offset for the sprite's origin.
    *   `8`

## RectAnimation Configuration

The `<RectAnimation>` tag defines the specific animation sequence for the particle.

### Key Attributes:

*   **`name`**: The name of this animation, referenced by `default_animation` in the `<Sprite>` tag.
    *   `"smoke"`
*   **`frame_count`**: The total number of frames in the animation.
    *   `4`
*   **`frame_width`**: The width of each individual frame in pixels.
    *   `17`
*   **`frame_height`**: The height of each individual frame in pixels.
    *   `17`
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before transitioning to the next.
    *   `0.025`
*   **`frames_per_row`**: The number of frames arranged horizontally within the sprite sheet.
    *   `8`
*   **`loop`**: Determines if the animation should loop. `0` indicates no looping (plays once).
    *   `0`
*   **`pos_x`**: The starting X-coordinate (in frames) of the animation sequence within the sprite sheet.
    *   `0`
*   **`pos_y`**: The starting Y-coordinate (in frames) of the animation sequence within the sprite sheet.
    *   `1`
*   **`shrink_by_one_pixel`**: A flag indicating if frames should shrink by one pixel each step. `1` means enabled.
    *   `1`