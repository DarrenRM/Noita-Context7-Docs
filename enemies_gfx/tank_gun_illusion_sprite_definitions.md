---
title: Tank Gun Illusion Sprite Definitions
category: data/enemies_gfx/
---

# Tank Gun Illusion Sprite Definitions

This document details the sprite definitions for the "tank_gun_illusion" enemy in Noita, focusing on its visual animations.

## Sprite Attributes

The main `<Sprite>` tag defines the overall sprite properties and the default animation.

| Attribute       | Value                               | Description                                                                 |
| :-------------- | :---------------------------------- | :-------------------------------------------------------------------------- |
| `default_animation` | `stand`                             | The animation to play by default when the sprite is first loaded.           |
| `filename`      | `data/enemies_gfx/tank_gun_illusion.png` | The path to the sprite image file.                                          |
| `offset_x`      | `9`                                 | Horizontal offset for the sprite's origin.                                  |
| `offset_y`      | `10`                                | Vertical offset for the sprite's origin.                                    |

## RectAnimation Definitions

Each `<RectAnimation>` tag defines a specific animation sequence for the sprite.

### Stand Animation

| Attribute       | Value   | Description                                                                 |
| :-------------- | :------ | :-------------------------------------------------------------------------- |
| `name`          | `stand` | The name of this animation.                                                 |
| `frame_count`   | `1`     | Number of frames in this animation.                                         |
| `frame_width`   | `22`    | Width of each individual frame in pixels.                                   |
| `frame_height`  | `20`    | Height of each individual frame in pixels.                                  |
| `frames_per_row`| `11`    | Number of frames arranged horizontally in the sprite sheet.                 |
| `frame_wait`    | `0.16`  | Time in seconds to wait between each frame.                                 |
| `pos_x`         | `0`     | X-coordinate of the top-left corner of the animation frames in the sprite sheet. |
| `pos_y`         | `1`     | Y-coordinate of the top-left corner of the animation frames in the sprite sheet. |

### Walk Animation

| Attribute       | Value   | Description                                                                 |
| :-------------- | :------ | :-------------------------------------------------------------------------- |
| `name`          | `walk`  | The name of this animation.                                                 |
| `frame_count`   | `4`     | Number of frames in this animation.                                         |
| `frame_width`   | `22`    | Width of each individual frame in pixels.                                   |
| `frame_height`  | `20`    | Height of each individual frame in pixels.                                  |
| `frames_per_row`| `11`    | Number of frames arranged horizontally in the sprite sheet.                 |
| `frame_wait`    | `0.1`   | Time in seconds to wait between each frame.                                 |
| `pos_x`         | `0`     | X-coordinate of the top-left corner of the animation frames in the sprite sheet. |
| `pos_y`         | `22`    | Y-coordinate of the top-left corner of the animation frames in the sprite sheet. |

### Run Animation

| Attribute       | Value   | Description                                                                 |
| :-------------- | :------ | :-------------------------------------------------------------------------- |
| `name`          | `run`   | The name of this animation.                                                 |
| `frame_count`   | `4`     | Number of frames in this animation.                                         |
| `frame_width`   | `22`    | Width of each individual frame in pixels.                                   |
| `frame_height`  | `20`    | Height of each individual frame in pixels.                                  |
| `frames_per_row`| `11`    | Number of frames arranged horizontally in the sprite sheet.                 |
| `frame_wait`    | `0.09`  | Time in seconds to wait between each frame.                                 |
| `pos_x`         | `0`     | X-coordinate of the top-left corner of the animation frames in the sprite sheet. |
| `pos_y`         | `22`    | Y-coordinate of the top-left corner of the animation frames in the sprite sheet. |

### Burn Animation

| Attribute       | Value   | Description                                                                 |
| :-------------- | :------ | :-------------------------------------------------------------------------- |
| `name`          | `burn`  | The name of this animation.                                                 |
| `frame_count`   | `4`     | Number of frames in this animation.                                         |
| `frame_width`   | `22`    | Width of each individual frame in pixels.                                   |
| `frame_height`  | `20`    | Height of each individual frame in pixels.                                  |
| `frames_per_row`| `11`    | Number of frames arranged horizontally in the sprite sheet.                 |
| `frame_wait`    | `0.09`  | Time in seconds to wait between each frame.                                 |
| `pos_x`         | `0`     | X-coordinate of the top-left corner of the animation frames in the sprite sheet. |
| `pos_y`         | `22`    | Y-coordinate of the top-left corner of the animation frames in the sprite sheet. |

### Attack Animation

| Attribute       | Value   | Description                                                                 |
| :-------------- | :------ | :-------------------------------------------------------------------------- |
| `name`          | `attack`| The name of this animation.                                                 |
| `frame_count`   | `4`     | Number of frames in this animation.                                         |
| `frame_width`   | `22`    | Width of each individual frame in pixels.                                   |
| `frame_height`  | `20`    | Height of each individual frame in pixels.                                  |
| `frames_per_row`| `11`    | Number of frames arranged horizontally in the sprite sheet.                 |
| `frame_wait`    | `0.07`  | Time in seconds to wait between each frame.                                 |
| `loop`          | `0`     | `0` indicates the animation does not loop.                                  |
| `pos_x`         | `0`     | X-coordinate of the top-left corner of the animation frames in the sprite sheet. |
| `pos_y`         | `43`    | Y-coordinate of the top-left corner of the animation frames in the sprite sheet. |

### Attack Ranged Animation

| Attribute       | Value   | Description                                                                 |
| :-------------- | :------ | :-------------------------------------------------------------------------- |
| `name`          | `attack_ranged` | The name of this animation.                                                 |
| `frame_count`   | `4`     | Number of frames in this animation.                                         |
| `frame_width`   | `22`    | Width of each individual frame in pixels.                                   |
| `frame_height`  | `20`    | Height of each individual frame in pixels.                                  |
| `frames_per_row`| `11`    | Number of frames arranged horizontally in the sprite sheet.                 |
| `frame_wait`    | `0.09`  | Time in seconds to wait between each frame.                                 |
| `pos_x`         | `0`     | X-coordinate of the top-left corner of the animation frames in the sprite sheet. |
| `pos_y`         | `43`    | Y-coordinate of the top-left corner of the animation frames in the sprite sheet. |

### Attack Grenade Animation

| Attribute       | Value   | Description                                                                 |
| :-------------- | :------ | :-------------------------------------------------------------------------- |
| `name`          | `attack_grenade` | The name of this animation.                                                 |
| `frame_count`   | `11`    | Number of frames in this animation.                                         |
| `frame_width`   | `23`    | Width of each individual frame in pixels.                                   |
| `frame_height`  | `21`    | Height of each individual frame in pixels.                                  |
| `frames_per_row`| `11`    | Number of frames arranged horizontally in the sprite sheet.                 |
| `frame_wait`    | `0.04`  | Time in seconds to wait between each frame.                                 |
| `loop`          | `0`     | `0` indicates the animation does not loop.                                  |
| `pos_x`         | `0`     | X-coordinate of the top-left corner of the animation frames in the sprite sheet. |
| `pos_y`         | `64`    | Y-coordinate of the top-left corner of the animation frames in the sprite sheet. |
| `shrink_by_one_pixel` | `1` | This attribute might indicate a slight visual adjustment for this specific animation. |