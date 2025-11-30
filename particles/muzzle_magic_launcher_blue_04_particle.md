---
title: Muzzle Magic Launcher Blue 04 Particle
category: particles
---

# Muzzle Magic Launcher Blue 04 Particle

This document describes the configuration for a blue muzzle flash particle effect, specifically designed for a magic launcher.

## Sprite Configuration

The `Sprite` element defines the visual appearance and animation of the particle.

### Key Attributes:

*   **filename**: `data/particles/muzzle_flashes/muzzle_magic_launcher_blue_04.png` - Specifies the texture file used for the particle.
*   **offset\_x**: `8` - The horizontal offset of the sprite's origin.
*   **offset\_y**: `7` - The vertical offset of the sprite's origin.
*   **default\_animation**: `"muzzle"` - The name of the default animation to play.

## Animation Configuration

The `RectAnimation` element defines the animation sequence for the sprite.

### Key Attributes:

*   **name**: `"muzzle"` - The identifier for this animation.
*   **pos\_x**: `0` - The starting X position of the animation frame within the sprite sheet.
*   **pos\_y**: `0` - The starting Y position of the animation frame within the sprite sheet.
*   **frame\_count**: `1` - The total number of frames in the animation.
*   **frame\_width**: `16` - The width of each animation frame.
*   **frame\_height**: `16` - The height of each animation frame.
*   **frame\_wait**: `0.1` - The duration (in seconds) each frame is displayed.
*   **frames\_per\_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates whether the animation should loop (0 for no loop, 1 for loop).

```xml
<Sprite
filename="data/particles/muzzle_flashes/muzzle_magic_launcher_blue_04.png"
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