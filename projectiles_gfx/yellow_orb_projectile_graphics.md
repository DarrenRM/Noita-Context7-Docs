---
title: Yellow Orb Projectile Graphics
category: projectiles_gfx
---

# Yellow Orb Projectile Graphics

This document describes the graphical assets for the "Yellow Orb" projectile in Noita.

## Sprite Definition

The primary sprite definition for the yellow orb projectile is as follows:

```xml
<Sprite
 filename="data/projectiles_gfx/orb_yellow.png"
 offset_x="5"
 offset_y="5"
 default_animation="fireball" >
</Sprite>
```

**Key Attributes:**

*   `filename`: Specifies the texture file used for the sprite.
*   `offset_x`, `offset_y`: Define the sprite's origin point relative to its center.
*   `default_animation`: Sets the animation to play by default when the projectile is created.

## Animation: `fireball`

The `fireball` animation defines how the `orb_yellow.png` texture is displayed over time.

```xml
<RectAnimation
 name="fireball"
 pos_x="0"
 pos_y="0"
 frame_count="4"
 frame_width="10"
 frame_height="10"
 frame_wait="0.09"
 frames_per_row="4"
 loop="1" >
</RectAnimation>
```

**Key Attributes:**

*   `name`: The identifier for this animation, referenced by `default_animation`.
*   `pos_x`, `pos_y`: The top-left corner of the animation's sprite sheet region.
*   `frame_count`: The total number of frames in the animation.
*   `frame_width`, `frame_height`: The dimensions of each individual frame.
*   `frame_wait`: The duration (in seconds) each frame is displayed before advancing.
*   `frames_per_row`: How many frames are arranged horizontally in the sprite sheet.
*   `loop`: Determines if the animation should repeat (`1` for loop, `0` for no loop).