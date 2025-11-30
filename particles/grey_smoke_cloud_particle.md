---
title: Grey Smoke Cloud Particle
category: particles
---

---

# Grey Smoke Cloud Particle

This document describes the configuration for a grey smoke cloud particle effect in Noita, intended for AI-assisted modding.

## Sprite Configuration

The primary sprite for this particle is defined as follows:

```xml
<Sprite
  filename="data/particles/smoke_cloud_grey_4.png"
  offset_x="10"
  offset_y="10"
  default_animation="explosion"
>
  <!-- ... animation definitions ... -->
</Sprite>
```

### Key Attributes:

*   **`filename`**: Specifies the texture file used for the particle.
*   **`offset_x`**, **`offset_y`**: Define the sprite's origin point relative to its center.
*   **`default_animation`**: Sets the animation to play by default when the particle is spawned.

## Animation: `explosion`

The `explosion` animation defines how the smoke cloud visually progresses.

```xml
<RectAnimation
  name="explosion"
  pos_x="0"
  pos_y="0"
  frame_count="8"
  frame_width="20"
  frame_height="20"
  frame_wait="0.09"
  frames_per_row="8"
  loop="0"
>
</RectAnimation>
```

### Key Attributes:

*   **`name`**: The identifier for this animation, referenced by `default_animation`.
*   **`frame_count`**: The total number of frames in the animation sequence.
*   **`frame_width`**, **`frame_height`**: Dimensions of each individual frame within the sprite sheet.
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before transitioning to the next.
*   **`frames_per_row`**: How many frames are arranged horizontally in the sprite sheet.
*   **`loop`**: Determines if the animation should repeat (`1`) or play once (`0`). In this case, it plays once.