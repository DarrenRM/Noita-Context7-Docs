---
title: Muzzle Launcher 05 Particle Effect
category: guides
---

<Sprite
filename="data/particles/muzzle_flashes/muzzle_launcher_05.png"
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
title: Muzzle Launcher 05 Particle Effect
category: particles
---

# Muzzle Launcher 05 Particle Effect

This document describes the `muzzle_launcher_05.xml` particle effect, used for muzzle flashes in Noita.

## Sprite

The primary visual component of the particle effect.

### Key Attributes:

*   **filename**: `data/particles/muzzle_flashes/muzzle_launcher_05.png` - The image file used for the sprite.
*   **offset\_x**: `8` - Horizontal offset of the sprite.
*   **offset\_y**: `7` - Vertical offset of the sprite.
*   **default\_animation**: `muzzle` - The name of the animation to play by default.

## RectAnimation

Defines the animation sequence for the sprite.

### Key Attributes:

*   **name**: `muzzle` - The identifier for this animation.
*   **frame\_count**: `1` - The total number of frames in the animation.
*   **frame\_width**: `16` - The width of each individual frame.
*   **frame\_height**: `16` - The height of each individual frame.
*   **frame\_wait**: `0.1` - The duration (in seconds) each frame is displayed.
*   **frames\_per\_row**: `1` - The number of frames arranged horizontally in the sprite sheet.
*   **loop**: `0` - Indicates if the animation should loop (0 for no loop, 1 for loop).