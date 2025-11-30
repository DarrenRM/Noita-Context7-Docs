---
title: Quantum FX Red Sprite
category: projectiles_gfx
---

# Quantum FX Red Sprite

This document describes the sprite definition for the "Quantum FX Red" projectile effect in Noita.

## Sprite Definition

The primary `Sprite` element defines the visual appearance and animation of the projectile.

### Key Attributes:

*   **`default_animation`**: Specifies the name of the animation to be used by default. In this case, it's "fireball".
*   **`filename`**: The path to the image file containing the sprite's graphical assets.
*   **`offset_x`**: Horizontal offset for the sprite's origin.
*   **`offset_y`**: Vertical offset for the sprite's origin.

```xml
<Sprite 
  default_animation="fireball" 
  filename="data/projectiles_gfx/quantum_fx_red.png" 
  offset_x="8" 
  offset_y="8" >
  </Sprite>
```

## Animation Details

The `RectAnimation` element defines how the sprite frames are arranged and played.

### Key Attributes:

*   **`name`**: The name of this specific animation, referenced by `default_animation` in the `Sprite` tag.
*   **`frame_count`**: The total number of frames in the animation.
*   **`frame_width`**: The width of each individual frame.
*   **`frame_height`**: The height of each individual frame.
*   **`frames_per_row`**: How many frames are arranged horizontally in the sprite sheet.
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before transitioning to the next.
*   **`pos_x`**: The starting X position of the animation frames within the sprite sheet.
*   **`pos_y`**: The starting Y position of the animation frames within the sprite sheet.
*   **`shrink_by_one_pixel`**: A boolean attribute (implicitly 1 for true) that indicates if frames should be shrunk by one pixel.

```xml
<RectAnimation 
  frame_count="4" 
  frame_height="17" 
  frame_wait="0.06" 
  frame_width="17" 
  frames_per_row="7" 
  name="fireball" 
  pos_x="0" 
  pos_y="1" 
  shrink_by_one_pixel="1" >
</RectAnimation>
```