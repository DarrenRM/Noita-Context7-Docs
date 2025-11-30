---
title: Dark Blue Vine Part B
category: entities
---

# Dark Blue Vine Part B

This document describes the `vine_dark_b_2.xml` entity, which represents a segment of a dark blue vine.

## Sprite Information

The entity uses a sprite for its visual representation.

### Sprite Attributes

| Attribute     | Value                                                              | Description                                      |
|---------------|--------------------------------------------------------------------|--------------------------------------------------|
| `filename`    | `data/entities/verlet_chains/vines/vine_parts_blue/vine_dark_b.png` | Path to the sprite image file.                   |
| `offset_x`    | `0`                                                                | Horizontal offset of the sprite.                 |
| `offset_y`    | `0`                                                                | Vertical offset of the sprite.                   |
| `default_animation` | `stand`                                                            | The animation to play by default.                |

### Animation: `stand`

This animation defines the visual state of the vine part.

| Attribute       | Value | Description                                    |
|-----------------|-------|------------------------------------------------|
| `name`          | `stand` | The name of the animation.                     |
| `pos_x`         | `4`   | X-coordinate of the animation's starting frame. |
| `pos_y`         | `0`   | Y-coordinate of the animation's starting frame. |
| `frame_count`   | `1`   | The total number of frames in the animation.   |
| `frame_width`   | `4`   | The width of each animation frame.             |
| `frame_height`  | `3`   | The height of each animation frame.            |
| `frame_wait`    | `1`   | The duration each frame is displayed.          |
| `frames_per_row`| `8`   | The number of frames in a single row of the sprite sheet. |
| `loop`          | `1`   | Whether the animation should loop (1 for true). |