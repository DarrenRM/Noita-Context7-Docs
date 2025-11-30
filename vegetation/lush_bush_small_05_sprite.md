---
title: Lush Bush Small 05 Sprite
category: vegetation
---

# Lush Bush Small 05 Sprite

This documentation describes the sprite definition for `lush_bush_small_05.xml`, a small, lush bush entity in Noita.

## Sprite Definition

The primary sprite for this entity is defined by the `<Sprite>` tag.

### Key Attributes

| Attribute     | Value                               | Description                                                                 |
|---------------|-------------------------------------|-----------------------------------------------------------------------------|
| `filename`    | `data/vegetation/lush_bush_05.png`  | The image file used for the sprite.                                         |
| `offset_x`    | `16`                                | Horizontal offset of the sprite's origin.                                   |
| `offset_y`    | `30`                                | Vertical offset of the sprite's origin.                                     |
| `default_animation` | `vegetation_growth`             | The animation to play by default when the entity is spawned.                |

## Animation Definition

The `vegetation_growth` animation is a special type that signifies a growing vegetation entity.

### Key Attributes

| Attribute        | Value   | Description                                                                                             |
|------------------|---------|---------------------------------------------------------------------------------------------------------|
| `name`           | `vegetation_growth` | The name of the animation. This is crucial for the "growing vegetation" behavior.                       |
| `pos_x`          | `0`     | X-coordinate of the animation's starting position within the sprite sheet.                              |
| `pos_y`          | `0`     | Y-coordinate of the animation's starting position within the sprite sheet.                              |
| `frame_count`    | `1`     | The total number of frames in the animation.                                                            |
| `frame_width`    | `32`    | The width of each individual frame in pixels.                                                           |
| `frame_height`   | `32`    | The height of each individual frame in pixels.                                                          |
| `frame_wait`     | `1.0`   | The duration (in seconds) each frame is displayed before advancing to the next.                           |
| `frames_per_row` | `1`     | The number of frames arranged horizontally in a single row of the sprite sheet.                         |
| `loop`           | `1`     | Indicates whether the animation should loop (1 for true, 0 for false). In this case, it loops.         |