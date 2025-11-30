---
title: Red Orb Projectile Sprite
category: projectiles_gfx
---

# Red Orb Projectile Sprite

This documentation describes the sprite and animation for the "red orb" projectile in Noita, intended for AI-assisted modding.

## Sprite Definition

The core sprite definition for the red orb projectile.

```xml
<Sprite
 filename="data/projectiles_gfx/orb_red.png"
 offset_x="5"
 offset_y="5"
 default_animation="fireball" >
</Sprite>
```

### Key Attributes:

*   **filename**: Specifies the texture file used for the sprite.
*   **offset\_x**, **offset\_y**: Adjusts the sprite's position relative to its origin.
*   **default\_animation**: Sets the initial animation to play.

## Animation Definition

Defines the "fireball" animation for the red orb.

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

### Key Attributes:

*   **name**: The identifier for this animation.
*   **pos\_x**, **pos\_y**: The starting position of the animation frames within the sprite sheet.
*   **frame\_count**: The total number of frames in the animation.
*   **frame\_width**, **frame\_height**: Dimensions of each individual frame.
*   **frame\_wait**: The duration (in seconds) each frame is displayed before advancing.
*   **frames\_per\_row**: How many frames are arranged horizontally in the sprite sheet.
*   **loop**: Determines if the animation should repeat (1 for loop, 0 for no loop).