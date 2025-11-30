---
title: Big Pink Orb Projectile Sprite
category: projectiles_gfx
---

# Big Pink Orb Projectile Sprite

This document describes the sprite data for the "Big Pink Orb" projectile in Noita, intended for AI-assisted modding.

## Sprite Definition

The primary sprite definition for this projectile is as follows:

```xml
<Sprite
 filename="data/projectiles_gfx/orb_pink_big.png"
 offset_x="8"
 offset_y="8"
 default_animation="fireball" >
</Sprite>
```

### Key Attributes:

*   **filename**: Specifies the texture file used for the sprite (`data/projectiles_gfx/orb_pink_big.png`).
*   **offset_x**: The horizontal offset of the sprite's origin.
*   **offset_y**: The vertical offset of the sprite's origin.
*   **default_animation**: The name of the animation to be used by default.

## Animation: `fireball`

The projectile utilizes a `RectAnimation` for its visual representation.

```xml
<RectAnimation
 name="fireball"
 pos_x="0"
 pos_y="0"
 frame_count="4"
 frame_width="16"
 frame_height="16"
 frame_wait="0.05"
 frames_per_row="4"
 loop="1" >
</RectAnimation>
```

### Key Attributes:

*   **name**: The identifier for this animation, matching `default_animation` in the `Sprite` tag.
*   **pos_x**: The starting X-coordinate of the animation frames within the texture.
*   **pos_y**: The starting Y-coordinate of the animation frames within the texture.
*   **frame_count**: The total number of frames in the animation.
*   **frame_width**: The width of each individual animation frame.
*   **frame_height**: The height of each individual animation frame.
*   **frame_wait**: The duration (in seconds) each frame is displayed before transitioning to the next.
*   **frames_per_row**: The number of frames arranged horizontally in the texture.
*   **loop**: Indicates whether the animation should loop (1 for true, 0 for false).