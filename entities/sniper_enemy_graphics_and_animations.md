---
title: Sniper Enemy Graphics and Animations
category: entities
---

# Sniper Enemy Graphics and Animations

This document details the graphical assets and animations for the "Sniper" enemy in Noita, as defined in its `sniper.xml` file. This file primarily uses the `<Sprite>` and `<RectAnimation>` tags to define how the enemy appears and moves.

## Sprite Definition

The main `<Sprite>` tag defines the base image file and its default animation.

### Key Attributes:

*   **filename**: `data/enemies_gfx/sniper.png` - The primary image file for the sniper sprite.
*   **offset\_x**: `5` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `14` - Vertical offset for the sprite's origin.
*   **default\_animation**: `"stand"` - The animation to play by default when the enemy is idle.

## Animations

The `<RectAnimation>` tags define distinct animations for the sniper, each with its own set of frames, timing, and events.

### Animations Table:

| Name           | Frame Count | Frame Width | Frame Height | Frame Wait | Frames Per Row | Pos X | Pos Y | Loop | Shrink |
| :------------- | :---------- | :---------- | :----------- | :--------- | :------------- | :---- | :---- | :--- | :----- |
| `stand`        | 12          | 20          | 17           | 0.2        | 12             | 0     | 1     | -    | -      |
| `walk`         | 6           | 21          | 18           | 0.1        | 6              | 0     | 19    | -    | 1      |
| `run`          | 6           | 21          | 18           | 0.09       | 8              | 0     | 19    | -    | 1      |
| `attack_ranged`| 13          | 21          | 18           | 0.11       | 13             | 0     | 37    | 0    | 1      |
| `attack`       | 6           | 21          | 18           | 0.09       | 6              | 0     | 55    | -    | 1      |
| `burn`         | 6           | 21          | 18           | 0.06       | 8              | 0     | 73    | -    | 1      |
| `jump_up`      | 3           | 21          | 18           | 0.082      | 8              | 0     | 91    | 0    | 1      |
| `jump_fall`    | 3           | 21          | 18           | 0.082      | 8              | 0     | 109   | 0    | 1      |
| `swim_idle`    | 6           | 21          | 18           | 0.082      | 8              | 0     | 127   | -    | 1      |
| `swim_move`    | 6           | 21          | 18           | 0.082      | 8              | 0     | 127   | -    | 1      |
| `attack_throw` | 6           | 21          | 18           | 0.12       | 13             | 0     | 145   | 0    | 1      |
| `jump_prepare` | 3           | 21          | 18           | 0.09       | 13             | 0     | 163   | 0    | 1      |

*Note: '-' indicates the attribute was not explicitly set or defaults to a common value.*

### Animation Events

Within each `<RectAnimation>`, `<Event>` tags define specific actions or triggers that occur at certain frames.

#### Key Event Attributes:

*   **name**: The name of the event (e.g., `breath`, `step`, `shoot_sniper`, `kick`, `throw`).
*   **frame**: The frame number at which the event occurs.
*   **probability**: The chance (0-1) of the event triggering.
*   **max\_distance**: Maximum distance for the event to be considered.
*   **check\_physics\_material**: Whether to check the physics material of the ground (1 for yes, 0 for no).
*   **on\_finished**: Action to take when the event finishes (typically 0, meaning no specific action).

#### Notable Events:

*   **`stand` animation**:
    *   Frame 8: `breath` event.
*   **`walk` animation**:
    *   Frame 0: `step` event.
    *   Frame 3: `step` event.
*   **`run` animation**:
    *   Frame 0: `step` event.
    *   Frame 3: `step` event.
*   **`attack_ranged` animation**:
    *   Frame 8: `shoot_sniper` event.
*   **`attack` animation**:
    *   Frame 3: `kick` event.
*   **`burn` animation**:
    *   Frame 0: `step` event.
    *   Frame 3: `step` event.
*   **`jump_up` animation**:
    *   Frame 0: `jump` event.
*   **`swim_idle` animation**:
    *   Frame 0: `paddle` event.
    *   Frame 3: `paddle` event.
*   **`swim_move` animation**:
    *   Frame 0: `paddle` event.
    *   Frame 3: `paddle` event.
*   **`attack_throw` animation**:
    *   Frame 4: `throw` event.
*   **`jump_prepare` animation**:
    *   Frame 3: `jump_start` event.