---
title: Puff 03 Particle Sprite
category: particles
---

---

# Puff 03 Particle Sprite

This document describes the sprite configuration for the "puff_03" particle effect in Noita.

## Sprite Configuration

The primary sprite element defines the visual appearance and animation of the particle.

```xml
<Sprite 
  default_animation="explosion" 
  filename="data/particles/puff_03.png" 
  offset_x="3" 
  offset_y="3" >
  
  <!-- Animation details are nested within -->

</Sprite>
```

### Key Sprite Attributes:

*   **`default_animation`**: Specifies the name of the animation to be used by default. Here, it's set to "explosion".
*   **`filename`**: The path to the image file containing the particle's spritesheet.
*   **`offset_x`**, **`offset_y`**: Adjusts the horizontal and vertical positioning of the sprite.

## Animation Details: Explosion

The `RectAnimation` element defines the specific frames and timing for the "explosion" animation.

```xml
<RectAnimation 
  frame_count="3" 
  frame_height="7" 
  frame_wait="0.19" 
  frame_width="7" 
  frames_per_row="3" 
  loop="0" 
  name="explosion" 
  pos_x="0" 
  pos_y="1" 
  shrink_by_one_pixel="1" >
</RectAnimation>
```

### Key Animation Attributes:

*   **`name`**: The identifier for this animation, matching the `default_animation` in the `Sprite` tag.
*   **`frame_count`**: The total number of frames in the animation.
*   **`frame_width`**, **`frame_height`**: Dimensions of each individual frame in pixels.
*   **`frames_per_row`**: How many frames are arranged horizontally in the spritesheet.
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before transitioning to the next.
*   **`loop`**: Determines if the animation should loop (`1`) or play once (`0`). Here, it plays once.
*   **`pos_x`**, **`pos_y`**: The starting position of the animation frames within the spritesheet (in terms of frame grid).
*   **`shrink_by_one_pixel`**: If set to `1`, the sprite will shrink by one pixel each frame, creating a fading/shrinking effect.