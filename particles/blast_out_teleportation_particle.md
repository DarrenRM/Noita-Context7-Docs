---
title: Blast Out Teleportation Particle
category: particles
---

# Blast Out Teleportation Particle

This document describes the `blast_out_teleportation.xml` particle effect, used to visually represent a teleportation blast in Noita.

## Sprite

The primary visual component of the particle.

| Attribute     | Description                                                                 |
| :------------ | :-------------------------------------------------------------------------- |
| `filename`    | Path to the sprite sheet containing the particle's animation frames.        |
| `offset_x`    | Horizontal offset for the sprite's origin.                                  |
| `offset_y`    | Vertical offset for the sprite's origin.                                    |
| `default_animation` | The name of the animation to play by default.                             |
| `color_r`     | Red component of the particle's color tint (0.0 to 1.0).                    |
| `color_g`     | Green component of the particle's color tint (0.0 to 1.0).                  |
| `color_b`     | Blue component of the particle's color tint (0.0 to 1.0).                   |

### RectAnimation: `explosion`

Defines the rectangular animation sequence for the particle.

| Attribute       | Description                                                                 |
| :-------------- | :-------------------------------------------------------------------------- |
| `name`          | The identifier for this animation.                                          |
| `pos_x`         | X-coordinate of the top-left corner of the animation frames within the sprite sheet. |
| `pos_y`         | Y-coordinate of the top-left corner of the animation frames within the sprite sheet. |
| `frame_count`   | The total number of frames in the animation.                                |
| `frame_width`   | The width of each individual animation frame.                               |
| `frame_height`  | The height of each individual animation frame.                              |
| `frame_wait`    | The time in seconds to wait between each frame.                             |
| `frames_per_row`| The number of frames arranged horizontally in a single row of the sprite sheet. |
| `loop`          | Whether the animation should loop (1 for true, 0 for false).                |