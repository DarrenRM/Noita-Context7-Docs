---
title: Bush Growth 6 Sprite
category: data/vegetation
---

# Bush Growth 6 Sprite

This document describes the sprite and animation data for `bush_growth_6.xml`, used for a growing bush entity in Noita.

## Sprite Definition

The primary sprite definition for this entity.

### Key Attributes

| Attribute     | Value                               | Description                                                                 |
| :------------ | :---------------------------------- | :-------------------------------------------------------------------------- |
| `filename`    | `data/vegetation/bush_growth_6.png` | Path to the sprite image file.                                              |
| `offset_x`    | `18`                                | Horizontal offset of the sprite from its origin.                            |
| `offset_y`    | `31`                                | Vertical offset of the sprite from its origin.                              |
| `default_animation` | `vegetation_growth`             | The name of the animation to play by default. This is a special name for growing vegetation. |

## Animation Definition

Defines the animation sequence for the growing bush.

### `vegetation_growth` Animation

This is a special animation name that triggers a growing vegetation effect.

#### Key Attributes

| Attribute       | Value   | Description                                                                 |
| :-------------- | :------ | :-------------------------------------------------------------------------- |
| `name`          | `vegetation_growth` | The name of the animation.                                                  |
| `pos_x`         | `0`     | X-coordinate of the animation's starting position within the sprite sheet.  |
| `pos_y`         | `0`     | Y-coordinate of the animation's starting position within the sprite sheet.  |
| `frame_count`   | `5`     | The total number of frames in the animation.                                |
| `frame_width`   | `32`    | The width of each individual frame in pixels.                               |
| `frame_height`  | `34`    | The height of each individual frame in pixels.                              |
| `frame_wait`    | `1.0`   | The duration (in seconds) each frame is displayed before advancing.         |
| `frames_per_row`| `6`     | The number of frames arranged horizontally in the sprite sheet.             |
| `loop`          | `1`     | Indicates if the animation should loop (1 for true, 0 for false).           |