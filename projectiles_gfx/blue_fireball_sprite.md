---
title: Blue Fireball Sprite
category: projectiles_gfx
---

# Blue Fireball Sprite

This document describes the sprite definition for a smaller blue fireball projectile in Noita.

## Sprite Definition

The `<Sprite>` element defines the visual appearance and animation of the projectile.

### Key Attributes:

*   **`default_animation`**: Specifies the name of the default animation to play, which is "fireball" in this case.
*   **`filename`**: The path to the sprite sheet image file.
*   **`offset_x`**: Horizontal offset for the sprite's origin.
*   **`offset_y`**: Vertical offset for the sprite's origin.

```xml
<Sprite 
  default_animation="fireball" 
  filename="data/projectiles_gfx/fireball_smaller_blue.png" 
  offset_x="8" 
  offset_y="8" >
  </Sprite>
```

## Animation Definition

The `<RectAnimation>` element defines the specific animation frames and timing.

### Key Attributes:

*   **`name`**: The name of this animation, matching the `default_animation` in the `<Sprite>` tag.
*   **`frame_count`**: The total number of frames in the animation.
*   **`frame_width`**: The width of each individual frame.
*   **`frame_height`**: The height of each individual frame.
*   **`frames_per_row`**: How many frames are arranged horizontally in the sprite sheet.
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before advancing.
*   **`pos_x`**: The X-coordinate of the top-left corner of the animation within the sprite sheet.
*   **`pos_y`**: The Y-coordinate of the top-left corner of the animation within the sprite sheet.
*   **`shrink_by_one_pixel`**: A flag indicating if frames should be shrunk by one pixel (often used for certain sprite effects).

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