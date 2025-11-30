---
title: Puff 01 Particle Sprite
category: guides
---

<Sprite 
  default_animation="explosion" 
  filename="data/particles/puff_01.png" 
  offset_x="3" 
  offset_y="3" >

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

</Sprite>
```

---
title: Puff 01 Particle Sprite
category: particles
---

# Puff 01 Particle Sprite

This document describes the sprite definition for `puff_01.xml`, a particle effect in Noita. It details the visual appearance and animation of this specific puff effect.

## Sprite Definition

The primary `<Sprite>` element defines the visual asset for the particle.

### Key Attributes:

*   **`default_animation`**: Specifies the name of the animation to be used by default. Here, it's set to `"explosion"`.
*   **`filename`**: The path to the image file containing the sprite frames. In this case, it's `"data/particles/puff_01.png"`.
*   **`offset_x`**: Horizontal offset for the sprite. Value: `"3"`.
*   **`offset_y`**: Vertical offset for the sprite. Value: `"3"`.

## Animation: `explosion`

The `<RectAnimation>` element defines how the sprite frames are arranged and played.

### Key Attributes:

*   **`name`**: The identifier for this animation, matching the `default_animation` attribute of the `<Sprite>` tag. Value: `"explosion"`.
*   **`frame_count`**: The total number of frames in the animation. Value: `"3"`.
*   **`frame_width`**: The width of each individual frame in pixels. Value: `"7"`.
*   **`frame_height`**: The height of each individual frame in pixels. Value: `"7"`.
*   **`frames_per_row`**: How many frames are arranged horizontally in the sprite sheet. Value: `"3"`.
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before transitioning to the next. Value: `"0.19"`.
*   **`loop`**: Determines if the animation should loop. `"0"` indicates no looping (it plays once).
*   **`pos_x`**: The starting X position of the animation frames within the sprite sheet. Value: `"0"`.
*   **`pos_y`**: The starting Y position of the animation frames within the sprite sheet. Value: `"1"`.
*   **`shrink_by_one_pixel`**: A flag indicating if each frame should shrink by one pixel per animation cycle. Value: `"1"` (true).