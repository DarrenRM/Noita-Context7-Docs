---
title: Ghost Sprite Animation
category: guides
---

<Sprite 
  default_animation="stand" 
  filename="data/enemies_gfx/ghost.png" 
  offset_x="20" 
  offset_y="20"
>

  <RectAnimation 
    frame_count="8" 
    frame_height="41" 
    frame_wait="0.16" 
    frame_width="41" 
    frames_per_row="8" 
    name="stand" 
    pos_x="0" 
    pos_y="1" 
    shrink_by_one_pixel="1" >

  </RectAnimation>

</Sprite>
```

---
title: Ghost Sprite Animation
category: enemies_gfx
---

# Ghost Sprite Animation

This document details the sprite and animation data for the "ghost" enemy in Noita, intended for AI-assisted modding.

## Sprite Definition

The primary sprite for the ghost is defined by the `<Sprite>` tag.

### Key Attributes:

*   **`default_animation`**: Specifies the animation to play by default.
    *   Value: `"stand"`
*   **`filename`**: The path to the sprite image file.
    *   Value: `"data/enemies_gfx/ghost.png"`
*   **`offset_x`**: Horizontal offset for the sprite.
    *   Value: `"20"`
*   **`offset_y`**: Vertical offset for the sprite.
    *   Value: `"20"`

## Animation: "stand"

The ghost has a primary animation named "stand", defined by the `<RectAnimation>` tag. This animation dictates how the sprite sheet is used to create movement.

### Key Attributes:

*   **`name`**: The name of the animation.
    *   Value: `"stand"`
*   **`frame_count`**: The total number of frames in the animation.
    *   Value: `"8"`
*   **`frame_width`**: The width of each individual frame.
    *   Value: `"41"`
*   **`frame_height`**: The height of each individual frame.
    *   Value: `"41"`
*   **`frames_per_row`**: How many frames are present in a single row of the sprite sheet.
    *   Value: `"8"`
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before transitioning to the next.
    *   Value: `"0.16"`
*   **`pos_x`**: The starting X position of the animation frames within the sprite sheet.
    *   Value: `"0"`
*   **`pos_y`**: The starting Y position of the animation frames within the sprite sheet.
    *   Value: `"1"`
*   **`shrink_by_one_pixel`**: A flag indicating if frames should be shrunk by one pixel.
    *   Value: `"1"` (True)