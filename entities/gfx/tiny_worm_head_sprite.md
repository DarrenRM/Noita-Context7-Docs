---
title: Tiny Worm Head Sprite
category: entities/gfx
---

# Tiny Worm Head Sprite

This document describes the sprite data for the "tiny worm head" enemy in Noita.

## Sprite Definition

The primary sprite definition for the tiny worm head is provided by the `<Sprite>` tag.

### Key Attributes

| Attribute     | Description                                     |
|---------------|-------------------------------------------------|
| `filename`    | Path to the sprite image file.                  |
| `offset_x`    | Horizontal offset for the sprite's origin.      |
| `offset_y`    | Vertical offset for the sprite's origin.        |
| `default_animation` | The animation to play by default.             |

## Animations

The sprite supports multiple animations, defined by `<RectAnimation>` tags.

### `stand` Animation

This animation defines the default standing pose of the tiny worm head.

| Attribute       | Description                                     |
|-----------------|-------------------------------------------------|
| `name`          | The name of the animation.                      |
| `pos_x`         | X-coordinate of the animation's starting frame. |
| `pos_y`         | Y-coordinate of the animation's starting frame. |
| `frame_count`   | Total number of frames in the animation.        |
| `frame_width`   | Width of each individual frame.                 |
| `frame_height`  | Height of each individual frame.                |
| `frame_wait`    | Time in seconds to wait between frames.         |
| `frames_per_row`| Number of frames arranged horizontally.         |
| `loop`          | Whether the animation should loop (1 for yes).  |

### `eat` Animation

This animation defines the eating pose of the tiny worm head.

| Attribute       | Description                                     |
|-----------------|-------------------------------------------------|
| `name`          | The name of the animation.                      |
| `pos_x`         | X-coordinate of the animation's starting frame. |
| `pos_y`         | Y-coordinate of the animation's starting frame. |
| `frame_count`   | Total number of frames in the animation.        |
| `frame_width`   | Width of each individual frame.                 |
| `frame_height`  | Height of each individual frame.                |
| `frame_wait`    | Time in seconds to wait between frames.         |
| `frames_per_row`| Number of frames arranged horizontally.         |
| `loop`          | Whether the animation should loop (1 for yes).  |