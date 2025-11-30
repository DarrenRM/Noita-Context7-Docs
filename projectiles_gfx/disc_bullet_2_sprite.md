---
title: Disc Bullet 2 Sprite
category: projectiles_gfx
---

# Disc Bullet 2 Sprite

This document describes the sprite and animation data for the "disc_bullet_2" projectile in Noita.

## Sprite Attributes

The primary sprite for this projectile is defined by the `<Sprite>` tag.

| Attribute     | Description                                     |
|---------------|-------------------------------------------------|
| `filename`    | Path to the sprite image file.                  |
| `offset_x`    | Horizontal offset for the sprite's origin.      |
| `offset_y`    | Vertical offset for the sprite's origin.        |
| `default_animation` | The name of the default animation to play. |

```xml
<Sprite
 filename="data/projectiles_gfx/disc_bullet_2.png"
 offset_x="4.5"
 offset_y="4.5"
 default_animation="fireball" >
</Sprite>
```

## Animation Data

The projectile uses a rectangular animation named "fireball".

### RectAnimation Attributes

| Attribute        | Description                                     |
|------------------|-------------------------------------------------|
| `name`           | The name of this animation.                     |
| `pos_x`          | Starting X position of the animation frames.    |
| `pos_y`          | Starting Y position of the animation frames.    |
| `frame_count`    | Total number of frames in the animation.        |
| `frame_width`    | Width of each individual frame.                 |
| `frame_height`   | Height of each individual frame.                |
| `frame_wait`     | Time in seconds to wait between frames.         |
| `frames_per_row` | Number of frames arranged horizontally in the sprite sheet. |
| `loop`           | Whether the animation should loop (1 for true, 0 for false). |

```xml
<RectAnimation
 name="fireball"
 pos_x="0"
 pos_y="0"
 frame_count="4"
 frame_width="9"
 frame_height="9"
 frame_wait="0.02"
 frames_per_row="4"
 loop="1" >
</RectAnimation>
```