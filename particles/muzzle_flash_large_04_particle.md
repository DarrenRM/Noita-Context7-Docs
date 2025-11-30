---
title: Muzzle Flash Large 04 Particle
category: particles
---

# Muzzle Flash Large 04 Particle

This document describes the configuration for a large muzzle flash particle effect in Noita, designed for AI-assisted modding.

## Sprite Configuration

The `Sprite` element defines the visual appearance and animation of the particle.

### Key Attributes:

*   **filename**: `data/particles/muzzle_flashes/muzzle_large_04.png` - Specifies the texture file used for the particle.
*   **offset_x**: `8` - Horizontal offset for the sprite's origin.
*   **offset_y**: `7` - Vertical offset for the sprite's origin.
*   **default_animation**: `muzzle` - The name of the animation to play by default.

## Animation Configuration

The `RectAnimation` element defines the animation sequence for the sprite.

### Key Attributes:

*   **name**: `muzzle` - The identifier for this animation.
*   **pos_x**: `0` - Starting X position within the sprite sheet for the animation.
*   **pos_y**: `0` - Starting Y position within the sprite sheet for the animation.
*   **frame_count**: `1` - The total number of frames in the animation.
*   **frame_width**: `16` - The width of each individual frame.
*   **frame_height**: `16` - The height of each individual frame.
*   **frame_wait**: `0.1` - The duration (in seconds) each frame is displayed before advancing.
*   **frames_per_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates whether the animation should loop (0 for no loop, 1 for loop).

```xml
<Sprite
filename="data/particles/muzzle_flashes/muzzle_large_04.png"
offset_x="8"
offset_y="7"
default_animation="muzzle"
 >

<!-- explosion -->
<RectAnimation
name="muzzle"
pos_x="0"
pos_y="0"
frame_count="1"
frame_width="16"
frame_height="16"
frame_wait="0.1"
frames_per_row="1"
loop="0"   >
</RectAnimation>
</Sprite>
```