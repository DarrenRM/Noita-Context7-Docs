---
title: Racing Cart Killer Sprite
category: projectiles_gfx
---

# Racing Cart Killer Sprite

This document describes the sprite data for the "racing_cart_killer" projectile in Noita. It defines the visual appearance and animations used for this projectile.

## Sprite Attributes

The main `<Sprite>` tag defines the base image and its general properties.

| Attribute      | Value                               | Description                                                                 |
|----------------|-------------------------------------|-----------------------------------------------------------------------------|
| `default_animation` | `float`                             | The animation to play by default when the sprite is first created.          |
| `filename`     | `data/projectiles_gfx/racing_cart_killer.png` | The path to the image file containing the sprite frames.                    |
| `offset_x`     | `7`                                 | Horizontal offset for the sprite's origin.                                  |
| `offset_y`     | `7`                                 | Vertical offset for the sprite's origin.                                    |

## Animations

The `<Sprite>` tag contains one or more `<RectAnimation>` tags, each defining a distinct animation.

### `float` Animation

This animation is set as the `default_animation`.

| Attribute       | Value   | Description                                                                 |
|-----------------|---------|-----------------------------------------------------------------------------|
| `name`          | `float` | The name of this animation.                                                 |
| `frame_count`   | `4`     | The total number of frames in this animation.                               |
| `frame_width`   | `14`    | The width of each individual frame in pixels.                               |
| `frame_height`  | `15`    | The height of each individual frame in pixels.                              |
| `frame_wait`    | `0.12`  | The time in seconds to wait between each frame.                             |
| `frames_per_row`| `4`     | The number of frames arranged horizontally in the sprite sheet.             |
| `pos_x`         | `0`     | The starting X-coordinate of the animation frames within the sprite sheet.  |
| `pos_y`         | `1`     | The starting Y-coordinate of the animation frames within the sprite sheet.  |

### `fly` Animation

This animation provides an alternative visual for the projectile.

| Attribute       | Value   | Description                                                                 |
|-----------------|---------|-----------------------------------------------------------------------------|
| `name`          | `fly`   | The name of this animation.                                                 |
| `frame_count`   | `4`     | The total number of frames in this animation.                               |
| `frame_width`   | `15`    | The width of each individual frame in pixels.                               |
| `frame_height`  | `16`    | The height of each individual frame in pixels.                              |
| `frame_wait`    | `0.06`  | The time in seconds to wait between each frame.                             |
| `frames_per_row`| `4`     | The number of frames arranged horizontally in the sprite sheet.             |
| `pos_x`         | `0`     | The starting X-coordinate of the animation frames within the sprite sheet.  |
| `pos_y`         | `17`    | The starting Y-coordinate of the animation frames within the sprite sheet.  |
| `shrink_by_one_pixel` | `1` | Indicates that each frame should be shrunk by one pixel.                    |