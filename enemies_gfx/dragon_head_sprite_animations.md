---
title: Dragon Head Sprite Animations
category: data/enemies_gfx
---

# Dragon Head Sprite Animations

This document details the sprite animations for the Dragon Head enemy in Noita, as defined in the `dragon_head.xml` file. It focuses on the key attributes of the main `<Sprite>` element and its associated `<RectAnimation>` tags, which define the visual frames and behaviors of the dragon's head.

## Sprite Element

The root element `<Sprite>` defines the base image and default animation for the dragon head.

### Key Attributes:

*   **filename**: Specifies the path to the sprite sheet image file.
    *   `data/enemies_gfx/dragon_head.png`
*   **offset\_x**: Horizontal offset of the sprite from its origin.
    *   `17`
*   **offset\_y**: Vertical offset of the sprite from its origin.
    *   `15`
*   **default\_animation**: The animation to play by default.
    *   `stand`

## RectAnimation Elements

Each `<RectAnimation>` tag defines a specific animation sequence for the dragon head. These animations are crucial for controlling the visual representation of actions like opening/closing the mouth, eating, and standing.

### Animation Definitions:

Here's a breakdown of the defined animations:

| Animation Name | Frame Count | Frame Width | Frame Height | Frames Per Row | Frame Wait | Loop | Pos X | Pos Y | Shrink By One Pixel | Description                               |
| :------------- | :---------- | :---------- | :----------- | :------------- | :--------- | :--- | :---- | :---- | :------------------ | :---------------------------------------- |
| `mouth_shut`   | 1           | 32          | 32           | 4              | 0.09       | N/A  | 0     | 1     | N/A                 | Static frame for a closed mouth.          |
| `open_mouth`   | 4           | 33          | 33           | 4              | 0.09       | 0    | 0     | 34    | 1                   | Sequence for opening the mouth.           |
| `mouth_open`   | 1           | 32          | 32           | 4              | 0.09       | N/A  | 0     | 67    | N/A                 | Static frame for a fully open mouth.      |
| `shut_mouth`   | 2           | 33          | 33           | 4              | 0.07       | 0    | 0     | 100   | 1                   | Sequence for closing the mouth.           |
| `eat`          | 4           | 33          | 33           | 4              | 0.09       | 1    | 0     | 133   | 1                   | Animation sequence for eating.            |

### Key Attributes for `RectAnimation`:

*   **name**: The identifier for the animation. This name is used in game logic to trigger specific animations.
*   **frame\_count**: The total number of frames in this animation.
*   **frame\_width**: The width of each individual frame in pixels.
*   **frame\_height**: The height of each individual frame in pixels.
*   **frames\_per\_row**: How many frames are arranged horizontally on the sprite sheet.
*   **frame\_wait**: The duration (in seconds) each frame is displayed before transitioning to the next.
*   **loop**: If set to `0`, the animation plays only once. If omitted or set to `1`, it loops.
*   **pos\_x**: The starting X-coordinate of the animation's frames on the sprite sheet.
*   **pos\_y**: The starting Y-coordinate of the animation's frames on the sprite sheet.
*   **shrink\_by\_one\_pixel**: A value indicating if frames should be shrunk by one pixel, often used for smoother transitions or specific visual effects.