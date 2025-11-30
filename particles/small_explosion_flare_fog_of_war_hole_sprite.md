---
title: Small Explosion Flare Fog of War Hole Sprite
category: guides
---

<Sprite 
  default_animation="explosion" 
  filename="data/particles/explosion_flare_fog_of_war_hole_small.png" 
  offset_x="8" 
  offset_y="8" >

  <RectAnimation 
    frame_count="3" 
    frame_height="17" 
    frame_wait="0.02" 
    frame_width="17" 
    frames_per_row="3" 
    loop="0" 
    name="explosion" 
    pos_x="0" 
    pos_y="1" 
    shrink_by_one_pixel="1" >

  </RectAnimation>

</Sprite>
```

---
title: Small Explosion Flare Fog of War Hole Sprite
category: particles
---

# Small Explosion Flare Fog of War Hole Sprite

This document describes the sprite definition for a small explosion flare that creates a hole in the fog of war.

## Sprite Definition

The `<Sprite>` element defines the visual appearance and animation of the particle.

### Key Attributes:

*   **`default_animation`**: Specifies the name of the default animation to play. In this case, it's `"explosion"`.
*   **`filename`**: The path to the sprite sheet image file.
    *   `data/particles/explosion_flare_fog_of_war_hole_small.png`
*   **`offset_x`**: The horizontal offset of the sprite's origin.
    *   `8`
*   **`offset_y`**: The vertical offset of the sprite's origin.
    *   `8`

## RectAnimation Definition

The `<RectAnimation>` element defines a specific animation sequence using a rectangular grid of frames within the sprite sheet.

### Key Attributes:

*   **`name`**: The name of this animation sequence.
    *   `"explosion"`
*   **`frame_count`**: The total number of frames in this animation.
    *   `3`
*   **`frame_width`**: The width of each individual frame.
    *   `17`
*   **`frame_height`**: The height of each individual frame.
    *   `17`
*   **`frames_per_row`**: The number of frames arranged horizontally in the sprite sheet.
    *   `3`
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before advancing to the next.
    *   `0.02`
*   **`loop`**: Determines if the animation should loop. `0` indicates no looping (plays once).
    *   `0`
*   **`pos_x`**: The starting X position of the animation frames within the sprite sheet.
    *   `0`
*   **`pos_y`**: The starting Y position of the animation frames within the sprite sheet.
    *   `1`
*   **`shrink_by_one_pixel`**: A flag indicating if each frame should shrink by one pixel.
    *   `1` (True)