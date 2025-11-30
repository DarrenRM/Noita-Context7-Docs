---
title: Orb Big Sprite
category: entities
---

---

# Orb Big Sprite

This document describes the sprite configuration for the "Orb Big" entity in Noita, commonly associated with boss fish.

## Sprite Attributes

The `<Sprite>` element defines the visual representation of the entity.

| Attribute     | Description                                     |
|---------------|-------------------------------------------------|
| `filename`    | Path to the sprite image file.                  |
| `offset_x`    | Horizontal offset for the sprite's origin.      |
| `offset_y`    | Vertical offset for the sprite's origin.        |
| `default_animation` | The name of the animation to play by default. |

## Animation Details

The `<RectAnimation>` element specifies how the sprite animates.

| Attribute        | Description                                                              |
|------------------|--------------------------------------------------------------------------|
| `name`           | The name of this animation (referenced by `default_animation`).          |
| `pos_x`          | Starting X position within the sprite sheet for the animation.           |
| `pos_y`          | Starting Y position within the sprite sheet for the animation.           |
| `frame_count`    | The total number of frames in the animation.                             |
| `frame_width`    | The width of each individual frame.                                      |
| `frame_height`   | The height of each individual frame.                                     |
| `frame_wait`     | The duration (in seconds) each frame is displayed before advancing.      |
| `frames_per_row` | The number of frames arranged horizontally in the sprite sheet.          |
| `loop`           | Whether the animation should loop (1 for true, 0 for false).             |