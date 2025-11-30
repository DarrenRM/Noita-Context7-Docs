---
title: Green Poof Explosion Particle
category: particles
---

# Green Poof Explosion Particle

This document describes the configuration for a green poof explosion particle effect in Noita, intended for AI-assisted modding.

## Sprite Configuration

The `Sprite` element defines the visual appearance and animation of the particle.

```xml
<Sprite
filename="data/particles/explosion_040_poof_green.png"
offset_x="20"
offset_y="20"
default_animation="explosion"
>
```

### Key Attributes:

*   **`filename`**: Specifies the texture file used for the particle sprite.
*   **`offset_x`**, **`offset_y`**: Adjusts the sprite's origin point.
*   **`default_animation`**: Sets the initial animation to play when the particle is spawned.

## Animation Definition

The `RectAnimation` element defines the specific animation sequence for the particle.

```xml
<!-- explosion -->
<RectAnimation
name="explosion"
pos_x="0"
pos_y="0"
frame_count="5"
frame_width="40"
frame_height="40"
frame_wait="0.04"
frames_per_row="5"
loop="0"
>
</RectAnimation>
```

### Key Attributes:

*   **`name`**: The identifier for this animation, referenced by the `Sprite` element.
*   **`frame_count`**: The total number of frames in the animation.
*   **`frame_width`**, **`frame_height`**: Dimensions of each individual frame in the sprite sheet.
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before advancing.
*   **`frames_per_row`**: How many frames are arranged horizontally in the sprite sheet.
*   **`loop`**: Determines if the animation should repeat (`1` for loop, `0` for no loop). In this case, it plays once.