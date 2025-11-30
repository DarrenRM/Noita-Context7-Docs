---
title: Enemy Sprite Definition - Body Old Test
category: data/enemies_gfx
---

# Enemy Sprite Definition - Body Old Test

This document describes the sprite definition for an enemy, likely an older or test version of a "body" enemy. It outlines the visual assets and animations used for this entity.

## Sprite Attributes

The main `<Sprite>` tag defines the base visual properties of the enemy.

| Attribute     | Value        | Description                                                                 |
|---------------|--------------|-----------------------------------------------------------------------------|
| `filename`    | `data/enemies_gfx/body_old` | The base filename for the sprite texture.                                   |
| `offset_x`    | `48`         | Horizontal offset for the sprite's origin.                                  |
| `offset_y`    | `48`         | Vertical offset for the sprite's origin.                                    |
| `default_animation` | `stand`      | The animation to play by default when the enemy is idle.                    |

## Animations

The `<Sprite>` tag contains multiple `<RectAnimation>` tags, each defining a specific animation sequence.

### `stand` Animation

This animation represents the enemy's idle or standing state.

| Attribute       | Value   | Description                                                                 |
|-----------------|---------|-----------------------------------------------------------------------------|
| `name`          | `stand` | The name of this animation.                                                 |
| `pos_x`         | `0`     | X-coordinate of the top-left corner of the animation frames within the sprite sheet. |
| `pos_y`         | `0`     | Y-coordinate of the top-left corner of the animation frames within the sprite sheet. |
| `frame_count`   | `4`     | The total number of frames in this animation.                               |
| `frame_width`   | `96`    | The width of each individual frame.                                         |
| `frame_height`  | `102`   | The height of each individual frame.                                        |
| `frame_wait`    | `0.12`  | The duration (in seconds) each frame is displayed before transitioning.     |
| `frames_per_row`| `4`     | The number of frames arranged horizontally in the sprite sheet for this animation. |
| `loop`          | `1`     | Indicates if the animation should loop (1 for true, 0 for false).           |

### `open` Animation

This animation likely represents the enemy opening up or preparing to attack.

| Attribute       | Value   | Description                                                                 |
|-----------------|---------|-----------------------------------------------------------------------------|
| `name`          | `open`  | The name of this animation.                                                 |
| `pos_x`         | `0`     | X-coordinate of the top-left corner of the animation frames.                |
| `pos_y`         | `102`   | Y-coordinate of the top-left corner of the animation frames.                |
| `frame_count`   | `7`     | The total number of frames in this animation.                               |
| `frame_width`   | `96`    | The width of each individual frame.                                         |
| `frame_height`  | `102`   | The height of each individual frame.                                        |
| `frame_wait`    | `0.09`  | The duration (in seconds) each frame is displayed.                          |
| `frames_per_row`| `7`     | The number of frames arranged horizontally in the sprite sheet.             |
| `next_animation`| `opened`| The animation to transition to after this one completes.                    |
| `loop`          | `0`     | Indicates if the animation should loop (0 for false).                       |

### `close` Animation

This animation likely represents the enemy closing up after an action.

| Attribute       | Value   | Description                                                                 |
|-----------------|---------|-----------------------------------------------------------------------------|
| `name`          | `close` | The name of this animation.                                                 |
| `pos_x`         | `0`     | X-coordinate of the top-left corner of the animation frames.                |
| `pos_y`         | `306`   | Y-coordinate of the top-left corner of the animation frames.                |
| `frame_count`   | `7`     | The total number of frames in this animation.                               |
| `frame_width`   | `96`    | The width of each individual frame.                                         |
| `frame_height`  | `102`   | The height of each individual frame.                                        |
| `frame_wait`    | `0.09`  | The duration (in seconds) each frame is displayed.                          |
| `frames_per_row`| `7`     | The number of frames arranged horizontally in the sprite sheet.             |
| `next_animation`| `stand` | The animation to transition to after this one completes.                    |
| `loop`          | `0`     | Indicates if the animation should loop (0 for false).                       |

### `opened` Animation

This animation likely represents the enemy in a fully open or active state.

| Attribute       | Value   | Description                                                                 |
|-----------------|---------|-----------------------------------------------------------------------------|
| `name`          | `opened`| The name of this animation.                                                 |
| `pos_x`         | `0`     | X-coordinate of the top-left corner of the animation frames.                |
| `pos_y`         | `408`   | Y-coordinate of the top-left corner of the animation frames.                |
| `frame_count`   | `10`    | The total number of frames in this animation.                               |
| `frame_width`   | `96`    | The width of each individual frame.                                         |
| `frame_height`  | `102`   | The height of each individual frame.                                        |
| `frame_wait`    | `0.11`  | The duration (in seconds) each frame is displayed.                          |
| `frames_per_row`| `10`    | The number of frames arranged horizontally in the sprite sheet.             |
| `loop`          | `1`     | Indicates if the animation should loop (1 for true).                        |

### `aggro` Animation

This animation likely represents the enemy becoming aggressive or entering an attack stance.

| Attribute       | Value   | Description                                                                 |
|-----------------|---------|-----------------------------------------------------------------------------|
| `name`          | `aggro` | The name of this animation.                                                 |
| `pos_x`         | `0`     | X-coordinate of the top-left corner of the animation frames.                |
| `pos_y`         | `510`   | Y-coordinate of the top-left corner of the animation frames.                |
| `frame_count`   | `7`     | The total number of frames in this animation.                               |
| `frame_width`   | `96`    | The width of each individual frame.                                         |
| `frame_height`  | `102`   | The height of each individual frame.                                        |
| `frame_wait`    | `0.13`  | The duration (in seconds) each frame is displayed.                          |
| `frames_per_row`| `10`    | The number of frames arranged horizontally in the sprite sheet.             |
| `loop`          | `1`     | Indicates if the animation should loop (1 for true).                        |