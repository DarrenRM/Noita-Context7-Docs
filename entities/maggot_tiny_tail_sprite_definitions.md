---
title: Maggot Tiny Tail Sprite Definitions
category: entities
---

# Maggot Tiny Tail Sprite Definitions

This document details the sprite definitions for the "Maggot Tiny Tail" enemy in Noita, as found in `maggot_tiny_tail.xml`. It focuses on the visual representation and animation frames used for this entity.

## Sprite Attributes

The primary `<Sprite>` tag defines the base image and default animation.

| Attribute   | Value                               | Description                                                                 |
| :---------- | :---------------------------------- | :-------------------------------------------------------------------------- |
| `filename`  | `data/enemies_gfx/maggot_tiny_tail.png` | The path to the sprite image file.                                          |
| `offset_x`  | `72`                                | Horizontal offset for the sprite's origin.                                  |
| `offset_y`  | `48`                                | Vertical offset for the sprite's origin.                                    |
| `default_animation` | `stand`                             | The animation to play by default when the entity is idle.                   |

## Animation Definitions

The `<RectAnimation>` tags define specific animations for the entity. Each animation is composed of frames from the sprite sheet.

### `stand` Animation

This animation represents the entity in a standing or idle state.

| Attribute       | Value   | Description                                                              |
| :-------------- | :------ | :----------------------------------------------------------------------- |
| `name`          | `stand` | The name of this animation.                                              |
| `frame_count`   | `1`     | The total number of frames in this animation.                            |
| `frame_width`   | `96`    | The width of each individual frame in pixels.                            |
| `frame_height`  | `96`    | The height of each individual frame in pixels.                           |
| `frames_per_row`| `4`     | The number of frames arranged horizontally on the sprite sheet.          |
| `frame_wait`    | `0.082` | The duration in seconds each frame is displayed before transitioning.    |
| `pos_x`         | `0`     | The X-coordinate of the top-left corner of the animation frames on the sheet. |
| `pos_y`         | `0`     | The Y-coordinate of the top-left corner of the animation frames on the sheet. |

### `eat` Animation

This animation represents the entity performing an eating action.

| Attribute       | Value   | Description                                                              |
| :-------------- | :------ | :----------------------------------------------------------------------- |
| `name`          | `eat`   | The name of this animation.                                              |
| `frame_count`   | `1`     | The total number of frames in this animation.                            |
| `frame_width`   | `96`    | The width of each individual frame in pixels.                            |
| `frame_height`  | `96`    | The height of each individual frame in pixels.                           |
| `frames_per_row`| `4`     | The number of frames arranged horizontally on the sprite sheet.          |
| `frame_wait`    | `0.082` | The duration in seconds each frame is displayed before transitioning.    |
| `pos_x`         | `0`     | The X-coordinate of the top-left corner of the animation frames on the sheet. |
| `pos_y`         | `0`     | The Y-coordinate of the top-left corner of the animation frames on the sheet. |

**Note:** Both `stand` and `eat` animations currently use a single frame and share identical frame dimensions and timing. This suggests that the visual distinction between these animations might be minimal or handled by other game logic.