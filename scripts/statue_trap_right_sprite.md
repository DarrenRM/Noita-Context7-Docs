---
title: Statue Trap Right Sprite
category: data/buildings_gfx
---

---

# Statue Trap Right Sprite

This document describes the sprite data for the `statue_trap_right` building graphic in Noita.

## Sprite Attributes

The primary `<Sprite>` element defines the visual asset and its positioning.

| Attribute   | Description                                     |
| :---------- | :---------------------------------------------- |
| `filename`  | Path to the sprite image file.                  |
| `offset_x`  | Horizontal offset for sprite placement.         |
| `offset_y`  | Vertical offset for sprite placement.           |
| `default_animation` | The name of the default animation to play. |

## Animation Data

The `<RectAnimation>` element defines the animation sequence for the sprite.

| Attribute        | Description                                                              |
| :--------------- | :----------------------------------------------------------------------- |
| `name`           | The name of this animation (referenced by `default_animation`).          |
| `pos_x`          | Starting X position of the animation frame within the sprite sheet.      |
| `pos_y`          | Starting Y position of the animation frame within the sprite sheet.      |
| `frame_count`    | The total number of frames in the animation.                             |
| `frame_width`    | The width of each individual animation frame.                            |
| `frame_height`   | The height of each individual animation frame.                           |
| `frame_wait`     | The duration (in seconds) each frame is displayed before advancing.      |
| `frames_per_row` | The number of frames arranged horizontally in the sprite sheet.          |
| `loop`           | Whether the animation should loop (`1` for true, `0` for false).         |