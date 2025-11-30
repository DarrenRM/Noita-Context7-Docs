---
title: Drone Sprite Animations
category: entities
---

# Drone Sprite Animations

This document details the sprite animations for the "drone" entity in Noita, as defined in `drone.xml`. It focuses on the key attributes of the sprite and its associated animations.

## Sprite Definition

The main `<Sprite>` tag defines the base image and its default animation.

### Key Sprite Attributes:

*   **filename**: `data/enemies_gfx/drone.png` - The path to the sprite sheet image.
*   **offset\_x**: `6` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `11` - Vertical offset for the sprite's origin.
*   **default\_animation**: `"stand"` - The animation to play by default.

## Animation Definitions

The `<RectAnimation>` tags define individual animations for the drone. All animations share similar frame dimensions and timing.

### Key RectAnimation Attributes:

*   **name**: The name of the animation (e.g., "stand", "walk", "burn").
*   **frame\_count**: `4` - The total number of frames in this animation.
*   **frame\_width**: `17` - The width of each individual frame in pixels.
*   **frame\_height**: `17` - The height of each individual frame in pixels.
*   **frames\_per\_row**: `4` - How many frames are arranged horizontally in the sprite sheet.
*   **frame\_wait**: `0.05` - The duration (in seconds) each frame is displayed before advancing.
*   **pos\_x**: `0` - The X-coordinate of the top-left corner of the animation frame area within the sprite sheet.
*   **pos\_y**: `1` - The Y-coordinate of the top-left corner of the animation frame area within the sprite sheet.
*   **shrink\_by\_one\_pixel**: `1` - Indicates if frames should be shrunk by one pixel, often for visual adjustments.

### Defined Animations:

| Animation Name | Frame Count | Frame Width | Frame Height | Frames Per Row | Frame Wait | Pos X | Pos Y | Shrink by One Pixel |
| :------------- | :---------- | :---------- | :----------- | :------------- | :--------- | :---- | :---- | :------------------ |
| `stand`        | 4           | 17          | 17           | 4              | 0.05       | 0     | 1     | 1                   |
| `walk`         | 4           | 17          | 17           | 4              | 0.05       | 0     | 1     | 1                   |
| `run`          | 4           | 17          | 17           | 4              | 0.05       | 0     | 1     | 1                   |
| `burn`         | 4           | 17          | 17           | 4              | 0.05       | 0     | 1     | 1                   |
| `fly_move`     | 4           | 17          | 17           | 4              | 0.05       | 0     | 1     | 1                   |
| `fly_idle`     | 4           | 17          | 17           | 4              | 0.05       | 0     | 1     | 1                   |

**Note:** All listed animations share the same frame dimensions, layout, and timing. The visual difference between them would be in the actual pixel data within the `drone.png` sprite sheet for each frame.