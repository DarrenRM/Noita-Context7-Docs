---
title: Grenade Projectile Sprite
category: projectiles_gfx
---

---

# Grenade Projectile Sprite

This document describes the sprite and animation data for the "grenade" projectile in Noita.

## Sprite Definition

The primary sprite definition for the grenade projectile.

```xml
<Sprite
 filename="data/projectiles_gfx/grenade.png"
 offset_x="4"
 offset_y="4"
 default_animation="fireball" >
</Sprite>
```

### Key Attributes:

*   **filename**: The path to the sprite image file.
*   **offset\_x**: Horizontal offset for the sprite.
*   **offset\_y**: Vertical offset for the sprite.
*   **default\_animation**: The name of the animation to play by default.

## Animation: `fireball`

Defines the animation sequence for the grenade's visual effect.

```xml
<RectAnimation
 name="fireball"
 pos_x="0"
 pos_y="0"
 frame_count="4"
 frame_width="8"
 frame_height="8"
 frame_wait="0.04"
 frames_per_row="4"
 loop="1" >
</RectAnimation>
```

### Key Attributes:

*   **name**: The identifier for this animation.
*   **pos\_x**: Starting X coordinate of the animation frames within the sprite sheet.
*   **pos\_y**: Starting Y coordinate of the animation frames within the sprite sheet.
*   **frame\_count**: The total number of frames in the animation.
*   **frame\_width**: The width of each individual animation frame.
*   **frame\_height**: The height of each individual animation frame.
*   **frame\_wait**: The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: The number of frames arranged horizontally in the sprite sheet.
*   **loop**: Whether the animation should loop (1 for true, 0 for false).