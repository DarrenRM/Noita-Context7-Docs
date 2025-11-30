---
title: Explosion Particle Sprite
category: particles
---

# Explosion Particle Sprite

This document describes the sprite and animation data for a 128x128 pixel explosion particle effect in Noita.

## Sprite Data

The `<Sprite>` element defines the visual appearance and positioning of the particle.

### Key Attributes:

*   **`default_animation`**: Specifies the name of the animation to use by default. In this case, it's "explosion".
*   **`filename`**: The path to the sprite sheet containing the animation frames.
*   **`offset_x`**: The horizontal offset of the sprite's origin.
*   **`offset_y`**: The vertical offset of the sprite's origin.

```xml
<Sprite 
  default_animation="explosion" 
  filename="data/particles/explosion_128.png" 
  offset_x="64" 
  offset_y="64" >
  </Sprite>
```

## Animation Data

The `<RectAnimation>` element defines the specific frames and timing for the "explosion" animation.

### Key Attributes:

*   **`name`**: The name of this animation, matching `default_animation` in the `<Sprite>` tag.
*   **`frame_count`**: The total number of frames in the animation.
*   **`frame_width`**: The width of each individual frame.
*   **`frame_height`**: The height of each individual frame.
*   **`frames_per_row`**: How many frames are arranged horizontally in the sprite sheet.
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before advancing.
*   **`loop`**: Whether the animation should loop (0 for no, 1 for yes).
*   **`pos_x`**: The starting X position of the animation frames within the sprite sheet.
*   **`pos_y`**: The starting Y position of the animation frames within the sprite sheet.
*   **`shrink_by_one_pixel`**: A flag to indicate if frames should shrink by one pixel each subsequent frame (useful for fading effects).

```xml
<RectAnimation 
  frame_count="5" 
  frame_height="129" 
  frame_wait="0.03" 
  frame_width="129" 
  frames_per_row="5" 
  loop="0" 
  name="explosion" 
  pos_x="0" 
  pos_y="1" 
  shrink_by_one_pixel="1" >
</RectAnimation>
```