---
title: Gunpowder Smoke Particle (03)
category: guides
---

<Sprite 
  default_animation="explosion" 
  filename="data/particles/smoke_gunpowder_03.png" 
  offset_x="10" 
  offset_y="10"
  rect_animation="explosion">

  <RectAnimation 
    frame_count="12" 
    frame_wait="0.06" 
    frame_height="20" 
    frame_width="20" 
    frames_per_row="12" 
    loop="0" 
    name="explosion" 
    pos_x="0" 
    pos_y="0" >

  </RectAnimation>

</Sprite>
```

---
title: Gunpowder Smoke Particle (03)
category: particles
---

# Gunpowder Smoke Particle (03)

This document describes the configuration for a specific gunpowder smoke particle effect in Noita, identified as `smoke_gunpowder_03`. This particle is likely used to visually represent the aftermath of gunpowder explosions.

## Sprite Configuration

The primary visual representation of this particle is defined by the `<Sprite>` element.

### Key Attributes:

*   **`default_animation`**: Specifies the default animation to play when the sprite is active. Here, it's set to `"explosion"`.
*   **`filename`**: The path to the image file containing the sprite's frames. In this case, it's `"data/particles/smoke_gunpowder_03.png"`.
*   **`offset_x`**: The horizontal offset of the sprite's origin. Set to `10`.
*   **`offset_y`**: The vertical offset of the sprite's origin. Set to `10`.
*   **`rect_animation`**: Links the sprite to a specific rectangular animation definition. It's set to `"explosion"`, matching the `default_animation`.

## Rectangular Animation Definition

The `<RectAnimation>` element details how the sprite frames are arranged and animated.

### Key Attributes:

*   **`name`**: The identifier for this animation, which is `"explosion"`. This name is referenced by the `<Sprite>` element.
*   **`frame_count`**: The total number of frames in the animation. Set to `12`.
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before advancing to the next. Set to `0.06`.
*   **`frame_height`**: The height of each individual frame in pixels. Set to `20`.
*   **`frame_width`**: The width of each individual frame in pixels. Set to `20`.
*   **`frames_per_row`**: The number of frames arranged horizontally within the sprite sheet. Set to `12`.
*   **`loop`**: Determines if the animation should loop. `0` indicates that the animation does not loop (it plays once).
*   **`pos_x`**: The starting X-coordinate of the animation frames within the sprite sheet. Set to `0`.
*   **`pos_y`**: The starting Y-coordinate of the animation frames within the sprite sheet. Set to `0`.