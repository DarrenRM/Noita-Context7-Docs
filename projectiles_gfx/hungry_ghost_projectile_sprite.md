---
title: Hungry Ghost Projectile Sprite
category: projectiles_gfx
---

# Hungry Ghost Projectile Sprite

This document details the sprite information for the "Hungry Ghost" projectile in Noita, focusing on its visual animation and positioning.

## Sprite Attributes

The main `<Sprite>` element defines the core visual properties of the projectile.

| Attribute        | Value      | Description                                                                 |
| :--------------- | :--------- | :-------------------------------------------------------------------------- |
| `default_animation` | `float_right` | The animation to play by default when the projectile is spawned.            |
| `filename`       | `data/projectiles_gfx/hungry_ghost.png` | The path to the image file containing the sprite frames.                  |
| `offset_x`       | `4.5`      | Horizontal offset for the sprite's origin.                                  |
| `offset_y`       | `5`        | Vertical offset for the sprite's origin.                                    |

## Animation Definitions

The `<Sprite>` element contains multiple `<RectAnimation>` elements, each defining a distinct animation sequence.

### `float_right` Animation

| Attribute       | Value   | Description                                                                 |
| :-------------- | :------ | :-------------------------------------------------------------------------- |
| `name`          | `float_right` | Identifier for this animation.                                              |
| `frame_count`   | `8`     | Total number of frames in this animation.                                   |
| `frame_height`  | `10`    | The height of each individual frame in pixels.                              |
| `frame_wait`    | `0.14`  | The duration (in seconds) each frame is displayed before advancing.         |
| `frame_width`   | `9`     | The width of each individual frame in pixels.                               |
| `frames_per_row`| `12`    | How many frames are arranged horizontally in the sprite sheet.              |
| `pos_x`         | `0`     | The starting X coordinate of the animation frames within the sprite sheet.  |
| `pos_y`         | `0`     | The starting Y coordinate of the animation frames within the sprite sheet.  |

### `float_left` Animation

| Attribute       | Value   | Description                                                                 |
| :-------------- | :------ | :-------------------------------------------------------------------------- |
| `name`          | `float_left` | Identifier for this animation.                                              |
| `frame_count`   | `8`     | Total number of frames in this animation.                                   |
| `frame_height`  | `10`    | The height of each individual frame in pixels.                              |
| `frame_wait`    | `0.14`  | The duration (in seconds) each frame is displayed before advancing.         |
| `frame_width`   | `9`     | The width of each individual frame in pixels.                               |
| `frames_per_row`| `8`     | How many frames are arranged horizontally in the sprite sheet.              |
| `pos_x`         | `0`     | The starting X coordinate of the animation frames within the sprite sheet.  |
| `pos_y`         | `10`    | The starting Y coordinate of the animation frames within the sprite sheet.  |

### `fly_right` Animation

| Attribute       | Value   | Description                                                                 |
| :-------------- | :------ | :-------------------------------------------------------------------------- |
| `name`          | `fly_right` | Identifier for this animation.                                              |
| `frame_count`   | `4`     | Total number of frames in this animation.                                   |
| `frame_height`  | `10`    | The height of each individual frame in pixels.                              |
| `frame_wait`    | `0.08`  | The duration (in seconds) each frame is displayed before advancing.         |
| `frame_width`   | `9`     | The width of each individual frame in pixels.                               |
| `frames_per_row`| `8`     | How many frames are arranged horizontally in the sprite sheet.              |
| `pos_x`         | `0`     | The starting X coordinate of the animation frames within the sprite sheet.  |
| `pos_y`         | `20`    | The starting Y coordinate of the animation frames within the sprite sheet.  |

### `fly_left` Animation

| Attribute       | Value   | Description                                                                 |
| :-------------- | :------ | :-------------------------------------------------------------------------- |
| `name`          | `fly_left`  | Identifier for this animation.                                              |
| `frame_count`   | `4`     | Total number of frames in this animation.                                   |
| `frame_height`  | `10`    | The height of each individual frame in pixels.                              |
| `frame_wait`    | `0.08`  | The duration (in seconds) each frame is displayed before advancing.         |
| `frame_width`   | `9`     | The width of each individual frame in pixels.                               |
| `frames_per_row`| `8`     | How many frames are arranged horizontally in the sprite sheet.              |
| `pos_x`         | `0`     | The starting X coordinate of the animation frames within the sprite sheet.  |
| `pos_y`         | `30`    | The starting Y coordinate of the animation frames within the sprite sheet.  |