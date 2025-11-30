---
title: Explosion Particle 008
category: guides
---

<Sprite 
  default_animation="explosion" 
  filename="data/particles/explosion_008.png" 
  offset_x="4" 
  offset_y="4" >

  <RectAnimation 
    frame_count="9" 
    frame_height="9" 
    frame_wait="0.01" 
    frame_width="9" 
    frames_per_row="8" 
    loop="0" 
    name="explosion" 
    pos_x="0" 
    pos_y="1" 
    shrink_by_one_pixel="1" >

  </RectAnimation>

</Sprite>
```

---
title: Explosion Particle 008
category: particles
---

# Explosion Particle 008

This documentation describes the `explosion_008.xml` particle file, which defines a specific visual effect for explosions in Noita.

## Sprite Definition

The primary visual component is defined by the `<Sprite>` tag.

### Key Attributes:

*   **`default_animation`**: Specifies the name of the default animation to play. Here, it's set to `"explosion"`.
*   **`filename`**: The path to the sprite sheet image used for this particle.
    *   `data/particles/explosion_008.png`
*   **`offset_x`**: Horizontal offset for the sprite.
    *   `4`
*   **`offset_y`**: Vertical offset for the sprite.
    *   `4`

## RectAnimation Definition

The `<RectAnimation>` tag details how the sprite sheet is used to create an animation.

### Key Attributes:

*   **`name`**: The name of this specific animation.
    *   `"explosion"`
*   **`frame_count`**: The total number of frames in the animation.
    *   `9`
*   **`frame_width`**: The width of each individual frame in pixels.
    *   `9`
*   **`frame_height`**: The height of each individual frame in pixels.
    *   `9`
*   **`frames_per_row`**: How many frames are arranged horizontally on the sprite sheet.
    *   `8`
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before advancing to the next.
    *   `0.01`
*   **`loop`**: Determines if the animation should loop. `0` indicates no looping (plays once).
    *   `0`
*   **`pos_x`**: The starting X position of the animation frames on the sprite sheet.
    *   `0`
*   **`pos_y`**: The starting Y position of the animation frames on the sprite sheet.
    *   `1`
*   **`shrink_by_one_pixel`**: A flag that affects how the sprite is rendered, potentially by shrinking it by one pixel.
    *   `1`