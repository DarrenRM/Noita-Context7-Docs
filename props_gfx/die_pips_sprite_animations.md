---
title: Die Pips Sprite Animations
category: props_gfx
---

# Die Pips Sprite Animations

This document describes the sprite animations for the "die_pips" asset in Noita, used for visual representation of dice rolls.

## Sprite Definition

The main `<Sprite>` tag defines the base image and its properties.

### Key Attributes:

*   **filename**: `data/props_gfx/die_pips.png` - The path to the sprite sheet.
*   **offset\_x**: `8` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `8` - Vertical offset for the sprite's origin.
*   **default\_animation**: `"default"` - Specifies the animation to play by default.

## Animations

The file defines several `RectAnimation` elements, each representing a distinct animation state for the dice pips.

### Animation Details:

Each `RectAnimation` defines a sequence of frames from the sprite sheet.

| Attribute        | Description                                                              |
| :--------------- | :----------------------------------------------------------------------- |
| **name**         | Unique identifier for the animation (e.g., "default", "roll", "rolled\_1"). |
| **pos\_x**       | Starting X-coordinate of the animation frames on the sprite sheet.       |
| **pos\_y**       | Starting Y-coordinate of the animation frames on the sprite sheet.       |
| **frame\_count** | The total number of frames in this animation.                            |
| **frame\_width** | The width of each individual frame in pixels.                            |
| **frame\_height**| The height of each individual frame in pixels.                           |
| **frame\_wait**  | The duration (in seconds) each frame is displayed before advancing.      |
| **frames\_per\_row** | How many frames are arranged horizontally on the sprite sheet.         |
| **loop**         | `1` indicates the animation will loop, `0` means it plays once.          |

### Defined Animations:

| Animation Name | Description                               | Frame Count | Frame Wait | Notes                                     |
| :------------- | :---------------------------------------- | :---------- | :--------- | :---------------------------------------- |
| `default`      | The default, likely idle, state.          | 1           | 0.1        | Single frame, static display.             |
| `roll`         | Represents the dice rolling animation.    | 8           | 0.04       | Rapid animation for rolling effect.       |
| `rolled_1`     | Displays the result of a '1' roll.        | 1           | 0.1        | Static frame for a '1' result.            |
| `rolled_2`     | Displays the result of a '2' roll.        | 1           | 0.1        | Static frame for a '2' result.            |
| `rolled_3`     | Displays the result of a '3' roll.        | 1           | 0.1        | Static frame for a '3' result.            |
| `rolled_4`     | Displays the result of a '4' roll.        | 1           | 0.1        | Static frame for a '4' result.            |
| `rolled_5`     | Displays the result of a '5' roll.        | 1           | 0.1        | Static frame for a '5' result.            |
| `rolled_6`     | Displays the result of a '6' roll.        | 1           | 0.1        | Static frame for a '6' result.            |
| `rolled_bad`   | Displays a "bad" roll outcome.            | 1           | 0.1        | Specific visual for a negative outcome.   |
| `rolled_good`  | Displays a "good" roll outcome.           | 1           | 0.1        | Specific visual for a positive outcome.   |

**Note:** The `pos_x` values for the `rolled_X` animations indicate they are positioned sequentially on the sprite sheet, each occupying a 16x16 pixel area. For example, `rolled_1` starts at `pos_x="0"`, `rolled_2` at `pos_x="16"`, and so on.