---
title: Pink Muzzle Flash 03 Particle
category: particles
---

---

# Pink Muzzle Flash 03 Particle

This document describes the configuration for a pink muzzle flash particle effect in Noita, intended for AI-assisted modding.

## Sprite Configuration

This section details the visual representation of the particle.

### Sprite Attributes

| Attribute   | Value      | Description                                     |
| :---------- | :--------- | :---------------------------------------------- |
| `filename`  | `data/particles/muzzle_flashes/muzzle_pink_03.png` | Path to the sprite sheet for the particle.      |
| `offset_x`  | `8`        | Horizontal offset of the sprite.                |
| `offset_y`  | `7`        | Vertical offset of the sprite.                  |
| `default_animation` | `muzzle` | The name of the default animation to play.      |

## Animation Configuration

This section defines how the sprite animates.

### RectAnimation Attributes

| Attribute       | Value | Description                                     |
| :-------------- | :---- | :---------------------------------------------- |
| `name`          | `muzzle` | The name of this animation.                     |
| `pos_x`         | `0`   | Starting X position within the sprite sheet.    |
| `pos_y`         | `0`   | Starting Y position within the sprite sheet.    |
| `frame_count`   | `1`   | Total number of frames in the animation.        |
| `frame_width`   | `16`  | Width of each individual frame.                 |
| `frame_height`  | `16`  | Height of each individual frame.                |
| `frame_wait`    | `0.1` | Time in seconds to wait between frames.         |
| `frames_per_row`| `1`   | Number of frames in a single row of the sheet.  |
| `loop`          | `0`   | Whether the animation should loop (0 = no, 1 = yes). |