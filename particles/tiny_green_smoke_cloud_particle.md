---
title: Tiny Green Smoke Cloud Particle
category: guides
---

<Sprite
filename="data/particles/smoke_cloud_tiny_green_2.png"
offset_x="10"
offset_y="10"
default_animation="explosion"
>

<!-- explosion -->
<RectAnimation
name="explosion"
pos_x="0"
pos_y="0"
frame_count="6"
frame_width="20"
frame_height="20"
frame_wait="0.06"
frames_per_row="6"
loop="0"
>
</RectAnimation>
</Sprite>
```

---
title: Tiny Green Smoke Cloud Particle
category: particles
---

# Tiny Green Smoke Cloud Particle

This document describes the configuration for a small, green smoke cloud particle effect in Noita, intended for AI-assisted modding.

## Sprite Configuration

The particle uses a sprite sheet to define its visual appearance.

### Key Attributes:

*   **`filename`**: `data/particles/smoke_cloud_tiny_green_2.png` - Specifies the image file containing the particle's animation frames.
*   **`offset_x`**: `10` - Horizontal offset for the sprite.
*   **`offset_y`**: `10` - Vertical offset for the sprite.
*   **`default_animation`**: `explosion` - The name of the animation to play by default when the particle is spawned.

## Animation Details: `explosion`

This section details the `explosion` animation used by the particle.

### Key Attributes:

*   **`name`**: `explosion` - The identifier for this animation.
*   **`frame_count`**: `6` - The total number of frames in the animation.
*   **`frame_width`**: `20` - The width of each individual frame in pixels.
*   **`frame_height`**: `20` - The height of each individual frame in pixels.
*   **`frame_wait`**: `0.06` - The duration (in seconds) each frame is displayed before advancing to the next.
*   **`frames_per_row`**: `6` - The number of frames arranged horizontally in the sprite sheet.
*   **`loop`**: `0` - Indicates that the animation does not loop (it plays once and stops).