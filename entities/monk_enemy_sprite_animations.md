---
title: Monk Enemy Sprite Animations
category: entities
---

# Monk Enemy Sprite Animations

This document details the sprite animations for the Monk enemy in Noita, as defined in the `monk.xml` file. It focuses on the key attributes of each animation state.

## Sprite Definition

The main `<Sprite>` tag defines the base image and default animation.

### Key Attributes:

*   **filename**: `data/enemies_gfx/monk.png` - The path to the sprite sheet.
*   **offset\_x**: `10` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `19` - Vertical offset for the sprite's origin.
*   **default\_animation**: `"stand"` - The animation to play by default.

## Animation States

The `<RectAnimation>` tags define individual animation sequences.

### Common Attributes:

*   **name**: The identifier for the animation state (e.g., "stand", "walk", "jump\_up").
*   **pos\_x**: The X-coordinate of the animation's starting frame on the sprite sheet.
*   **pos\_y**: The Y-coordinate of the animation's starting frame on the sprite sheet.
*   **frame\_width**: The width of each individual frame in pixels.
*   **frame\_height**: The height of each individual frame in pixels.
*   **frame\_count**: The total number of frames in the animation.
*   **frame\_wait**: The duration (in seconds) each frame is displayed.
*   **frames\_per\_row**: The number of frames that fit horizontally on the sprite sheet.
*   **loop**: `0` for non-looping animations, `1` for looping animations.

### Defined Animations:

| Name            | pos\_y | frame\_count | frame\_wait | loop | Notes                               |
| :-------------- | :----- | :----------- | :---------- | :--- | :---------------------------------- |
| **stand**       | `0`    | `7`          | `0.09`      | `1`  | Idle animation.                     |
| **walk**        | `22`   | `7`          | `0.06`      | `1`  | Walking animation.                  |
| **run**         | `22`   | `7`          | `0.04`      | `1`  | Running animation (faster walk).    |
| **jump\_prepare** | `44`   | `3`          | `0.09`      | `0`  | Prepares for a jump.                |
|                 |        |              |             |      | `<Event frame="3" name="jump_start"/>` |
| **jump\_up**    | `66`   | `3`          | `0.12`      | `0`  | Ascending phase of a jump.          |
| **jump\_fall**  | `88`   | `3`          | `0.12`      | `1`  | Descending phase of a jump.         |
| **land**        | `44`   | `3`          | `0.06`      | `0`  | Animation played upon landing.      |
|                 |        |              |             |      | `<Event check_physics_material="1" ... name="land"/>` |

### Animation Events:

Some animations include `<Event>` tags to trigger specific actions at certain frames.

*   **jump\_prepare**: Triggers a `"jump_start"` event on frame `3`.
*   **land**: Triggers a `"land"` event on frame `0` when `check_physics_material` is `1`. This event is likely used to detect landing on different surfaces.