---
title: Endworm Middle Sprite
category: entities/enemies_gfx
---

# Endworm Middle Sprite

This document describes the sprite definition for the middle segment of the Endworm enemy in Noita.

## Sprite Definition

The `<Sprite>` tag defines the visual representation of the enemy segment.

### Key Attributes

| Attribute     | Description                                     |
|---------------|-------------------------------------------------|
| `filename`    | Path to the sprite image file.                  |
| `offset_x`    | Horizontal offset for sprite positioning.       |
| `offset_y`    | Vertical offset for sprite positioning.         |
| `default_animation` | The animation to play by default.           |

## Animations

The `<RectAnimation>` tags define the different animations available for this sprite.

### `stand` Animation

This animation defines the default standing pose for the Endworm middle segment.

| Attribute       | Description                                     |
|-----------------|-------------------------------------------------|
| `name`          | The name of the animation.                      |
| `pos_x`         | Starting X position within the sprite sheet.    |
| `pos_y`         | Starting Y position within the sprite sheet.    |
| `frame_count`   | Total number of frames in the animation.        |
| `frame_width`   | Width of each individual frame.                 |
| `frame_height`  | Height of each individual frame.                |
| `frame_wait`    | Time in seconds between frames.                 |
| `frames_per_row`| Number of frames in a single row of the sheet.  |
| `loop`          | Whether the animation should loop (1 for yes).  |

### `eat` Animation

This animation defines the eating pose for the Endworm middle segment.

| Attribute       | Description                                     |
|-----------------|-------------------------------------------------|
| `name`          | The name of the animation.                      |
| `pos_x`         | Starting X position within the sprite sheet.    |
| `pos_y`         | Starting Y position within the sprite sheet.    |
| `frame_count`   | Total number of frames in the animation.        |
| `frame_width`   | Width of each individual frame.                 |
| `frame_height`  | Height of each individual frame.                |
| `frame_wait`    | Time in seconds between frames.                 |
| `frames_per_row`| Number of frames in a single row of the sheet.  |
| `loop`          | Whether the animation should loop (1 for yes).  |