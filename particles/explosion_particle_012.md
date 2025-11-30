---
title: Explosion Particle 012
category: guides
---

<Sprite 
  default_animation="explosion" 
  filename="data/particles/explosion_012.png" 
  offset_x="6" 
  offset_y="6" >

  <RectAnimation 
    frame_count="9" 
    frame_height="13" 
    frame_wait="0.021" 
    frame_width="13" 
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
title: Explosion Particle 012
category: particles
---

# Explosion Particle 012

This document describes the configuration for a specific explosion particle effect in Noita, identified as `explosion_012`. This particle is designed to be a visual effect, likely triggered by in-game events.

## Sprite Configuration

The primary visual representation of this particle is defined by the `<Sprite>` tag.

### Key Attributes:

*   **`default_animation`**: Specifies the name of the default animation to be played. Here, it's set to `"explosion"`.
*   **`filename`**: The path to the image file containing the sprite frames for this particle. In this case, it's `"data/particles/explosion_012.png"`.
*   **`offset_x`**: Horizontal offset for the sprite. Value: `"6"`.
*   **`offset_y`**: Vertical offset for the sprite. Value: `"6"`.

## RectAnimation Configuration

The `<RectAnimation>` tag defines how the sprite frames are arranged and animated.

### Key Attributes:

*   **`name`**: The name of this animation, which must match the `default_animation` in the `<Sprite>` tag. Here, it's `"explosion"`.
*   **`frame_count`**: The total number of frames in the animation. Value: `"9"`.
*   **`frame_width`**: The width of each individual frame. Value: `"13"`.
*   **`frame_height`**: The height of each individual frame. Value: `"13"`.
*   **`frames_per_row`**: How many frames are arranged horizontally in the sprite sheet. Value: `"8"`.
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before transitioning to the next. Value: `"0.021"`.
*   **`loop`**: Determines if the animation should loop. `"0"` indicates no looping (it plays once).
*   **`pos_x`**: The starting X position of the animation frames within the sprite sheet. Value: `"0"`.
*   **`pos_y`**: The starting Y position of the animation frames within the sprite sheet. Value: `"1"`.
*   **`shrink_by_one_pixel`**: A boolean-like attribute indicating if frames should shrink by one pixel. Value: `"1"` (true).

This configuration suggests a small, quick explosion animation composed of 9 frames, each 13x13 pixels, extracted from a sprite sheet. The animation plays once and has a very short frame duration.