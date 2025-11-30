---
title: Explosion Particle 032
category: particles
---

---

# Explosion Particle 032

This document describes the configuration for a specific explosion particle effect in Noita, identified as `explosion_032`.

## Sprite Configuration

The primary visual representation of this particle is defined by a sprite.

### Key Sprite Attributes

| Attribute      | Value     | Description                                     |
|----------------|-----------|-------------------------------------------------|
| `filename`     | `data/particles/explosion_032.png` | Path to the sprite image file.                  |
| `offset_x`     | `16`      | Horizontal offset for the sprite's origin.      |
| `offset_y`     | `16`      | Vertical offset for the sprite's origin.        |
| `default_animation` | `explosion` | The name of the default animation to play.      |

## Animation Configuration

The sprite is animated to create the visual effect of an explosion.

### Key Animation Attributes (`explosion`)

| Attribute       | Value    | Description                                       |
|-----------------|----------|---------------------------------------------------|
| `name`          | `explosion` | The identifier for this animation.                |
| `pos_x`         | `0`      | Starting X position within the sprite sheet.      |
| `pos_y`         | `0`      | Starting Y position within the sprite sheet.      |
| `frame_count`   | `9`      | Total number of frames in the animation.          |
| `frame_width`   | `32`     | Width of each individual frame.                   |
| `frame_height`  | `32`     | Height of each individual frame.                  |
| `frame_wait`    | `0.021`  | Time in seconds to wait between frames.           |
| `frames_per_row`| `9`      | Number of frames arranged horizontally in the sheet.|
| `loop`          | `0`      | Whether the animation should loop (0 = no loop).  |