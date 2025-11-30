---
title: Big Firebug Sprite Definitions
category: enemies_gfx
---

# Big Firebug Sprite Definitions

This document details the sprite definitions for the Big Firebug enemy in Noita, focusing on its visual animations and associated events.

## Sprite Definition

The main `<Sprite>` tag defines the base image and default animation for the Big Firebug.

### Key Attributes:

*   **filename**: `data/enemies_gfx/bigfirebug.png` - The path to the sprite sheet.
*   **offset\_x**: `10` - Horizontal offset for the sprite.
*   **offset\_y**: `18` - Vertical offset for the sprite.
*   **default\_animation**: `"stand"` - The animation to play by default.

## Animation Definitions

The `<Sprite>` tag contains multiple `<RectAnimation>` tags, each defining a specific animation sequence.

### Animation Attributes:

*   **name**: The identifier for the animation (e.g., "stand", "walk", "attack\_ranged").
*   **frame\_count**: The total number of frames in the animation.
*   **frame\_width**: The width of each individual frame.
*   **frame\_height**: The height of each individual frame.
*   **frames\_per\_row**: How many frames are arranged horizontally on the sprite sheet.
*   **frame\_wait**: The duration (in seconds) each frame is displayed.
*   **pos\_x**: The starting X coordinate of the animation frames on the sprite sheet.
*   **pos\_y**: The starting Y coordinate of the animation frames on the sprite sheet.
*   **loop**: `0` indicates the animation does not loop, `1` (or omitted) indicates it loops.
*   **shrink\_by\_one\_pixel**: `1` indicates the sprite is shrunk by one pixel, often used for attack animations.

### Notable Animations:

| Animation Name    | Frame Count | Frame Size (WxH) | Frames Per Row | Frame Wait | Pos (X, Y) | Loop | Notes                               |
| :---------------- | :---------- | :--------------- | :------------- | :--------- | :--------- | :--- | :---------------------------------- |
| `stand`           | 10          | 20x20            | 10             | 0.05       | (0, 1)     | Yes  | Idle animation.                     |
| `walk`            | 10          | 20x20            | 10             | 0.05       | (0, 1)     | Yes  | Walking animation.                  |
| `run`             | 10          | 20x20            | 10             | 0.05       | (0, 1)     | Yes  | Running animation.                  |
| `burn`            | 10          | 20x20            | 10             | 0.05       | (0, 1)     | Yes  | Animation when burning.             |
| `fly_move`        | 8           | 20x20            | 8              | 0.035      | (0, 22)    | Yes  | Flying movement animation.          |
| `fly_idle`        | 8           | 20x20            | 8              | 0.035      | (0, 22)    | Yes  | Idle flying animation.              |
| `attack_dash`     | 8           | 20x20            | 8              | 0.035      | (0, 22)    | Yes  | Dash attack animation.              |
| `attack_ranged`   | 8           | 21x21            | 8              | 0.06       | (0, 43)    | No   | Ranged attack animation.            |

## Animation Events

Some animations can trigger specific game events at certain frames.

### Key Event Attributes:

*   **name**: The identifier for the event (e.g., "dash", "attack\_shoot").
*   **frame**: The frame number within the animation when the event should trigger.
*   **probability**: The chance (0 to 1) that the event will occur.
*   **on\_finished**: `0` means the event triggers and the animation continues; `1` means the event triggers and the animation stops.
*   **check\_physics\_material**: `0` means no physics material check is performed; `1` means a check is performed.
*   **max\_distance**: For movement events, the maximum distance the entity can move.

### Notable Events:

*   **`attack_dash` animation**:
    *   **Event**: `dash`
    *   **Frame**: `2`
    *   **Probability**: `1`
    *   **Max Distance**: `500`
    *   **Notes**: Triggers a dash action on frame 2.

*   **`attack_ranged` animation**:
    *   **Event**: `attack_shoot`
    *   **Frame**: `1`
    *   **Probability**: `1`
    *   **Notes**: Triggers a projectile firing action on frame 1. This animation does not loop.