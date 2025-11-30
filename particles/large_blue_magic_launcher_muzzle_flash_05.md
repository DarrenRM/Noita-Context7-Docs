---
title: Large Blue Magic Launcher Muzzle Flash 05
category: particles
---

# Large Blue Magic Launcher Muzzle Flash 05

This particle effect defines a muzzle flash for a large blue magic launcher. It's a simple, single-frame animation.

## Sprite

The primary visual component of the muzzle flash.

| Attribute   | Value                                                | Description                                                                 |
| :---------- | :--------------------------------------------------- | :-------------------------------------------------------------------------- |
| `filename`  | `data/particles/muzzle_flashes/muzzle_magic_launcher_large_blue_05.png` | The image file used for the sprite.                                         |
| `offset_x`  | `8`                                                  | Horizontal offset of the sprite's origin.                                   |
| `offset_y`  | `7`                                                  | Vertical offset of the sprite's origin.                                     |
| `default_animation` | `muzzle`                                             | The name of the animation to play by default.                               |

## RectAnimation

Defines the animation sequence for the sprite.

| Attribute       | Value | Description                                                                 |
| :-------------- | :---- | :-------------------------------------------------------------------------- |
| `name`          | `muzzle` | The name of this animation, referenced by the `Sprite`'s `default_animation`. |
| `pos_x`         | `0`   | X-coordinate of the animation's starting position within the sprite sheet.  |
| `pos_y`         | `0`   | Y-coordinate of the animation's starting position within the sprite sheet.  |
| `frame_count`   | `1`   | The total number of frames in the animation.                                |
| `frame_width`   | `16`  | The width of each individual frame in pixels.                               |
| `frame_height`  | `16`  | The height of each individual frame in pixels.                              |
| `frame_wait`    | `0.1` | The duration (in seconds) each frame is displayed before advancing.         |
| `frames_per_row`| `1`   | The number of frames arranged horizontally in the sprite sheet.             |
| `loop`          | `0`   | Determines if the animation should loop (`1` for loop, `0` for no loop).    |