---
title: Phantom A Sprite Animations
category: entities
---

# Phantom A Sprite Animations

This document details the sprite animations for the "Phantom A" enemy in Noita, as defined in its XML configuration file. It focuses on the key attributes of the `Sprite` and `RectAnimation` elements, providing a clear overview for modding purposes.

## Sprite Element

The root element defining the sprite's base properties and its constituent animations.

### Key Attributes:

*   **filename**: The path to the sprite sheet image file.
    *   `data/enemies_gfx/phantom_a.png`
*   **offset\_x**: Horizontal offset for the sprite's origin.
    *   `8`
*   **offset\_y**: Vertical offset for the sprite's origin.
    *   `19`
*   **default\_animation**: The animation to play by default.
    *   `stand`

## RectAnimation Elements

Each `RectAnimation` defines a specific animation sequence for the sprite.

### Key Attributes:

*   **name**: The identifier for the animation (e.g., "stand", "walk", "attack").
*   **frame\_count**: The total number of frames in the animation.
*   **frame\_width**: The width of each individual frame in pixels.
*   **frame\_height**: The height of each individual frame in pixels.
*   **frames\_per\_row**: How many frames are arranged horizontally on the sprite sheet.
*   **frame\_wait**: The duration (in seconds) each frame is displayed before advancing.
*   **pos\_x**: The horizontal starting position of the animation frames on the sprite sheet.
*   **pos\_y**: The vertical starting position of the animation frames on the sprite sheet.
*   **loop**: Whether the animation should loop (`1` for true, `0` for false).
*   **shrink\_by\_one\_pixel**: Indicates if frames should be shrunk by one pixel (often used for consistency).

### Defined Animations:

| Name          | Frame Count | Frame Width | Frame Height | Frames Per Row | Frame Wait | Pos X | Pos Y | Loop |
| :------------ | :---------- | :---------- | :----------- | :------------- | :--------- | :---- | :---- | :--- |
| `stand`       | 6           | 17          | 23           | 8              | 0.12       | 0     | 1     | 1    |
| `walk`        | 4           | 17          | 23           | 8              | 0.1        | 0     | 24    | 1    |
| `run`         | 4           | 17          | 23           | 8              | 0.1        | 0     | 24    | 1    |
| `burn`        | 4           | 17          | 23           | 8              | 0.1        | 0     | 24    | 1    |
| `fly_idle`    | 4           | 17          | 23           | 8              | 0.09       | 0     | 47    | 1    |
| `fly_move`    | 4           | 17          | 23           | 8              | 0.09       | 0     | 47    | 1    |
| `attack_ranged` | 7           | 17          | 23           | 8              | 0.09       | 0     | 70    | 0    |
| `attack`      | 5           | 25          | 23           | 8              | 0.09       | 0     | 93    | 0    |

*Note: `walk`, `run`, and `burn` share the same sprite sheet coordinates and dimensions, implying they use similar visual frames or are intended to be visually distinct through other game logic.*

## Event Elements

Events can be attached to specific frames within an animation to trigger actions.

### `attack_ranged` Animation Events:

*   **Event Name**: `shoot_magic`
    *   **Trigger Frame**: `4`
    *   **On Finished**: `0` (Does not trigger when animation finishes)
    *   **Probability**: `1` (Always triggers if conditions met)
    *   **Max Distance**: `500`
    *   **Check Physics Material**: `0` (Does not check physics material)