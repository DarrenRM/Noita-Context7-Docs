---
title: Homunculus Dark Sprite Animations
category: data/enemies_gfx
---

# Homunculus Dark Sprite Animations

This document details the sprite animations for the "Homunculus Dark" enemy in Noita, as defined in its XML configuration file. This information is crucial for understanding and modifying the visual behavior of this enemy.

## Sprite Definition

The main `<Sprite>` tag defines the base properties and the default animation.

### Key Attributes

| Attribute        | Value     | Description                                                                 |
| :--------------- | :-------- | :-------------------------------------------------------------------------- |
| `default_animation` | `stand`   | The animation played when the enemy is idle.                                |
| `filename`       | `data/enemies_gfx/homunculus_dark.png` | The path to the sprite sheet containing all animations.                     |
| `offset_x`       | `6.5`     | Horizontal offset for the sprite's origin.                                  |
| `offset_y`       | `10`      | Vertical offset for the sprite's origin.                                    |

## Animation Definitions

The `<Sprite>` tag contains multiple `<RectAnimation>` tags, each defining a specific animation sequence.

### `stand` Animation

*   **Description:** The idle animation for the Homunculus Dark.
*   **Key Attributes:**
    *   `name`: `stand`
    *   `frame_count`: `6`
    *   `frame_width`: `16`
    *   `frame_height`: `16`
    *   `frame_wait`: `0.1` (seconds per frame)
    *   `frames_per_row`: `6`
    *   `pos_x`: `0` (starting X coordinate on sprite sheet)
    *   `pos_y`: `1` (starting Y coordinate on sprite sheet)

### `walk` Animation

*   **Description:** The animation for when the Homunculus Dark is walking.
*   **Key Attributes:**
    *   `name`: `walk`
    *   `frame_count`: `6`
    *   `frame_width`: `16`
    *   `frame_height`: `16`
    *   `frame_wait`: `0.085` (seconds per frame)
    *   `frames_per_row`: `6`
    *   `pos_x`: `0`
    *   `pos_y`: `18`
*   **Events:**
    *   `step` event triggered at frame `0` and `3`.

### `run` Animation

*   **Description:** The animation for when the Homunculus Dark is running.
*   **Key Attributes:**
    *   `name`: `run`
    *   `frame_count`: `6`
    *   `frame_width`: `16`
    *   `frame_height`: `16`
    *   `frame_wait`: `0.085` (seconds per frame)
    *   `frames_per_row`: `6`
    *   `pos_x`: `0`
    *   `pos_y`: `18`
*   **Events:**
    *   `step` event triggered at frame `0` and `3`.

### `burn` Animation

*   **Description:** The animation for when the Homunculus Dark is burning.
*   **Key Attributes:**
    *   `name`: `burn`
    *   `frame_count`: `6`
    *   `frame_width`: `16`
    *   `frame_height`: `16`
    *   `frame_wait`: `0.085` (seconds per frame)
    *   `frames_per_row`: `6`
    *   `pos_x`: `0`
    *   `pos_y`: `18`
*   **Events:**
    *   `step` event triggered at frame `0` and `3`.

### `fly_idle` Animation

*   **Description:** The idle animation when the Homunculus Dark is flying.
*   **Key Attributes:**
    *   `name`: `fly_idle`
    *   `frame_count`: `4`
    *   `frame_width`: `17`
    *   `frame_height`: `18`
    *   `frame_wait`: `0.12` (seconds per frame)
    *   `frames_per_row`: `15`
    *   `pos_x`: `0`
    *   `pos_y`: `35`
    *   `shrink_by_one_pixel`: `1`

### `fly_move` Animation

*   **Description:** The movement animation when the Homunculus Dark is flying.
*   **Key Attributes:**
    *   `name`: `fly_move`
    *   `frame_count`: `4`
    *   `frame_width`: `17`
    *   `frame_height`: `18`
    *   `frame_wait`: `0.12` (seconds per frame)
    *   `frames_per_row`: `15`
    *   `pos_x`: `0`
    *   `pos_y`: `35`
    *   `shrink_by_one_pixel`: `1`

### `attack_ranged` Animation

*   **Description:** The animation for performing a ranged attack.
*   **Key Attributes:**
    *   `name`: `attack_ranged`
    *   `frame_count`: `6`
    *   `frame_width`: `16`
    *   `frame_height`: `17`
    *   `frame_wait`: `0.04` (seconds per frame)
    *   `frames_per_row`: `6`
    *   `loop`: `0` (animation does not loop)
    *   `pos_x`: `0`
    *   `pos_y`: `53`
*   **Events:**
    *   `shoot_magic` event triggered at frame `3`.

### `attack` Animation

*   **Description:** The animation for performing a melee attack.
*   **Key Attributes:**
    *   `name`: `attack`
    *   `frame_count`: `6`
    *   `frame_width`: `16`
    *   `frame_height`: `17`
    *   `frame_wait`: `0.04` (seconds per frame)
    *   `frames_per_row`: `6`
    *   `loop`: `0` (animation does not loop)
    *   `pos_x`: `0`
    *   `pos_y`: `53`
*   **Events:**
    *   `shoot_melee` event triggered at frame `3`.

## Animation Events

Events within animations can trigger specific game actions.

### `step` Event

*   **Description:** Triggers a "step" sound or effect.
*   **Key Attributes:**
    *   `check_physics_material`: `1` (checks the material of the ground)
    *   `max_distance`: `500`
    *   `on_finished`: `0` (event does not trigger on animation completion)
    *   `probability`: `1` (always triggers if conditions are met)

### `shoot_magic` Event

*   **Description:** Triggers a magical projectile or effect during a ranged attack.
*   **Key Attributes:**
    *   `check_physics_material`: `0` (does not check physics material)
    *   `max_distance`: `500`
    *   `on_finished`: `0`
    *   `probability`: `1`

### `shoot_melee` Event

*   **Description:** Triggers a melee attack action.
*   **Key Attributes:**
    *   `check_physics_material`: `0`
    *   `max_distance`: `500`
    *   `on_finished`: `0`
    *   `probability`: `1`