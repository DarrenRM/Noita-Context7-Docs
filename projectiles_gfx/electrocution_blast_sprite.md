---
title: Electrocution Blast Sprite
category: projectiles_gfx
---

# Electrocution Blast Sprite

This document details the sprite information for the "blast_electrocution" projectile in Noita, focusing on its visual representation and animation.

## Sprite Attributes

The main `<Sprite>` tag defines the overall visual properties of the projectile.

| Attribute   | Value   | Description                                                                 |
| :---------- | :------ | :-------------------------------------------------------------------------- |
| `filename`  | `data/projectiles_gfx/blast_electrocution.png` | Path to the sprite image file.                                              |
| `offset_x`  | `32`    | Horizontal offset for the sprite's origin.                                  |
| `offset_y`  | `32`    | Vertical offset for the sprite's origin.                                    |
| `color_r`   | `0.6`   | Red component of the sprite's tint.                                         |
| `color_g`   | `0.9`   | Green component of the sprite's tint.                                       |
| `color_b`   | `1`     | Blue component of the sprite's tint.                                        |
| `color_a`   | `1`     | Alpha (transparency) component of the sprite's tint.                        |
| `default_animation` | `spawn` | The animation to play by default when the sprite is first created.          |

## Animations

The `<Sprite>` tag contains multiple `<RectAnimation>` tags, each defining a distinct animation sequence.

### `spawn` Animation

This animation is typically used for the initial appearance or "spawning" of the projectile.

| Attribute       | Value   | Description                                                                 |
| :-------------- | :------ | :-------------------------------------------------------------------------- |
| `name`          | `spawn` | The name of this animation.                                                 |
| `frame_count`   | `5`     | Total number of frames in this animation.                                   |
| `frame_width`   | `65`    | Width of each individual frame.                                             |
| `frame_height`  | `65`    | Height of each individual frame.                                            |
| `frames_per_row`| `4`     | Number of frames arranged horizontally in the sprite sheet.                 |
| `frame_wait`    | `0.04`  | Time in seconds to wait between each frame.                                 |
| `loop`          | `0`     | Whether the animation should loop (0 = no, 1 = yes).                        |
| `next_animation`| `fireball`| The animation to transition to after this one finishes.                   |
| `pos_x`         | `0`     | X-coordinate of the top-left corner of the animation frames within the sprite sheet. |
| `pos_y`         | `1`     | Y-coordinate of the top-left corner of the animation frames within the sprite sheet. |
| `shrink_by_one_pixel` | `1` | Whether each frame should shrink by one pixel after each iteration (often used for fading effects). |

### `fireball` Animation

This animation likely represents the main visual state of the projectile while in flight.

| Attribute       | Value   | Description                                                                 |
| :-------------- | :------ | :-------------------------------------------------------------------------- |
| `name`          | `fireball`| The name of this animation.                                                 |
| `frame_count`   | `4`     | Total number of frames in this animation.                                   |
| `frame_width`   | `64`    | Width of each individual frame.                                             |
| `frame_height`  | `64`    | Height of each individual frame.                                            |
| `frames_per_row`| `4`     | Number of frames arranged horizontally in the sprite sheet.                 |
| `frame_wait`    | `0.03`  | Time in seconds to wait between each frame.                                 |
| `pos_x`         | `0`     | X-coordinate of the top-left corner of the animation frames within the sprite sheet. |
| `pos_y`         | `131`   | Y-coordinate of the top-left corner of the animation frames within the sprite sheet. |