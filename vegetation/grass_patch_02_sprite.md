---
title: Grass Patch 02 Sprite
category: data/vegetation
---

# Grass Patch 02 Sprite

This document describes the sprite and animation data for `grass_patch_02.xml`, a vegetation asset in Noita.

## Sprite

The primary sprite for this asset is defined by the `<Sprite>` tag.

### Key Attributes

| Attribute   | Value                               | Description                                                                 |
| :---------- | :---------------------------------- | :-------------------------------------------------------------------------- |
| `filename`  | `data/vegetation/grass_patch_02.png` | The image file used for the sprite.                                         |
| `offset_x`  | `10`                                | Horizontal offset of the sprite's origin.                                   |
| `offset_y`  | `9`                                 | Vertical offset of the sprite's origin.                                     |
| `default_animation` | `vegetation_growth`             | The animation to play by default when this sprite is used.                |

## Animation: `vegetation_growth`

This sprite utilizes a special animation named `vegetation_growth`, which is designed to create a growing vegetation effect.

### Key Attributes

| Attribute       | Value | Description                                                              |
| :-------------- | :---- | :----------------------------------------------------------------------- |
| `name`          | `vegetation_growth` | The name of the animation.                                               |
| `pos_x`         | `0`   | Starting X position of the animation frame within the sprite sheet.        |
| `pos_y`         | `0`   | Starting Y position of the animation frame within the sprite sheet.        |
| `frame_count`   | `1`   | The total number of frames in the animation.                             |
| `frame_width`   | `20`  | The width of each individual animation frame.                            |
| `frame_height`  | `10`  | The height of each individual animation frame.                           |
| `frame_wait`    | `1.0` | The duration (in seconds) to wait before displaying the next frame.      |
| `frames_per_row`| `1`   | The number of frames arranged horizontally in the sprite sheet.          |
| `loop`          | `1`   | Indicates if the animation should loop (1 for true, 0 for false).        |