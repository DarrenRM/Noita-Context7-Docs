---
title: Creepy Particle Sprite
category: guides
---

<Sprite 
  default_animation="explosion" 
  filename="data/particles/creepy.png" 
  offset_x="8" 
  offset_y="8" >

  <RectAnimation 
    frame_count="4" 
    frame_height="17" 
    frame_wait="0.12" 
    frame_width="17" 
    frames_per_row="4" 
    loop="0" 
    name="explosion" 
    pos_x="0" 
    pos_y="1" 
    shrink_by_one_pixel="1" >

  </RectAnimation>

</Sprite>
```

---
title: Creepy Particle Sprite
category: particles
---

# Creepy Particle Sprite

This document describes the sprite definition for the "creepy" particle in Noita. It details the visual appearance and animation of this particle.

## Sprite Definition

The primary sprite element defines the visual asset and its default animation.

### Key Attributes:

*   **`default_animation`**: Specifies the name of the animation to be used by default.
    *   Value: `"explosion"`
*   **`filename`**: The path to the image file containing the sprite frames.
    *   Value: `"data/particles/creepy.png"`
*   **`offset_x`**: Horizontal offset for the sprite's origin.
    *   Value: `"8"`
*   **`offset_y`**: Vertical offset for the sprite's origin.
    *   Value: `"8"`

## RectAnimation: "explosion"

This section defines a rectangular animation sequence for the sprite.

### Key Attributes:

*   **`name`**: The name of this specific animation.
    *   Value: `"explosion"`
*   **`frame_count`**: The total number of frames in the animation.
    *   Value: `"4"`
*   **`frame_height`**: The height of each individual frame in pixels.
    *   Value: `"17"`
*   **`frame_width`**: The width of each individual frame in pixels.
    *   Value: `"17"`
*   **`frames_per_row`**: How many frames are arranged horizontally in the source image.
    *   Value: `"4"`
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before advancing.
    *   Value: `"0.12"`
*   **`loop`**: Determines if the animation should loop. `0` indicates no looping.
    *   Value: `"0"`
*   **`pos_x`**: The starting X-coordinate of the animation frames within the sprite sheet.
    *   Value: `"0"`
*   **`pos_y`**: The starting Y-coordinate of the animation frames within the sprite sheet.
    *   Value: `"1"`
*   **`shrink_by_one_pixel`**: A flag indicating if frames should shrink by one pixel each step. `1` means true.
    *   Value: `"1"`