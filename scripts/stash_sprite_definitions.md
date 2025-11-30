---
title: Stash Sprite Definitions
category: data/buildings_gfx
---

# Stash Sprite Definitions

This document details the sprite definitions for the "stash" building in Noita, focusing on its visual animations.

## Sprite Attributes

The main `<Sprite>` tag defines the base image and its default animation.

| Attribute     | Description                                     |
|---------------|-------------------------------------------------|
| `filename`    | Path to the sprite image file.                  |
| `offset_x`    | Horizontal offset for the sprite.               |
| `offset_y`    | Vertical offset for the sprite.                 |
| `default_animation` | The animation to play by default.           |

## Animation Definitions

The `<RectAnimation>` tags define individual animations for the stash. Each animation consists of a sequence of frames from the sprite sheet.

### `stand` Animation

This is the default idle animation for the stash.

| Attribute       | Description                                     |
|-----------------|-------------------------------------------------|
| `name`          | `stand`                                         |
| `pos_x`         | X-coordinate of the animation's starting frame. |
| `pos_y`         | Y-coordinate of the animation's starting frame. |
| `frame_count`   | Number of frames in this animation.             |
| `frame_width`   | Width of each individual frame.                 |
| `frame_height`  | Height of each individual frame.                |
| `frame_wait`    | Time in seconds between frames.                 |
| `frames_per_row`| Number of frames per row in the sprite sheet.   |
| `loop`          | Whether the animation should loop (1 for yes).  |

### `opening` Animation

This animation plays when the stash is opening.

| Attribute       | Description                                     |
|-----------------|-------------------------------------------------|
| `name`          | `opening`                                       |
| `pos_x`         | X-coordinate of the animation's starting frame. |
| `pos_y`         | Y-coordinate of the animation's starting frame. |
| `frame_count`   | Number of frames in this animation.             |
| `frame_width`   | Width of each individual frame.                 |
| `frame_height`  | Height of each individual frame.                |
| `frame_wait`    | Time in seconds between frames.                 |
| `frames_per_row`| Number of frames per row in the sprite sheet.   |
| `loop`          | Whether the animation should loop (0 for no).   |
| `next_animation`| The animation to play after this one finishes.  |

### `open` Animation

This animation plays when the stash is fully open.

| Attribute       | Description                                     |
|-----------------|-------------------------------------------------|
| `name`          | `open`                                          |
| `pos_x`         | X-coordinate of the animation's starting frame. |
| `pos_y`         | Y-coordinate of the animation's starting frame. |
| `frame_count`   | Number of frames in this animation.             |
| `frame_width`   | Width of each individual frame.                 |
| `frame_height`  | Height of each individual frame.                |
| `frame_wait`    | Time in seconds between frames.                 |
| `frames_per_row`| Number of frames per row in the sprite sheet.   |
| `loop`          | Whether the animation should loop (1 for yes).  |

### `closing` Animation

This animation plays when the stash is closing.

| Attribute       | Description                                     |
|-----------------|-------------------------------------------------|
| `name`          | `closing`                                       |
| `pos_x`         | X-coordinate of the animation's starting frame. |
| `pos_y`         | Y-coordinate of the animation's starting frame. |
| `frame_count`   | Number of frames in this animation.             |
| `frame_width`   | Width of each individual frame.                 |
| `frame_height`  | Height of each individual frame.                |
| `frame_wait`    | Time in seconds between frames.                 |
| `frames_per_row`| Number of frames per row in the sprite sheet.   |
| `loop`          | Whether the animation should loop (0 for no).   |
| `next_animation`| The animation to play after this one finishes.  |

### `shake` and `shake2` Animations

These animations appear to be variations of a "shake" effect, likely used to indicate something happening with the stash.

| Attribute       | Description                                     |
|-----------------|-------------------------------------------------|
| `name`          | `shake` or `shake2`                             |
| `pos_x`         | X-coordinate of the animation's starting frame. |
| `pos_y`         | Y-coordinate of the animation's starting frame. |
| `frame_count`   | Number of frames in this animation.             |
| `frame_width`   | Width of each individual frame.                 |
| `frame_height`  | Height of each individual frame.                |
| `frame_wait`    | Time in seconds between frames.                 |
| `frames_per_row`| Number of frames per row in the sprite sheet.   |
| `loop`          | Whether the animation should loop (0 for no).   |
| `next_animation`| The animation to play after this one finishes.  |