---
title: Gas Bubble 02 Particle Sprite
category: guides
---

<Sprite 
  default_animation="bubble" 
  filename="data/particles/gas_bubble_02.png" 
  offset_x="1" 
  offset_y="1" >

  <RectAnimation 
    frame_count="2" 
    frame_height="3" 
    frame_wait="0.27" 
    frame_width="3" 
    frames_per_row="2" 
    loop="0" 
    name="bubble" 
    pos_x="0" 
    pos_y="1" 
    shrink_by_one_pixel="1" >

  </RectAnimation>

</Sprite>
```

---
title: Gas Bubble 02 Particle Sprite
category: particles
---

# Gas Bubble 02 Particle Sprite

This document describes the sprite definition for the "gas_bubble_02" particle in Noita. It details the visual appearance and animation of this particle.

## Sprite Definition

The primary sprite element defines the visual asset and its default animation.

### Key Attributes:

*   **`default_animation`**: Specifies the name of the animation to be used by default.
    *   Value: `"bubble"`
*   **`filename`**: The path to the image file containing the sprite frames.
    *   Value: `"data/particles/gas_bubble_02.png"`
*   **`offset_x`**: Horizontal offset for the sprite.
    *   Value: `"1"`
*   **`offset_y`**: Vertical offset for the sprite.
    *   Value: `"1"`

## Animation: `bubble`

This section details the `RectAnimation` element, which defines how the sprite frames are arranged and animated.

### Key Attributes:

*   **`name`**: The identifier for this specific animation.
    *   Value: `"bubble"`
*   **`frame_count`**: The total number of frames in the animation.
    *   Value: `"2"`
*   **`frame_width`**: The width of each individual frame in pixels.
    *   Value: `"3"`
*   **`frame_height`**: The height of each individual frame in pixels.
    *   Value: `"3"`
*   **`frames_per_row`**: How many frames are arranged horizontally in the sprite sheet.
    *   Value: `"2"`
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before advancing.
    *   Value: `"0.27"`
*   **`loop`**: Determines if the animation should loop. `0` indicates no looping.
    *   Value: `"0"`
*   **`pos_x`**: The starting X position of the animation frames within the sprite sheet.
    *   Value: `"0"`
*   **`pos_y`**: The starting Y position of the animation frames within the sprite sheet.
    *   Value: `"1"`
*   **`shrink_by_one_pixel`**: A flag indicating if frames should shrink by one pixel.
    *   Value: `"1"`