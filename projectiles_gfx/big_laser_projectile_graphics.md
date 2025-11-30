---
title: Big Laser Projectile Graphics
category: projectiles_gfx
---

---

# Big Laser Projectile Graphics

This document describes the graphical assets for the "big laser" projectile in Noita, as defined in `laser_big.xml`.

## Sprite Definition

The primary sprite definition for this projectile is as follows:

```xml
<Sprite
 filename="data/projectiles_gfx/laser_big.png"
 offset_x="2"
 offset_y="2.5"
 default_animation="fireball" >
```

### Key Attributes:

*   **filename**: Specifies the texture file used for the projectile's graphics.
*   **offset\_x**, **offset\_y**: Define the graphical offset of the sprite from its origin.
*   **default\_animation**: Sets the initial animation to play when the projectile is created.

## Animation: `fireball`

The `fireball` animation defines how the projectile's sprite is rendered over time.

```xml
<RectAnimation
 name="fireball"
 pos_x="0"
 pos_y="0"
 frame_count="2"
 frame_width="8"
 frame_height="5"
 frame_wait="0.02"
 frames_per_row="2"
 loop="1" >
</RectAnimation>
```

### Key Attributes:

*   **name**: The identifier for this animation.
*   **pos\_x**, **pos\_y**: The starting position of the animation frames within the sprite sheet.
*   **frame\_count**: The total number of frames in the animation.
*   **frame\_width**, **frame\_height**: The dimensions of each individual frame.
*   **frame\_wait**: The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: How many frames are arranged horizontally in the sprite sheet.
*   **loop**: Indicates if the animation should repeat (1 for true, 0 for false).