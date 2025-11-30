---
title: Big Pink Orb Out Particle
category: particles
---

# Big Pink Orb Out Particle

This document describes the configuration for the "Big Pink Orb Out" particle effect in Noita, used for visual feedback during gameplay.

## Sprite Configuration

The primary visual component of this particle is a sprite.

### Sprite Attributes

| Attribute     | Description                                     | Value        |
|---------------|-------------------------------------------------|--------------|
| `filename`    | Path to the sprite image file.                  | `data/particles/orb_pink_big_out.png` |
| `offset_x`    | Horizontal offset for the sprite's origin.      | `8`          |
| `offset_y`    | Vertical offset for the sprite's origin.        | `8`          |
| `default_animation` | The name of the animation to play by default. | `explosion`  |

## Animation: Explosion

This particle utilizes a `RectAnimation` to define its visual sequence.

### RectAnimation Attributes

| Attribute       | Description                                     | Value   |
|-----------------|-------------------------------------------------|---------|
| `name`          | The identifier for this animation.              | `explosion` |
| `pos_x`         | Starting X position within the sprite sheet.    | `0`     |
| `pos_y`         | Starting Y position within the sprite sheet.    | `0`     |
| `frame_count`   | Total number of frames in the animation.        | `10`    |
| `frame_width`   | Width of each individual frame.                 | `16`    |
| `frame_height`  | Height of each individual frame.                | `16`    |
| `frame_wait`    | Time in seconds to wait between frames.         | `0.025` |
| `frames_per_row`| Number of frames arranged horizontally in the sprite sheet. | `10`    |
| `loop`          | Whether the animation should loop (0 = no, 1 = yes). | `0`     |