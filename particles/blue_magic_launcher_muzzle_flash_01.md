---
title: Blue Magic Launcher Muzzle Flash 01
category: particles
---

---

# Blue Magic Launcher Muzzle Flash 01

This documentation describes the particle effect for a blue magic launcher's muzzle flash.

## Sprite

The primary visual component of the muzzle flash.

| Attribute   | Value                                         | Description                                                                 |
| :---------- | :-------------------------------------------- | :-------------------------------------------------------------------------- |
| `filename`  | `data/particles/muzzle_flashes/muzzle_magic_launcher_blue_01.png` | Path to the sprite sheet containing the animation frames.                   |
| `offset_x`  | `8`                                           | Horizontal offset of the sprite from its origin.                            |
| `offset_y`  | `7`                                           | Vertical offset of the sprite from its origin.                              |
| `default_animation` | `muzzle`                                      | The name of the animation to play by default.                               |

## RectAnimation

Defines the animation sequence for the sprite.

| Attribute       | Value | Description                                                                 |
| :-------------- | :---- | :-------------------------------------------------------------------------- |
| `name`          | `muzzle` | The name of this animation, referenced by the `Sprite` element.             |
| `pos_x`         | `0`   | Starting X position of the animation frame within the sprite sheet.         |
| `pos_y`         | `0`   | Starting Y position of the animation frame within the sprite sheet.         |
| `frame_count`   | `1`   | The total number of frames in the animation.                                |
| `frame_width`   | `16`  | The width of each individual animation frame.                               |
| `frame_height`  | `16`  | The height of each individual animation frame.                              |
| `frame_wait`    | `0.1` | The duration (in seconds) each frame is displayed before advancing.         |
| `frames_per_row`| `1`   | The number of frames arranged horizontally in a single row of the sprite sheet. |
| `loop`          | `0`   | Determines if the animation should loop. `0` means it does not loop.        |