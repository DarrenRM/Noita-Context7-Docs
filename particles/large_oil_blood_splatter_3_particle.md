---
title: Large Oil Blood Splatter 3 Particle
category: particles
---

# Large Oil Blood Splatter 3 Particle

This document describes the configuration for a large oil blood splatter particle effect in Noita, intended for AI-assisted modding.

## Sprite Configuration

The `Sprite` element defines the visual appearance and animation of the particle.

### Key Attributes:

*   **`filename`**: `data/particles/bloodsplatters/bloodsplatter_large_oil_3.png` - Specifies the texture file used for the sprite.
*   **`offset_x`**: `16` - The horizontal offset of the sprite's origin.
*   **`offset_y`**: `16` - The vertical offset of the sprite's origin.
*   **`default_animation`**: `smoke` - The name of the animation to play by default.

## Animation: `smoke`

The `RectAnimation` element defines the specific animation sequence for the particle.

### Key Attributes:

*   **`name`**: `smoke` - The identifier for this animation.
*   **`frame_count`**: `6` - The total number of frames in the animation.
*   **`frame_width`**: `33` - The width of each individual frame in pixels.
*   **`frame_height`**: `33` - The height of each individual frame in pixels.
*   **`frames_per_row`**: `8` - The number of frames arranged horizontally in the texture.
*   **`frame_wait`**: `0.03` - The duration (in seconds) each frame is displayed before advancing.
*   **`loop`**: `0` - Indicates that the animation does not loop (plays only once).
*   **`pos_x`**: `0` - The starting X coordinate of the animation frames within the texture.
*   **`pos_y`**: `1` - The starting Y coordinate of the animation frames within the texture.
*   **`shrink_by_one_pixel`**: `1` - A flag indicating if frames should shrink by one pixel.

```xml
<Sprite 
  default_animation="smoke" 
  filename="data/particles/bloodsplatters/bloodsplatter_large_oil_3.png" 
  offset_x="16" 
  offset_y="16" >

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

</Sprite>
```