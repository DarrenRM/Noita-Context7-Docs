---
title: Skygazer Sprite Definitions
category: enemies_gfx
---

# Skygazer Sprite Definitions

This document details the sprite and animation definitions for the Skygazer enemy in Noita, intended for AI-assisted modding.

## Sprite Attributes

The main `<Sprite>` tag defines the base visual properties and the primary sprite sheet.

| Attribute      | Value                               | Description                                                                 |
|----------------|-------------------------------------|-----------------------------------------------------------------------------|
| `default_animation` | `stand`                             | The animation to play by default when the entity is spawned.                |
| `filename`     | `data/enemies_gfx/skygazer.png`     | The path to the sprite sheet image file.                                    |
| `offset_x`     | `16`                                | Horizontal offset for the sprite's origin.                                  |
| `offset_y`     | `22`                                | Vertical offset for the sprite's origin.                                    |

## Animation Definitions

The Skygazer utilizes several distinct animations, each defined by a `<RectAnimation>` tag. These animations are crucial for defining the visual states and actions of the enemy.

### `stand` Animation

| Attribute       | Value   | Description                                                                 |
|-----------------|---------|-----------------------------------------------------------------------------|
| `name`          | `stand` | The name of this animation.                                                 |
| `frame_count`   | `4`     | Total number of frames in this animation.                                   |
| `frame_width`   | `32`    | Width of each individual frame in pixels.                                   |
| `frame_height`  | `32`    | Height of each individual frame in pixels.                                  |
| `frames_per_row`| `4`     | Number of frames arranged horizontally in the sprite sheet.                 |
| `frame_wait`    | `0.16`  | Time in seconds to wait between each frame.                                 |
| `pos_x`         | `0`     | X-coordinate of the top-left corner of the animation frames in the sprite sheet. |
| `pos_y`         | `1`     | Y-coordinate of the top-left corner of the animation frames in the sprite sheet. |

### `fly` Animation

| Attribute       | Value   | Description                                                                 |
|-----------------|---------|-----------------------------------------------------------------------------|
| `name`          | `fly`   | The name of this animation.                                                 |
| `frame_count`   | `4`     | Total number of frames in this animation.                                   |
| `frame_width`   | `32`    | Width of each individual frame in pixels.                                   |
| `frame_height`  | `32`    | Height of each individual frame in pixels.                                  |
| `frames_per_row`| `4`     | Number of frames arranged horizontally in the sprite sheet.                 |
| `frame_wait`    | `0.16`  | Time in seconds to wait between each frame.                                 |
| `pos_x`         | `0`     | X-coordinate of the top-left corner of the animation frames in the sprite sheet. |
| `pos_y`         | `1`     | Y-coordinate of the top-left corner of the animation frames in the sprite sheet. |

### `fly_idle` Animation

| Attribute       | Value   | Description                                                                 |
|-----------------|---------|-----------------------------------------------------------------------------|
| `name`          | `fly_idle` | The name of this animation.                                                 |
| `frame_count`   | `4`     | Total number of frames in this animation.                                   |
| `frame_width`   | `32`    | Width of each individual frame in pixels.                                   |
| `frame_height`  | `32`    | Height of each individual frame in pixels.                                  |
| `frames_per_row`| `4`     | Number of frames arranged horizontally in the sprite sheet.                 |
| `frame_wait`    | `0.16`  | Time in seconds to wait between each frame.                                 |
| `pos_x`         | `0`     | X-coordinate of the top-left corner of the animation frames in the sprite sheet. |
| `pos_y`         | `1`     | Y-coordinate of the top-left corner of the animation frames in the sprite sheet. |

### `attack_ranged` Animation

This animation is specifically for the Skygazer's ranged attack.

| Attribute       | Value   | Description                                                                 |
|-----------------|---------|-----------------------------------------------------------------------------|
| `name`          | `attack_ranged` | The name of this animation.                                                 |
| `frame_count`   | `5`     | Total number of frames in this animation.                                   |
| `frame_width`   | `33`    | Width of each individual frame in pixels.                                   |
| `frame_height`  | `33`    | Height of each individual frame in pixels.                                  |
| `frames_per_row`| `5`     | Number of frames arranged horizontally in the sprite sheet.                 |
| `frame_wait`    | `0.1`   | Time in seconds to wait between each frame.                                 |
| `loop`          | `0`     | `0` indicates the animation does not loop.                                  |
| `pos_x`         | `0`     | X-coordinate of the top-left corner of the animation frames in the sprite sheet. |
| `pos_y`         | `34`    | Y-coordinate of the top-left corner of the animation frames in the sprite sheet. |
| `shrink_by_one_pixel` | `1` | This attribute is set to `1`, indicating a slight shrinking effect.         |

#### `attack_ranged` Events

Events within an animation define specific actions that occur at certain frames.

| Event Name     | Frame | Max Distance | On Finished | Probability | Description