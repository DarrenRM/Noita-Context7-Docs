---
title: Large Grenade Projectile Graphics
category: projectiles_gfx
---

---

# Large Grenade Projectile Graphics

This document describes the graphical assets for the "large grenade" projectile in Noita, as defined in `grenade_large.xml`.

## Sprite Definition

The primary sprite definition for the large grenade is as follows:

```xml
<Sprite
 filename="data/projectiles_gfx/grenade_large.png"
 offset_x="6"
 offset_y="6"
 default_animation="fireball" >
</Sprite>
```

**Key Attributes:**

*   `filename`: Specifies the texture file used for the projectile's graphics.
*   `offset_x`, `offset_y`: Define the sprite's origin point relative to its center.
*   `default_animation`: Sets the initial animation to play when the projectile is created.

## Animation: `fireball`

The `fireball` animation defines how the sprite cycles through its frames to create the visual effect of the grenade.

```xml
<RectAnimation
 name="fireball"
 pos_x="0"
 pos_y="0"
 frame_count="4"
 frame_width="12"
 frame_height="12"
 frame_wait="0.05"
 frames_per_row="4"
 loop="1" >
</RectAnimation>
```

**Key Attributes:**

*   `name`: The identifier for this animation.
*   `pos_x`, `pos_y`: The top-left corner of the animation's frame area within the `filename` texture.
*   `frame_count`: The total number of frames in the animation.
*   `frame_width`, `frame_height`: The dimensions of each individual frame.
*   `frame_wait`: The duration (in seconds) each frame is displayed before advancing.
*   `frames_per_row`: How many frames are arranged horizontally in the texture.
*   `loop`: Determines if the animation should repeat (`1` for loop, `0` for no loop).