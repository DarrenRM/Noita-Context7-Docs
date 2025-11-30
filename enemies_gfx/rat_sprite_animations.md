---
title: Rat Sprite Animations
category: enemies_gfx
---

# Rat Sprite Animations

This document details the sprite animations for the Rat enemy in Noita, as defined in `rat.xml`. It focuses on key attributes for AI-assisted modding.

## Sprite Definition

The main `<Sprite>` tag defines the base image and default animation.

### Key Attributes:

*   **filename**: `data/enemies_gfx/rat.png` - The texture file for the rat's sprites.
*   **offset\_x**: `20` - Horizontal offset for the sprite.
*   **offset\_y**: `12` - Vertical offset for the sprite.
*   **default\_animation**: `"stand"` - The animation played by default when the rat is idle.

## RectAnimation Definitions

Each `<RectAnimation>` tag defines a specific animation sequence.

### Animation List:

| Name       | Frame Count | Frame Width | Frame Height | Frames Per Row | Frame Wait | Loop | Pos X | Pos Y | Shrink By One Pixel |
| :--------- | :---------- | :---------- | :----------- | :------------- | :--------- | :--- | :---- | :---- | :------------------ |
| `stand`    | 5           | 20          | 20           | 6              | 0.1        | -    | 0     | 1     | -                   |
| `walk`     | 6           | 20          | 20           | 8              | 0.06       | -    | 0     | 22    | -                   |
| `run`      | 6           | 20          | 20           | 8              | 0.06       | -    | 0     | 22    | -                   |
| `burn`     | 6           | 20          | 20           | 8              | 0.06       | -    | 0     | 22    | -                   |
| `jump_up`  | 3           | 20          | 20           | 8              | 0.082      | 0    | 0     | 43    | -                   |
| `jump_fall`| 2           | 20          | 20           | 8              | 0.082      | 0    | 0     | 64    | -                   |
| `attack`   | 4           | 21          | 21           | 8              | 0.08       | 0    | 0     | 85    | 1                   |

### Key Attributes for `RectAnimation`:

*   **name**: The identifier for the animation (e.g., "stand", "walk", "attack").
*   **frame\_count**: The total number of frames in the animation.
*   **frame\_width**, **frame\_height**: Dimensions of each individual frame.
*   **frames\_per\_row**: How many frames are arranged horizontally in the sprite sheet.
*   **frame\_wait**: The duration (in seconds) each frame is displayed.
*   **loop**: `0` indicates the animation does not loop; otherwise, it loops.
*   **pos\_x**, **pos\_y**: The starting coordinates of the animation frames within the sprite sheet.
*   **shrink\_by\_one\_pixel**: If `1`, the sprite is shrunk by one pixel, often used for attack animations to give a sense of impact.

## Animation Events

`<Event>` tags within `<RectAnimation>` trigger specific actions at certain frames.

### Key Attributes for `Event`:

*   **name**: The name of the event (e.g., "step", "jump", "attack\_bite").
*   **frame**: The frame number (0-indexed) at which the event occurs.
*   **probability**: The chance (0-1) of the event firing.
*   **on\_finished**: If `0`, the event does not trigger when the animation finishes.
*   **check\_physics\_material**: If `1`, the event checks the physics material of the ground beneath the entity.
*   **max\_distance**: Maximum distance for physics material checks.

### Notable Events:

*   **`stand`**: No specific events defined.
*   **`walk`**, **`run`**, **`burn`**: Contain `step` events on frames `0` and `5`. These likely trigger footstep sounds or particle effects.
*   **`jump_up`**: Contains a `jump` event on frame `0`.
*   **`jump_fall`**: No specific events defined.
*   **`attack`**: Contains an `attack_bite` event on frame `2`. This is the primary event for the rat's attack action.