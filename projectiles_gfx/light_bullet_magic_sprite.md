---
title: Light Bullet Magic Sprite
category: guides
---

<Sprite 
  default_animation="fireball" 
  filename="data/projectiles_gfx/light_bullet_magic.png" 
  offset_x="0.5" 
  offset_y="0.5" >

  <RectAnimation 
    frame_count="1" 
    frame_height="2" 
    frame_wait="0.2" 
    frame_width="5" 
    frames_per_row="4" 
    loop="0" 
    name="fireball" 
    pos_x="0" 
    pos_y="1" 
    shrink_by_one_pixel="1" >

  </RectAnimation>

</Sprite>
```

---
title: Light Bullet Magic Sprite
category: projectiles_gfx
---

# Light Bullet Magic Sprite

This document details the sprite definition for the "light_bullet_magic" projectile in Noita. It focuses on the visual representation and animation of this projectile.

## Sprite Attributes

The `<Sprite>` tag defines the primary visual properties of the projectile.

### Key Attributes:

*   **`default_animation`**: Specifies the name of the animation to be used by default.
    *   Value: `"fireball"`
*   **`filename`**: The path to the image file containing the projectile's graphics.
    *   Value: `"data/projectiles_gfx/light_bullet_magic.png"`
*   **`offset_x`**: The horizontal offset of the sprite's origin.
    *   Value: `"0.5"` (50% from the left edge)
*   **`offset_y`**: The vertical offset of the sprite's origin.
    *   Value: `"0.5"` (50% from the top edge)

## RectAnimation - "fireball"

The `<RectAnimation>` tag defines a specific animation sequence using a rectangular grid of frames within the sprite sheet.

### Key Attributes:

*   **`name`**: The identifier for this animation.
    *   Value: `"fireball"`
*   **`frame_count`**: The total number of frames in this animation.
    *   Value: `"1"`
*   **`frame_width`**: The width of each individual frame in pixels.
    *   Value: `"5"`
*   **`frame_height`**: The height of each individual frame in pixels.
    *   Value: `"2"`
*   **`frames_per_row`**: How many frames are arranged horizontally in the sprite sheet.
    *   Value: `"4"`
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before advancing.
    *   Value: `"0.2"`
*   **`loop`**: Determines if the animation should loop.
    *   Value: `"0"` (0 means no loop, 1 means loop)
*   **`pos_x`**: The starting horizontal position (in frames) of the animation sequence within the sprite sheet.
    *   Value: `"0"`
*   **`pos_y`**: The starting vertical position (in frames) of the animation sequence within the sprite sheet.
    *   Value: `"1"`
*   **`shrink_by_one_pixel`**: A flag that affects how the sprite is rendered, potentially by shrinking it by one pixel.
    *   Value: `"1"`