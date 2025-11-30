---
title: Ghostly Fireball Sprite
category: projectiles_gfx
---

# Ghostly Fireball Sprite

This document details the sprite information for the "Ghostly Fireball" projectile in Noita, focusing on its visual animation and rendering properties.

## Sprite Attributes

The main `<Sprite>` tag defines the overall visual representation and its primary texture file.

| Attribute     | Value                               | Description                                                                 |
|---------------|-------------------------------------|-----------------------------------------------------------------------------|
| `default_animation` | `spawn`                             | The animation to play by default when the sprite is first created.          |
| `filename`    | `data/projectiles_gfx/fireball_ghostly.png` | The path to the image file containing the sprite's frames.                  |
| `offset_x`    | `16`                                | Horizontal offset for the sprite's origin.                                  |
| `offset_y`    | `12`                                | Vertical offset for the sprite's origin.                                    |

## Animations

The sprite utilizes two distinct `RectAnimation` blocks to define its visual sequences: `fireball` and `spawn`.

### `fireball` Animation

This animation likely represents the active state of the ghostly fireball.

| Attribute       | Value   | Description                                                              |
|-----------------|---------|--------------------------------------------------------------------------|
| `name`          | `fireball` | The identifier for this animation.                                       |
| `frame_count`   | `4`     | The total number of frames in this animation sequence.                   |
| `frame_width`   | `33`    | The width of each individual frame in pixels.                            |
| `frame_height`  | `25`    | The height of each individual frame in pixels.                           |
| `frames_per_row`| `4`     | How many frames are arranged horizontally in the sprite sheet.           |
| `frame_wait`    | `0.035` | The duration (in seconds) each frame is displayed before advancing.      |
| `pos_x`         | `0`     | The X-coordinate of the top-left corner of the animation frames in the sprite sheet. |
| `pos_y`         | `1`     | The Y-coordinate of the top-left corner of the animation frames in the sprite sheet. |
| `shrink_by_one_pixel` | `1` | Indicates if frames should be shrunk by one pixel, potentially for smoother transitions or effects. |

### `spawn` Animation

This animation defines the initial appearance or "spawn" effect of the ghostly fireball.

| Attribute       | Value   | Description                                                              |
|-----------------|---------|--------------------------------------------------------------------------|
| `name`          | `spawn` | The identifier for this animation.                                       |
| `frame_count`   | `4`     | The total number of frames in this animation sequence.                   |
| `frame_width`   | `32`    | The width of each individual frame in pixels.                            |
| `frame_height`  | `24`    | The height of each individual frame in pixels.                           |
| `frames_per_row`| `4`     | How many frames are arranged horizontally in the sprite sheet.           |
| `frame_wait`    | `0.08`  | The duration (in seconds) each frame is displayed before advancing.      |
| `loop`          | `0`     | `0` indicates that this animation does not loop and will play once.      |
| `next_animation`| `fireball` | The animation to transition to after this one completes.                 |
| `pos_x`         | `0`     | The X-coordinate of the top-left corner of the animation frames in the sprite sheet. |
| `pos_y`         | `26`    | The Y-coordinate of the top-left corner of the animation frames in the sprite sheet. |