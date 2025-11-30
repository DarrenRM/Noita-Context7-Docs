---
title: Tentacler Small Sprite Animations
category: enemies_gfx
---

# Tentacler Small Sprite Animations

This document details the sprite animations for the `tentacler_small` enemy in Noita, as defined in its XML configuration file. This information is crucial for modders looking to alter or create new animations for this enemy.

## Sprite Definition

The main `<Sprite>` tag defines the base image and its properties.

### Key Attributes

*   **`filename`**: Specifies the path to the sprite sheet image.
    *   `data/enemies_gfx/tentacler_small.png`
*   **`offset_x`**: Horizontal offset for the sprite's origin.
    *   `9`
*   **`offset_y`**: Vertical offset for the sprite's origin.
    *   `16`
*   **`default_animation`**: The animation that plays by default.
    *   `stand`

## Animation Definitions

The `<RectAnimation>` tags define individual animations, specifying how frames are extracted from the sprite sheet and how they are played.

### General Animation Attributes

*   **`name`**: The identifier for the animation (e.g., "stand", "walk", "attack").
*   **`pos_x`**: The X-coordinate on the sprite sheet where the animation frames begin.
*   **`pos_y`**: The Y-coordinate on the sprite sheet where the animation frames begin.
*   **`frame_count`**: The total number of frames in the animation.
*   **`frame_width`**: The width of each individual frame.
    *   `18`
*   **`frame_height`**: The height of each individual frame.
    *   `18`
*   **`frame_wait`**: The duration (in seconds) each frame is displayed before transitioning to the next.
*   **`frames_per_row`**: How many frames are arranged horizontally on the sprite sheet.
    *   `6`
*   **`loop`**: Whether the animation should loop (`1` for true, `0` for false).

### Specific Animations

| Animation Name   | `pos_y` | `frame_count` | `frame_wait` | `loop` | Key Events                                                              | Notes                               |
| :--------------- | :------ | :------------ | :----------- | :----- | :---------------------------------------------------------------------- | :---------------------------------- |
| `stand`          | `0`     | `6`           | `0.23`       | `1`    | None                                                                    | Default idle animation.             |
| `walk`           | `0`     | `6`           | `0.23`       | `1`    | None                                                                    | Walking animation.                  |
| `run`            | `0`     | `6`           | `0.23`       | `1`    | None                                                                    | Running animation (copied from walk). |
| `burn`           | `0`     | `6`           | `0.23`       | `1`    | None                                                                    | Burning animation (copied from walk). |
| `attack`         | `36`    | `6`           | `0.1`        | `0`    | Frame 3: `shoot_ice` (probability 1, check_physics_material 0)          | Melee attack animation.             |
| `attack_ranged`  | `36`    | `6`           | `0.1`        | `0`    | Frame 3: `shoot_ice` (probability 1, check_physics_material 0)          | Ranged attack animation.            |
| `fly_idle`       | `0`     | `4`           | `0.23`       | `1`    | None                                                                    | Flying idle animation.              |
| `fly_move`       | `18`    | `4`           | `0.23`       | `1`    | None                                                                    | Flying movement animation.          |

### Animation Events

Animations can trigger specific game events at certain frames.

*   **`Event` tag**: Defines an event to occur.
    *   **`frame`**: The frame number at which the event triggers.
    *   **`name`**: The name of the event (e.g., `shoot_ice`).
    *   **`probability`**: The chance of the event occurring (1 is 100%).
    *   **`check_physics_material`**: Whether to check the physics material of the target (0 is false).

**Example Event:**

```xml
<Event frame="3" name="shoot_ice" probability="1" check_physics_material="0"/>
```
This event triggers the `shoot_ice` action on frame 3 of the `attack` and `attack_ranged` animations with certainty.