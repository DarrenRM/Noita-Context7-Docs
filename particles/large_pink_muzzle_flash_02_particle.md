---
title: Large Pink Muzzle Flash 02 Particle
category: guides
---

<Sprite
filename="data/particles/muzzle_flashes/muzzle_large_pink_02.png"
offset_x="8"
offset_y="7"
default_animation="muzzle"
>
  <RectAnimation
    name="muzzle"
    pos_x="0"
    pos_y="0"
    frame_count="1"
    frame_width="16"
    frame_height="16"
    frame_wait="0.1"
    frames_per_row="1"
    loop="0"
  >
  </RectAnimation>
</Sprite>
```

---
title: Large Pink Muzzle Flash 02 Particle
category: particles
---

# Large Pink Muzzle Flash 02 Particle

This document describes the configuration for a specific muzzle flash particle effect in Noita, designed for AI-assisted modding.

## Sprite Configuration

The primary visual component of this particle is defined by the `<Sprite>` tag.

### Key Attributes:

*   **`filename`**: Specifies the image file used for the particle's texture.
    *   `data/particles/muzzle_flashes/muzzle_large_pink_02.png`
*   **`offset_x`**: The horizontal offset of the sprite's origin.
    *   `8`
*   **`offset_y`**: The vertical offset of the sprite's origin.
    *   `7`
*   **`default_animation`**: The name of the animation to use by default.
    *   `muzzle`

## Animation Details

The `<RectAnimation>` tag defines how the sprite is animated.

### Key Attributes:

*   **`name`**: The identifier for this animation.
    *   `muzzle`
*   **`frame_count`**: The total number of frames in the animation.
    *   `1` (This indicates a single-frame animation, essentially a static image for this effect).
*   **`frame_width`**: The width of each animation frame.
    *   `16`
*   **`frame_height`**: The height of each animation frame.
    *   `16`
*   **`frame_wait`**: The duration (in seconds) each frame is displayed.
    *   `0.1`
*   **`frames_per_row`**: The number of frames arranged horizontally in the sprite sheet.
    *   `1`
*   **`loop`**: Determines if the animation should loop.
    *   `0` (Indicates the animation does not loop, playing only once).