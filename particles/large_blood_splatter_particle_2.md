---
title: Large Blood Splatter Particle 2
category: guides
---

<Sprite 
  default_animation="smoke" 
  filename="data/particles/bloodsplatters/bloodsplatter_large_2.png" 
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

---
title: Large Blood Splatter Particle 2
category: particles
---

# Large Blood Splatter Particle 2

This document describes the configuration for a large blood splatter particle effect in Noita, specifically `bloodsplatter_large_2.xml`. This particle is used to visually represent blood splatters in the game.

## Sprite Configuration

The primary configuration for the visual appearance of the particle is handled by the `<Sprite>` tag.

### Key Attributes:

*   **`default_animation`**: Specifies the name of the default animation to be used for this sprite. In this case, it's set to `"smoke"`.
*   **`filename`**: The path to the image file containing the sprite's frames. Here, it's `"data/particles/bloodsplatters/bloodsplatter_large_2.png"`.
*   **`offset_x`**: The horizontal offset of the sprite's origin. Set to `16`.
*   **`offset_y`**: The vertical offset of the sprite's origin. Set to `16`.

## RectAnimation Configuration

The `<RectAnimation>` tag defines how the sprite frames are arranged and animated.

### Key Attributes:

*   **`name`**: The name of this specific animation, which is referenced by `default_animation` in the `<Sprite>` tag. Here, it's `"smoke"`.
*   **`frame_count`**: The total number of frames in the animation. Set to `6`.
*   **`frame_width`**: The width of each individual frame in pixels. Set to `33`.
*   **`frame_height`**: The height of each individual frame in pixels. Set to `33`.
*   **`frames_per_row`**: The number of frames that fit horizontally in a single row of the sprite sheet. Set to `8`.
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before transitioning to the next. Set to `0.03`.
*   **`loop`**: Determines if the animation should loop. `0` indicates that it will not loop (play once).
*   **`pos_x`**: The starting X-coordinate of the animation frames on the sprite sheet. Set to `0`.
*   **`pos_y`**: The starting Y-coordinate of the animation frames on the sprite sheet. Set to `1`.
*   **`shrink_by_one_pixel`**: A flag indicating if each frame should shrink by one pixel after each animation cycle. Set to `1` (true).