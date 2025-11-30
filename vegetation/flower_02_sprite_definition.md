---
title: Flower 02 Sprite Definition
category: data/vegetation
---

---

# Flower 02 Sprite Definition

This document describes the sprite definition for `flower_02.xml`, a vegetation asset in Noita.

## Sprite Attributes

The primary `<Sprite>` element defines the visual representation and animation for the flower.

| Attribute     | Description                                                              |
|---------------|--------------------------------------------------------------------------|
| `filename`    | Path to the sprite image file (`data/vegetation/flower_02.png`).         |
| `offset_x`    | Horizontal offset for the sprite's origin.                               |
| `offset_y`    | Vertical offset for the sprite's origin.                                 |
| `default_animation` | The name of the animation to play by default (`vegetation_growth`). |

## RectAnimation: `vegetation_growth`

This section defines the `vegetation_growth` animation, which is a special type of animation used for growing vegetation.

| Attribute       | Description                                                                                             |
|-----------------|---------------------------------------------------------------------------------------------------------|
| `name`          | The name of the animation (`vegetation_growth`).                                                        |
| `pos_x`         | X-coordinate of the animation's starting position within the sprite sheet.                                |
| `pos_y`         | Y-coordinate of the animation's starting position within the sprite sheet.                                |
| `frame_count`   | The total number of frames in the animation.                                                            |
| `frame_width`   | The width of each individual frame.                                                                     |
| `frame_height`  | The height of each individual frame.                                                                    |
| `frame_wait`    | The duration (in seconds) each frame is displayed before transitioning to the next.                       |
| `frames_per_row`| The number of frames arranged horizontally in a single row of the sprite sheet.                         |
| `loop`          | Determines if the animation should loop (`1` for loop, `0` for no loop).                                |