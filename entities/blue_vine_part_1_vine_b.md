---
title: Blue Vine Part 1 (Vine B)
category: entities
---

# Blue Vine Part 1 (Vine B)

This entity defines a single segment of a blue vine, specifically the first part (vine_b_1). It utilizes a sprite and a simple animation to represent its visual appearance.

## Sprite

The sprite for this vine segment is located at `data/entities/verlet_chains/vines/vine_parts_blue/vine_b.png`.

### Key Sprite Attributes

| Attribute    | Value | Description                                     |
| :----------- | :---- | :---------------------------------------------- |
| `filename`   | Path  | Path to the sprite image file.                  |
| `offset_x`   | 0     | Horizontal offset of the sprite.                |
| `offset_y`   | 0     | Vertical offset of the sprite.                  |
| `default_animation` | `stand` | The animation to play by default.             |

## Animation

The entity uses a single animation named "stand" for its visual representation.

### Key Animation Attributes

| Attribute       | Value | Description                                                              |
| :-------------- | :---- | :----------------------------------------------------------------------- |
| `name`          | `stand` | The name of the animation.                                               |
| `pos_x`         | 0     | Starting X position of the animation frame within the sprite sheet.      |
| `pos_y`         | 0     | Starting Y position of the animation frame within the sprite sheet.      |
| `frame_count`   | 1     | The total number of frames in the animation.                             |
| `frame_width`   | 4     | The width of each individual animation frame in pixels.                  |
| `frame_height`  | 3     | The height of each individual animation frame in pixels.                 |
| `frame_wait`    | 1     | The duration (in game ticks) each frame is displayed before advancing.   |
| `frames_per_row`| 8     | The number of frames arranged horizontally in the sprite sheet.          |
| `loop`          | 1     | Indicates if the animation should loop (1 for true, 0 for false).        |