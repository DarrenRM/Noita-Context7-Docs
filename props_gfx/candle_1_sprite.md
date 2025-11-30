---
title: Candle 1 Sprite
category: props_gfx
---

# Candle 1 Sprite

This document describes the sprite data for `candle_1.xml`, a graphical asset for Noita.

## Sprite Definition

The main `<Sprite>` element defines the visual properties and animations for the candle.

### Key Attributes

| Attribute      | Description                                     |
|----------------|-------------------------------------------------|
| `filename`     | Path to the sprite image file.                  |
| `offset_x`     | Horizontal offset for the sprite's origin.      |
| `offset_y`     | Vertical offset for the sprite's origin.        |
| `default_animation` | The animation to play by default.             |

## Animations

The sprite includes definitions for different animations.

### `stand` Animation

This animation likely represents the candle in its normal, lit state.

| Attribute       | Description                                     |
|-----------------|-------------------------------------------------|
| `name`          | The name of the animation.                      |
| `pos_x`         | X-coordinate of the animation's starting frame. |
| `pos_y`         | Y-coordinate of the animation's starting frame. |
| `frame_count`   | Total number of frames in the animation.        |
| `frame_width`   | Width of each individual frame.                 |
| `frame_height`  | Height of each individual frame.                |
| `frame_wait`    | Time in seconds to wait between frames.         |
| `frames_per_row`| Number of frames arranged horizontally in the sprite sheet. |
| `loop`          | Whether the animation should loop (1 for yes, 0 for no). |

### `out` Animation

This animation likely represents the candle when it is extinguished.

| Attribute       | Description                                     |
|-----------------|-------------------------------------------------|
| `name`          | The name of the animation.                      |
| `pos_x`         | X-coordinate of the animation's starting frame. |
| `pos_y`         | Y-coordinate of the animation's starting frame. |
| `frame_count`   | Total number of frames in the animation.        |
| `frame_width`   | Width of each individual frame.                 |
| `frame_height`  | Height of each individual frame.                |
| `frame_wait`    | Time in seconds to wait between frames.         |
| `frames_per_row`| Number of frames arranged horizontally in the sprite sheet. |
| `loop`          | Whether the animation should loop (1 for yes, 0 for no). |