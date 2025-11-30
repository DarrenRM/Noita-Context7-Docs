---
title: Tiny Ghost Projectile Sprite
category: projectiles_gfx
---

# Tiny Ghost Projectile Sprite

This document details the sprite information for the "tiny_ghost" projectile in Noita, focusing on its visual representation and animations.

## Sprite Attributes

The main `<Sprite>` element defines the core visual properties of the projectile.

| Attribute         | Description                                     |
| :---------------- | :---------------------------------------------- |
| `default_animation` | The animation to play by default.               |
| `filename`        | Path to the sprite image file.                  |
| `offset_x`        | Horizontal offset for the sprite's origin.      |
| `offset_y`        | Vertical offset for the sprite's origin.        |

## Animations

The `<Sprite>` element contains multiple `<RectAnimation>` elements, each defining a distinct animation sequence.

### `float_right` Animation

This animation likely represents the ghost floating to the right.

| Attribute       | Description                                     |
| :-------------- | :---------------------------------------------- |
| `name`          | The name of the animation.                      |
| `frame_count`   | Total number of frames in the animation.        |
| `frame_height`  | Height of each individual frame.                |
| `frame_wait`    | Time in seconds to wait between frames.         |
| `frame_width`   | Width of each individual frame.                 |
| `frames_per_row`| Number of frames arranged horizontally in the sprite sheet. |
| `pos_x`         | X-coordinate of the animation's starting frame in the sprite sheet. |
| `pos_y`         | Y-coordinate of the animation's starting frame in the sprite sheet. |

### `float_left` Animation

This animation likely represents the ghost floating to the left.

| Attribute       | Description                                     |
| :-------------- | :---------------------------------------------- |
| `name`          | The name of the animation.                      |
| `frame_count`   | Total number of frames in the animation.        |
| `frame_height`  | Height of each individual frame.                |
| `frame_wait`    | Time in seconds to wait between frames.         |
| `frame_width`   | Width of each individual frame.                 |
| `frames_per_row`| Number of frames arranged horizontally in the sprite sheet. |
| `pos_x`         | X-coordinate of the animation's starting frame in the sprite sheet. |
| `pos_y`         | Y-coordinate of the animation's starting frame in the sprite sheet. |

### `fly_right` Animation

This animation likely represents the ghost flying to the right.

| Attribute       | Description                                     |
| :-------------- | :---------------------------------------------- |
| `name`          | The name of the animation.                      |
| `frame_count`   | Total number of frames in the animation.        |
| `frame_height`  | Height of each individual frame.                |
| `frame_wait`    | Time in seconds to wait between frames.         |
| `frame_width`   | Width of each individual frame.                 |
| `frames_per_row`| Number of frames arranged horizontally in the sprite sheet. |
| `pos_x`         | X-coordinate of the animation's starting frame in the sprite sheet. |
| `pos_y`         | Y-coordinate of the animation's starting frame in the sprite sheet. |

### `fly_left` Animation

This animation likely represents the ghost flying to the left.

| Attribute       | Description                                     |
| :-------------- | :---------------------------------------------- |
| `name`          | The name of the animation.                      |
| `frame_count`   | Total number of frames in the animation.        |
| `frame_height`  | Height of each individual frame.                |
| `frame_wait`    | Time in seconds to wait between frames.         |
| `frame_width`   | Width of each individual frame.                 |
| `frames_per_row`| Number of frames arranged horizontally in the sprite sheet. |
| `pos_x`         | X-coordinate of the animation's starting frame in the sprite sheet. |
| `pos_y`         | Y-coordinate of the animation's starting frame in the sprite sheet. |