---
title: Blue Vine Part 2 Entity
category: entities
---

---

# Blue Vine Part 2 Entity

This document describes the `vine_b_2.xml` entity, which represents a segment of a blue vine in Noita.

## Sprite Information

The entity uses a sprite to visually represent the vine segment.

### Sprite Attributes

| Attribute      | Value                                                              | Description                                     |
|----------------|--------------------------------------------------------------------|-------------------------------------------------|
| `filename`     | `data/entities/verlet_chains/vines/vine_parts_blue/vine_b.png`     | Path to the sprite image file.                  |
| `offset_x`     | `0`                                                                | Horizontal offset of the sprite.                |
| `offset_y`     | `0`                                                                | Vertical offset of the sprite.                  |
| `default_animation` | `stand`                                                            | The animation to play by default.               |

### Animation: `stand`

This animation defines the visual appearance of the vine segment.

| Attribute       | Value | Description                                      |
|-----------------|-------|--------------------------------------------------|
| `name`          | `stand` | The name of the animation.                       |
| `pos_x`         | `4`   | X-coordinate of the sprite frame's top-left corner. |
| `pos_y`         | `0`   | Y-coordinate of the sprite frame's top-left corner. |
| `frame_count`   | `1`   | The total number of frames in the animation.     |
| `frame_width`   | `4`   | The width of each animation frame.               |
| `frame_height`  | `3`   | The height of each animation frame.              |
| `frame_wait`    | `1`   | The duration (in frames) each frame is displayed. |
| `frames_per_row`| `8`   | The number of frames in a single row of the sprite sheet. |
| `loop`          | `1`   | Indicates if the animation should loop (1 for true, 0 for false). |