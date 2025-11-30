---
title: Endworm Tail Sprite
category: enemies_gfx
---

# Endworm Tail Sprite

This document describes the sprite data for the Endworm's tail in Noita.

## Sprite Attributes

The primary `Sprite` element defines the visual representation and animation properties.

| Attribute      | Value                               | Description                                                                 |
|----------------|-------------------------------------|-----------------------------------------------------------------------------|
| `filename`     | `data/enemies_gfx/endworm_tail.png` | Path to the sprite image file.                                              |
| `offset_x`     | `16`                                | Horizontal offset for the sprite's origin.                                  |
| `offset_y`     | `16`                                | Vertical offset for the sprite's origin.                                    |
| `default_animation` | `stand`                             | The animation to play by default when the sprite is first loaded.           |

## Animations

The sprite utilizes `RectAnimation` elements to define different animation states.

### `stand` Animation

This animation defines the default standing pose for the endworm tail.

| Attribute       | Value   | Description                                                                 |
|-----------------|---------|-----------------------------------------------------------------------------|
| `name`          | `stand` | The name of this animation state.                                           |
| `pos_x`         | `0`     | Starting X-coordinate within the sprite sheet for this animation.           |
| `pos_y`         | `0`     | Starting Y-coordinate within the sprite sheet for this animation.           |
| `frame_count`   | `1`     | The total number of frames in this animation.                               |
| `frame_width`   | `32`    | The width of each individual frame in pixels.                               |
| `frame_height`  | `32`    | The height of each individual frame in pixels.                              |
| `frame_wait`    | `0.082` | The duration (in seconds) each frame is displayed before advancing.         |
| `frames_per_row`| `1`     | The number of frames arranged horizontally in the sprite sheet.             |
| `loop`          | `1`     | Indicates if the animation should loop (1 for true, 0 for false).           |

### `eat` Animation

This animation defines the eating pose for the endworm tail.

| Attribute       | Value   | Description                                                                 |
|-----------------|---------|-----------------------------------------------------------------------------|
| `name`          | `eat`   | The name of this animation state.                                           |
| `pos_x`         | `0`     | Starting X-coordinate within the sprite sheet for this animation.           |
| `pos_y`         | `0`     | Starting Y-coordinate within the sprite sheet for this animation.           |
| `frame_count`   | `1`     | The total number of frames in this animation.                               |
| `frame_width`   | `32`    | The width of each individual frame in pixels.                               |
| `frame_height`  | `32`    | The height of each individual frame in pixels.                              |
| `frame_wait`    | `0.082` | The duration (in seconds) each frame is displayed before advancing.         |
| `frames_per_row`| `1`     | The number of frames arranged horizontally in the sprite sheet.             |
| `loop`          | `1`     | Indicates if the animation should loop (1 for true, 0 for false).           |