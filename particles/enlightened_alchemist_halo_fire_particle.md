---
title: Enlightened Alchemist Halo Fire Particle
category: particles
---

---

# Enlightened Alchemist Halo Fire Particle

This document describes the particle effect for the "Enlightened Alchemist Halo Fire".

## Sprite Information

The particle uses a sprite sheet for its visual representation.

### Sprite Attributes

| Attribute      | Value                                     | Description                                     |
|----------------|-------------------------------------------|-------------------------------------------------|
| `filename`     | `data/particles/enlightened_alchemist_halo_fire.png` | Path to the sprite image file.                  |
| `offset_x`     | `21`                                      | Horizontal offset of the sprite.                |
| `offset_y`     | `44`                                      | Vertical offset of the sprite.                  |
| `default_animation` | `stand`                                   | The animation to play by default.               |

### Animation: `stand`

This defines the animation sequence for the particle.

| Attribute       | Value | Description                                     |
|-----------------|-------|-------------------------------------------------|
| `name`          | `stand` | The name of this animation.                     |
| `pos_x`         | `0`   | Starting X position within the sprite sheet.    |
| `pos_y`         | `0`   | Starting Y position within the sprite sheet.    |
| `frame_count`   | `1`   | Total number of frames in the animation.        |
| `frame_width`   | `42`  | Width of each individual frame.                 |
| `frame_height`  | `38`  | Height of each individual frame.                |
| `frame_wait`    | `0.04`| Time in seconds to wait between frames.         |
| `frames_per_row`| `1`   | Number of frames arranged horizontally in the sheet. |
| `loop`          | `1`   | Whether the animation should loop (1 for true). |