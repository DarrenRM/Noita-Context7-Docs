---
title: Drone Launcher Sprite
category: items_gfx
---

# Drone Launcher Sprite

This document details the sprite information for the Drone Launcher item in Noita.

## Sprite Attributes

The `<Sprite>` tag defines the visual representation of the item.

| Attribute     | Value   | Description                                     |
|---------------|---------|-------------------------------------------------|
| `filename`    | `data/items_gfx/dronelauncher.png` | Path to the sprite image file.                  |
| `offset_x`    | `6`     | X-axis offset for the sprite.                   |
| `offset_y`    | `3`     | Y-axis offset for the sprite.                   |
| `scale_x`     | `1`     | X-axis scaling factor.                          |
| `scale_y`     | `1`     | Y-axis scaling factor.                          |
| `color_r`     | `1`     | Red color channel multiplier (1 = full red).    |
| `color_g`     | `1`     | Green color channel multiplier (1 = full green).|
| `color_b`     | `1`     | Blue color channel multiplier (1 = full blue).  |
| `color_a`     | `1`     | Alpha (transparency) multiplier (1 = opaque).   |

## RectAnimation Attributes

The `<RectAnimation>` tag defines how the sprite is animated.

| Attribute         | Value   | Description                                       |
|-------------------|---------|---------------------------------------------------|
| `name`            | `default` | The name of this animation state.                 |
| `frame_count`     | `1`     | Total number of frames in the animation.          |
| `frame_width`     | `13`    | Width of each individual frame in pixels.         |
| `frame_height`    | `7`     | Height of each individual frame in pixels.        |
| `frame_wait`      | `0.2`   | Time in seconds to wait between frames.           |
| `frames_per_row`  | `10`    | Number of frames arranged horizontally in the sprite sheet. |
| `loop`            | `0`     | Whether the animation should loop (0 = no, 1 = yes). |
| `offset_x`        | `3`     | X-axis offset for the animation frame.            |
| `offset_y`        | `4`     | Y-axis offset for the animation frame.            |
| `shrink_by_one_pixel` | `1` | Whether to shrink the frame by one pixel.       |