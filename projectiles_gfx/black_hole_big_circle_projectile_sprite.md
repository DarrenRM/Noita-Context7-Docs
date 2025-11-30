---
title: Black Hole Big Circle Projectile Sprite
category: projectiles_gfx
---

# Black Hole Big Circle Projectile Sprite

This document details the sprite information for the "black_hole_big_circle" projectile in Noita, focusing on its visual representation and animation.

## Sprite Attributes

The main `<Sprite>` tag defines the core visual properties of the projectile.

| Attribute      | Value                               | Description                                                                 |
| -------------- | ----------------------------------- | --------------------------------------------------------------------------- |
| `default_animation` | `spawn`                             | The animation to play by default when the projectile is created.            |
| `filename`     | `data/projectiles_gfx/black_hole_big_circle.png` | The path to the image file containing the projectile's sprite frames.       |
| `offset_x`     | `67`                                | Horizontal offset for the sprite's origin.                                  |
| `offset_y`     | `67`                                | Vertical offset for the sprite's origin.                                    |

## Animations

The `<Sprite>` tag contains one or more `<RectAnimation>` tags, each defining a distinct animation sequence.

### `spawn` Animation

This animation is used for the initial appearance of the projectile.

| Attribute       | Value   | Description                                                                                             |
| --------------- | ------- | ------------------------------------------------------------------------------------------------------- |
| `name`          | `spawn` | The name of this animation, referenced by `default_animation` or other animations.                      |
| `frame_count`   | `64`    | The total number of frames in this animation.                                                           |
| `frame_width`   | `130`   | The width of each individual frame in pixels.                                                           |
| `frame_height`  | `130`   | The height of each individual frame in pixels.                                                          |
| `frames_per_row`| `13`    | The number of frames arranged horizontally in the sprite sheet.                                         |
| `frame_wait`    | `0.06`  | The duration (in seconds) each frame is displayed before transitioning to the next.                       |
| `loop`          | `0`     | Determines if the animation should loop. `0` means it does not loop.                                    |
| `next_animation`| `fireball`| The name of the animation to transition to after this one completes.                                    |
| `pos_x`         | `0`     | The X-coordinate of the top-left corner of the animation's frame area within the sprite sheet.          |
| `pos_y`         | `1`     | The Y-coordinate of the top-left corner of the animation's frame area within the sprite sheet.          |

### `fireball` Animation

This animation likely represents the projectile in its active, "fireball" state.

| Attribute       | Value   | Description                                                                                             |
| --------------- | ------- | ------------------------------------------------------------------------------------------------------- |
| `name`          | `fireball`| The name of this animation.                                                                             |
| `frame_count`   | `2`     | The total number of frames in this animation.                                                           |
| `frame_width`   | `131`   | The width of each individual frame in pixels.                                                           |
| `frame_height`  | `131`   | The height of each individual frame in pixels.                                                          |
| `frames_per_row`| `13`    | The number of frames arranged horizontally in the sprite sheet.                                         |
| `frame_wait`    | `0.01`  | The duration (in seconds) each frame is displayed before transitioning to the next.                       |
| `pos_x`         | `1441`  | The X-coordinate of the top-left corner of the animation's frame area within the sprite sheet.          |
| `pos_y`         | `652`   | The Y-coordinate of the top-left corner of the animation's frame area within the sprite sheet.          |
| `shrink_by_one_pixel` | `1` | Indicates that each frame should be shrunk by one pixel, potentially for a shrinking effect.            |