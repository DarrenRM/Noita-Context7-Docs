---
title: Muzzle Magic Launcher Large 05 Particle
category: particles
---

# Muzzle Magic Launcher Large 05 Particle

This documentation describes the `muzzle_magic_launcher_large_05.xml` particle effect, used for muzzle flashes in Noita.

## Sprite

The primary visual component of the particle.

```xml
<Sprite
filename="data/particles/muzzle_flashes/muzzle_magic_launcher_large_05.png"
offset_x="8"
offset_y="7"
default_animation="muzzle"
>
```

*   **filename**: Specifies the texture file for the sprite.
*   **offset\_x**, **offset\_y**: Adjusts the sprite's position relative to its origin.
*   **default\_animation**: The name of the animation to play by default.

### Animation: `muzzle`

Defines the animation sequence for the sprite.

```xml
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
```

*   **name**: The identifier for this animation.
*   **frame\_count**: The total number of frames in the animation.
*   **frame\_width**, **frame\_height**: Dimensions of each individual frame.
*   **frame\_wait**: The duration (in seconds) each frame is displayed.
*   **frames\_per\_row**: How many frames are arranged horizontally in the sprite sheet.
*   **loop**: Determines if the animation should loop (0 for no loop, 1 for loop).