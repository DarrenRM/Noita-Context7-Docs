---
title: Boss Centipede Body Sprite
category: entities
---

# Boss Centipede Body Sprite

This document details the sprite information for the Boss Centipede's body segment in Noita. It defines the visual appearance, animations, and their properties.

## Sprite Definition

The primary sprite for the Boss Centipede body is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/entities/animals/boss_centipede/body.png` - The path to the sprite image file.
*   **offset\_x**: `48` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `48` - Vertical offset for the sprite's origin.
*   **default\_animation**: `"stand"` - The animation to play by default when the entity is spawned.

## Animations

The `<Sprite>` tag contains multiple `<RectAnimation>` tags, each defining a distinct animation.

### Animation Details:

| Animation Name | Description                               | Frame Count | Frame Width | Frame Height | Frame Wait | Frames Per Row | Next Animation | Loop |
| :------------- | :---------------------------------------- | :---------- | :---------- | :----------- | :--------- | :------------- | :------------- | :------------- |
| `stand`        | Idle animation for the centipede body.    | 4           | 96          | 96           | 0.12       | 4              | N/A            | 1              |
| `open`         | Animation for opening the centipede's mouth. | 7           | 96          | 96           | 0.09       | 7              | `opened`       | 0              |
| `close`        | Animation for closing the centipede's mouth. | 7           | 96          | 96           | 0.09       | 7              | `stand`        | 0              |
| `opened`       | The state where the centipede's mouth is open. | 10          | 96          | 96           | 0.11       | 10             | N/A            | 1              |
| `aggro`        | Aggressive animation, likely when attacking. | 7           | 96          | 96           | 0.13       | 10             | N/A            | 1              |

### Key Attributes for RectAnimation:

*   **name**: The identifier for the animation.
*   **pos\_x**, **pos\_y**: The starting coordinates of the animation frames within the sprite sheet.
*   **frame\_count**: The total number of frames in the animation.
*   **frame\_width**, **frame\_height**: The dimensions of each individual frame.
*   **frame\_wait**: The duration (in seconds) each frame is displayed before transitioning to the next.
*   **frames\_per\_row**: How many frames are arranged horizontally in the sprite sheet for this animation.
*   **next\_animation**: Specifies which animation to transition to after the current one finishes (if `loop` is 0).
*   **loop**: `1` for looping animations, `0` for one-time animations.