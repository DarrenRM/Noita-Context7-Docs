---
title: Big Green Smoke Cloud Particle
category: particles
---

---

# Big Green Smoke Cloud Particle

This document describes the configuration for a "Big Green Smoke Cloud" particle effect in Noita, intended for AI-assisted modding.

## Sprite Configuration

The particle uses a sprite sheet for its animation.

### Sprite Attributes

| Attribute      | Value                               | Description                                                                 |
|----------------|-------------------------------------|-----------------------------------------------------------------------------|
| `default_animation` | `explosion`                         | Specifies the default animation to play.                                    |
| `filename`     | `data/particles/smoke_cloud_big_green.png` | Path to the sprite sheet image file.                                        |
| `offset_x`     | `12`                                | Horizontal offset for the sprite.                                           |
| `offset_y`     | `12`                                | Vertical offset for the sprite.                                             |

## Animation Details

The `explosion` animation defines how the sprite sheet is used to create the visual effect.

### RectAnimation Attributes

| Attribute         | Value   | Description                                                                                             |
|-------------------|---------|---------------------------------------------------------------------------------------------------------|
| `name`            | `explosion` | The name of this animation, referenced by `default_animation`.                                          |
| `frame_count`     | `12`    | The total number of frames in the animation.                                                            |
| `frame_width`     | `25`    | The width of each individual frame in pixels.                                                           |
| `frame_height`    | `25`    | The height of each individual frame in pixels.                                                          |
| `frames_per_row`  | `12`    | The number of frames arranged horizontally in the sprite sheet.                                         |
| `frame_wait`      | `0.045` | The duration (in seconds) each frame is displayed before advancing to the next.                           |
| `loop`            | `0`     | Determines if the animation should loop. `0` means it does not loop (plays once).                       |
| `pos_x`           | `0`     | The starting X position of the animation frames within the sprite sheet (usually 0 for full sheet use). |
| `pos_y`           | `1`     | The starting Y position of the animation frames within the sprite sheet (usually 0 for full sheet use). |
| `shrink_by_one_pixel` | `1` | Indicates if each frame should shrink by one pixel after each animation cycle (often used for fading effects). |