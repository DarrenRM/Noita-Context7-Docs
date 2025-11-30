---
title: Thunderball Projectile Graphics
category: projectiles_gfx
---

# Thunderball Projectile Graphics

This document details the graphical assets for the "thunderball" projectile in Noita, as defined in `thunderball.xml`.

## Sprite Definition

The primary sprite definition for the thunderball projectile.

```xml
<Sprite 
  default_animation="fireball" 
  filename="data/projectiles_gfx/thunderball.png" 
  offset_x="11" 
  offset_y="11" >
  <!-- ... RectAnimation details ... -->
</Sprite>
```

### Key Attributes:

*   **`default_animation`**: Specifies the default animation to use, which is "fireball" in this case.
*   **`filename`**: The path to the texture file containing the projectile's graphics.
*   **`offset_x`**: Horizontal offset for the sprite.
*   **`offset_y`**: Vertical offset for the sprite.

## RectAnimation: "fireball"

Defines the animation sequence for the "fireball" state of the thunderball projectile.

```xml
<RectAnimation 
  frame_count="5" 
  frame_height="23" 
  frame_wait="0.06" 
  frame_width="23" 
  frames_per_row="5" 
  name="fireball" 
  pos_x="0" 
  pos_y="1" 
  shrink_by_one_pixel="1" >
</RectAnimation>
```

### Key Attributes:

*   **`name`**: The name of this animation, "fireball".
*   **`frame_count`**: The total number of frames in the animation.
*   **`frame_width`**: The width of each individual frame.
*   **`frame_height`**: The height of each individual frame.
*   **`frames_per_row`**: How many frames are arranged horizontally in the texture.
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before advancing.
*   **`pos_x`**: The starting X position of the animation frames within the texture.
*   **`pos_y`**: The starting Y position of the animation frames within the texture.
*   **`shrink_by_one_pixel`**: A flag indicating if frames should shrink by one pixel.