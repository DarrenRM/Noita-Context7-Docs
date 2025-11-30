---
title: Rocket Roll Projectile Graphics
category: projectiles_gfx
---

---

# Rocket Roll Projectile Graphics

This document describes the graphical assets for the "rocket_roll" projectile in Noita, intended for AI-assisted modding.

## Sprite Definition

The primary sprite definition for the rocket roll projectile.

### Key Attributes:

*   **default\_animation**: Specifies the default animation to play. Here, it's "fireball".
*   **filename**: The path to the sprite sheet image file.
*   **offset\_x**: Horizontal offset for the sprite.
*   **offset\_y**: Vertical offset for the sprite.

```xml
<Sprite
  default_animation="fireball"
  filename="data/projectiles_gfx/rocket_roll.png"
  offset_x="7.5"
  offset_y="7.5" >
  <!-- ... animations ... -->
</Sprite>
```

## RectAnimation: "fireball"

Defines the rectangular animation sequence for the "fireball" animation.

### Key Attributes:

*   **name**: The name of this animation, referenced by `default_animation`.
*   **frame\_count**: The total number of frames in the animation.
*   **frame\_height**: The height of each individual frame.
*   **frame\_wait**: The duration (in seconds) each frame is displayed before advancing.
*   **frame\_width**: The width of each individual frame.
*   **frames\_per\_row**: The number of frames arranged horizontally in the sprite sheet.
*   **pos\_x**: The starting X position of the animation frames within the sprite sheet.
*   **pos\_y**: The starting Y position of the animation frames within the sprite sheet.

```xml
<RectAnimation
  frame_count="9"
  frame_height="15"
  frame_wait="0.04"
  frame_width="15"
  frames_per_row="9"
  name="fireball"
  pos_x="0"
  pos_y="0" >
</RectAnimation>
```