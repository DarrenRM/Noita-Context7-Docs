---
title: Fireball Projectile Graphics
category: projectiles_gfx
---

# Fireball Projectile Graphics

This document describes the graphical assets for a smaller fireball projectile in Noita.

## Sprite Definition

The primary sprite definition for the fireball.

### Key Attributes:

*   **`default_animation`**: Specifies the name of the default animation to use, which is "fireball".
*   **`filename`**: The path to the sprite sheet containing the fireball's graphics.
*   **`offset_x`**: The horizontal offset of the sprite from its origin.
*   **`offset_y`**: The vertical offset of the sprite from its origin.

```xml
<Sprite 
  default_animation="fireball" 
  filename="data/projectiles_gfx/fireball_smaller.png" 
  offset_x="8" 
  offset_y="8" >
  </Sprite>
```

## RectAnimation: "fireball"

Defines the animation sequence for the "fireball" sprite.

### Key Attributes:

*   **`name`**: The name of this animation, matching `default_animation` in the `Sprite` tag.
*   **`frame_count`**: The total number of frames in the animation.
*   **`frame_width`**: The width of each individual frame.
*   **`frame_height`**: The height of each individual frame.
*   **`frames_per_row`**: How many frames are arranged horizontally in the sprite sheet.
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before advancing.
*   **`pos_x`**: The starting X-coordinate of the animation frames within the sprite sheet.
*   **`pos_y`**: The starting Y-coordinate of the animation frames within the sprite sheet.
*   **`shrink_by_one_pixel`**: A flag indicating if frames should be shrunk by one pixel, potentially for visual effect or collision.

```xml
<RectAnimation 
  frame_count="4" 
  frame_height="17" 
  frame_wait="0.09" 
  frame_width="17" 
  frames_per_row="4" 
  name="fireball" 
  pos_x="0" 
  pos_y="1" 
  shrink_by_one_pixel="1" >
</RectAnimation>
```