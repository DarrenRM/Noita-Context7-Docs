---
title: Large Electric Spark Particle
category: particles
---

---

# Large Electric Spark Particle

This document describes the configuration for a large electric spark particle effect in Noita, intended for AI-assisted modding.

## Sprite Configuration

The particle uses a sprite sheet for its visual representation.

### Sprite Attributes

| Attribute     | Value                               | Description                                                                 |
|---------------|-------------------------------------|-----------------------------------------------------------------------------|
| `filename`    | `data/particles/spark_electric_large.png` | Path to the sprite sheet image file.                                        |
| `offset_x`    | `8`                                 | Horizontal offset for the sprite's origin.                                  |
| `offset_y`    | `8`                                 | Vertical offset for the sprite's origin.                                    |
| `default_animation` | `explosion`                         | The name of the animation to play by default.                               |

## Animation: Explosion

This section details the "explosion" animation used by the spark particle.

### RectAnimation Attributes

| Attribute       | Value   | Description                                                                                             |
|-----------------|---------|---------------------------------------------------------------------------------------------------------|
| `name`          | `explosion` | The identifier for this animation.                                                                      |
| `pos_x`         | `0`     | Starting X position of the animation frames within the sprite sheet.                                    |
| `pos_y`         | `0`     | Starting Y position of the animation frames within the sprite sheet.                                    |
| `frame_count`   | `8`     | The total number of frames in this animation.                                                           |
| `frame_width`   | `16`    | The width of each individual frame in pixels.                                                           |
| `frame_height`  | `16`    | The height of each individual frame in pixels.                                                          |
| `frame_wait`    | `0.04`  | The duration (in seconds) each frame is displayed before transitioning to the next.                       |
| `frames_per_row`| `6`     | The number of frames arranged horizontally in the sprite sheet.                                         |
| `loop`          | `0`     | Indicates if the animation should loop. `0` means it does not loop (plays once).                        |