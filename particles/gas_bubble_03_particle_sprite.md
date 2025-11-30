---
title: Gas Bubble 03 Particle Sprite
category: guides
---

<Sprite 
  default_animation="bubble" 
  filename="data/particles/gas_bubble_03.png" 
  offset_x="0.5" 
  offset_y="0.5" >

  <RectAnimation 
    frame_count="1" 
    frame_height="2" 
    frame_wait="0.25" 
    frame_width="2" 
    frames_per_row="1" 
    name="bubble" 
    pos_x="0" 
    pos_y="1" 
    shrink_by_one_pixel="1" >

  </RectAnimation>

</Sprite>
```

---
title: Gas Bubble 03 Particle Sprite
category: particles
---

# Gas Bubble 03 Particle Sprite

This document describes the sprite definition for the "gas_bubble_03" particle in Noita.

## Sprite Definition

The primary sprite element defines the visual appearance and animation of the particle.

### Key Attributes:

*   **`default_animation`**: Specifies the name of the default animation to use, which is "bubble" in this case.
*   **`filename`**: The path to the image file containing the particle's sprite sheet.
    *   `data/particles/gas_bubble_03.png`
*   **`offset_x`**: The horizontal offset of the sprite's origin.
    *   `0.5` (center)
*   **`offset_y`**: The vertical offset of the sprite's origin.
    *   `0.5` (center)

## RectAnimation: "bubble"

This defines the specific animation sequence for the "bubble" state.

### Key Attributes:

*   **`name`**: The name of this animation, "bubble".
*   **`frame_count`**: The total number of frames in the animation.
    *   `1` (This indicates a static sprite or a single-frame animation).
*   **`frame_width`**: The width of each individual frame in pixels.
    *   `2`
*   **`frame_height`**: The height of each individual frame in pixels.
    *   `2`
*   **`frames_per_row`**: The number of frames arranged horizontally in the sprite sheet.
    *   `1`
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before advancing.
    *   `0.25`
*   **`pos_x`**: The starting X coordinate of the animation frames within the sprite sheet.
    *   `0`
*   **`pos_y`**: The starting Y coordinate of the animation frames within the sprite sheet.
    *   `1`
*   **`shrink_by_one_pixel`**: A flag indicating if the sprite should shrink by one pixel.
    *   `1` (True)