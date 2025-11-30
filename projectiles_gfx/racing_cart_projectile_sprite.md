---
title: Racing Cart Projectile Sprite
category: projectiles_gfx
---

# Racing Cart Projectile Sprite

This document describes the sprite data for the "racing_cart" projectile in Noita. It defines the visual appearance and animations used for this projectile.

## Sprite Attributes

The main `<Sprite>` tag defines the base properties of the projectile's visual representation.

| Attribute   | Description                                     | Key Value(s)                               |
| :---------- | :---------------------------------------------- | :----------------------------------------- |
| `filename`  | Path to the sprite image file.                  | `data/projectiles_gfx/racing_cart.png`     |
| `default_animation` | The animation to play by default.           | `float`                                    |
| `offset_x`  | Horizontal offset for the sprite.               | `7`                                        |
| `offset_y`  | Vertical offset for the sprite.                 | `7`                                        |

## Animations

The `<Sprite>` tag contains one or more `<RectAnimation>` tags, each defining a specific animation sequence.

### `float` Animation

This animation is set as the default for the racing cart projectile.

| Attribute        | Description                                     | Key Value(s)                               |
| :--------------- | :---------------------------------------------- | :----------------------------------------- |
| `name`           | The name of the animation.                      | `float`                                    |
| `frame_count`    | Total number of frames in the animation.        | `4`                                        |
| `frame_width`    | Width of each individual frame.                 | `14`                                       |
| `frame_height`   | Height of each individual frame.                | `15`                                       |
| `frames_per_row` | Number of frames arranged horizontally in the sprite sheet. | `4`                                        |
| `frame_wait`     | Time in seconds to display each frame.          | `0.12`                                     |
| `pos_x`          | X-coordinate of the top-left corner of the animation frames within the sprite sheet. | `0`                                        |
| `pos_y`          | Y-coordinate of the top-left corner of the animation frames within the sprite sheet. | `1`                                        |

### `fly` Animation

This animation is an alternative that can be triggered for the racing cart projectile.

| Attribute        | Description                                     | Key Value(s)                               |
| :--------------- | :---------------------------------------------- | :----------------------------------------- |
| `name`           | The name of the animation.                      | `fly`                                      |
| `frame_count`    | Total number of frames in the animation.        | `4`                                        |
| `frame_width`    | Width of each individual frame.                 | `15`                                       |
| `frame_height`   | Height of each individual frame.                | `16`                                       |
| `frames_per_row` | Number of frames arranged horizontally in the sprite sheet. | `4`                                        |
| `frame_wait`     | Time in seconds to display each frame.          | `0.06`                                     |
| `pos_x`          | X-coordinate of the top-left corner of the animation frames within the sprite sheet. | `0`                                        |
| `pos_y`          | Y-coordinate of the top-left corner of the animation frames within the sprite sheet. | `17`                                       |
| `shrink_by_one_pixel` | Indicates if frames should be shrunk by one pixel. | `1`                                        |