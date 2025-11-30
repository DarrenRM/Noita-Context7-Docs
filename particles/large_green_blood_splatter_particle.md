---
title: Large Green Blood Splatter Particle
category: particles
---

# Large Green Blood Splatter Particle

This documentation describes the configuration for a large green blood splatter particle effect in Noita, intended for AI-assisted modding.

## Sprite Configuration

The `Sprite` element defines the visual appearance and animation of the particle.

### Key Attributes:

*   **`default_animation`**: Specifies the name of the default animation to play. In this case, it's "smoke".
*   **`filename`**: The path to the sprite sheet containing the animation frames.
*   **`offset_x`**: The horizontal offset of the sprite's origin.
*   **`offset_y`**: The vertical offset of the sprite's origin.

```xml
<Sprite 
  default_animation="smoke" 
  filename="data/particles/bloodsplatters/bloodsplatter_large_green_1.png" 
  offset_x="16" 
  offset_y="16" >
  </Sprite>
```

## Animation Details

The `RectAnimation` element defines the specific frames and timing for the "smoke" animation.

### Key Attributes:

*   **`name`**: The name of this animation, matching `default_animation` in the `Sprite` tag.
*   **`frame_count`**: The total number of frames in the animation.
*   **`frame_width`**: The width of each individual frame.
*   **`frame_height`**: The height of each individual frame.
*   **`frames_per_row`**: The number of frames arranged horizontally in the sprite sheet.
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before transitioning to the next.
*   **`loop`**: Determines if the animation should loop. `0` indicates no looping.
*   **`pos_x`**: The starting X-coordinate of the animation frames within the sprite sheet.
*   **`pos_y`**: The starting Y-coordinate of the animation frames within the sprite sheet.
*   **`shrink_by_one_pixel`**: A flag indicating if frames should shrink by one pixel each iteration.

```xml
<RectAnimation 
  frame_count="6" 
  frame_height="33" 
  frame_wait="0.03" 
  frame_width="33" 
  frames_per_row="8" 
  loop="0" 
  name="smoke" 
  pos_x="0" 
  pos_y="1" 
  shrink_by_one_pixel="1" >
</RectAnimation>
```