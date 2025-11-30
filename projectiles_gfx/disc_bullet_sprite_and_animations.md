---
title: Disc Bullet Sprite and Animations
category: guides
---

<Sprite
 filename="data/projectiles_gfx/disc_bullet.png"
 offset_x="4.5"
 offset_y="4.5"
 default_animation="fireball" >

 <!-- animation -->
 <RectAnimation
  name="fireball"
  pos_x="0"
  pos_y="0"
  frame_count="4"
  frame_width="9"
  frame_height="9"
  frame_wait="0.04"
  frames_per_row="4"
  loop="1"   >
 </RectAnimation>

 <RectAnimation
  name="on_ground"
  pos_x="0"
  pos_y="0"
  frame_count="1"
  frame_width="9"
  frame_height="9"
  frame_wait="0.02"
  frames_per_row="4"
  loop="0"   >
 </RectAnimation>
 

</Sprite>
```

---
title: Disc Bullet Sprite and Animations
category: projectiles_gfx
---

# Disc Bullet Sprite and Animations

This document details the sprite and animation definitions for the "disc bullet" projectile in Noita, as found in `disc_bullet_constant.xml`.

## Sprite Definition

The primary sprite for the disc bullet is defined by the `<Sprite>` tag.

### Key Attributes:

*   **`filename`**: Specifies the texture file used for the sprite.
    *   `data/projectiles_gfx/disc_bullet.png`
*   **`offset_x`**: Horizontal offset for the sprite's origin.
    *   `4.5`
*   **`offset_y`**: Vertical offset for the sprite's origin.
    *   `4.5`
*   **`default_animation`**: The animation to play by default.
    *   `fireball`

## Animations

The projectile utilizes two distinct animations defined by `<RectAnimation>` tags.

### `fireball` Animation

This animation is used during the projectile's active flight.

#### Key Attributes:

*   **`name`**: The identifier for this animation.
    *   `fireball`
*   **`pos_x`**: Starting X position within the sprite sheet.
    *   `0`
*   **`pos_y`**: Starting Y position within the sprite sheet.
    *   `0`
*   **`frame_count`**: Total number of frames in the animation.
    *   `4`
*   **`frame_width`**: Width of each individual frame.
    *   `9`
*   **`frame_height`**: Height of each individual frame.
    *   `9`
*   **`frame_wait`**: Time in seconds between each frame.
    *   `0.04`
*   **`frames_per_row`**: Number of frames arranged horizontally in the sprite sheet.
    *   `4`
*   **`loop`**: Whether the animation should loop.
    *   `1` (true)

### `on_ground` Animation

This animation is intended for when the projectile is on the ground.

#### Key Attributes:

*   **`name`**: The identifier for this animation.
    *   `on_ground`
*   **`pos_x`**: Starting X position within the sprite sheet.
    *   `0`
*   **`pos_y`**: Starting Y position within the sprite sheet.
    *   `0`
*   **`frame_count`**: Total number of frames in the animation.
    *   `1`
*   **`frame_width`**: Width of each individual frame.
    *   `9`
*   **`frame_height`**: Height of each individual frame.
    *   `9`
*   **`frame_wait`**: Time in seconds between each frame.
    *   `0.02`
*   **`frames_per_row`**: Number of frames arranged horizontally in the sprite sheet.
    *   `4`
*   **`loop`**: Whether the animation should loop.
    *   `0` (false)