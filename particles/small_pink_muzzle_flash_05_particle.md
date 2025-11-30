---
title: Small Pink Muzzle Flash 05 Particle
category: guides
---

<Sprite
filename="data/particles/muzzle_flashes/muzzle_small_pink_05.png"
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
title: Small Pink Muzzle Flash 05 Particle
category: particles
---

# Small Pink Muzzle Flash 05 Particle

This document describes the configuration for a small pink muzzle flash particle effect in Noita, intended for AI-assisted modding.

## Sprite Configuration

The primary sprite for this particle is defined by the `<Sprite>` tag.

### Key Attributes:

*   **`filename`**: `data/particles/muzzle_flashes/muzzle_small_pink_05.png`
    *   Specifies the image file used for the particle's visual representation.
*   **`offset_x`**: `8`
    *   Horizontal offset for the sprite's origin.
*   **`offset_y`**: `7`
    *   Vertical offset for the sprite's origin.
*   **`default_animation`**: `muzzle`
    *   The name of the animation to be used by default for this sprite.

## Animation Details

The `<RectAnimation>` tag defines how the sprite is animated.

### Key Attributes:

*   **`name`**: `muzzle`
    *   The identifier for this specific animation. This links to the `default_animation` attribute in the `<Sprite>` tag.
*   **`frame_count`**: `1`
    *   The total number of frames in the animation. In this case, it's a single frame.
*   **`frame_width`**: `16`
    *   The width of each individual frame in pixels.
*   **`frame_height`**: `16`
    *   The height of each individual frame in pixels.
*   **`frame_wait`**: `0.1`
    *   The duration (in seconds) each frame is displayed before advancing.
*   **`frames_per_row`**: `1`
    *   The number of frames arranged horizontally within the sprite sheet.
*   **`loop`**: `0`
    *   Indicates whether the animation should loop. `0` means it will not loop (play once).