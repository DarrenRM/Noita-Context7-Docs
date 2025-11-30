---
title: Fire Mage Graphics
category: data/enemies_gfx
---

# Fire Mage Graphics

This document details the graphical assets for the Fire Mage enemy in Noita, as defined in `firemage.xml`. It focuses on the sprite definition, animation states, and key event triggers.

## Sprite Definition

The main `Sprite` tag defines the base image and its associated hotspot data.

### Key Attributes:

*   **filename**: `data/enemies_gfx/firemage.png` - The primary image file for the Fire Mage.
*   **hotspots_filename**: `data/enemies_gfx/firemage_hotspots.png` - The image file containing collision and interaction points.
*   **offset\_x**: `8` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `20` - Vertical offset for the sprite's origin.
*   **default\_animation**: `"stand"` - The animation state that plays by default.

### Hotspots:

*   **hand**: A defined hotspot named "hand" with a specific color (`000011ff`), likely used for melee attacks or interactions.

## Animations

The `Sprite` tag contains multiple `RectAnimation` tags, each defining a distinct animation state for the Fire Mage.

### Animation States:

| Animation Name | Description      | Frame Count | Frame Width | Frame Height | Frame Wait (s) | Loop | Notes                                     |
| :------------- | :--------------- | :---------- | :---------- | :----------- | :------------- | :--- | :---------------------------------------- |
| `stand`        | Idle/Standing    | 8           | 18          | 24           | 0.09           | 1    |                                           |
| `walk`         | Walking          | 8           | 18          | 24           | 0.07           | 1    | Triggers `step` events on frames 2 and 6. |
| `run`          | Running          | 8           | 18          | 24           | 0.06           | 1    | Triggers `step` events on frames 2 and 6. |
| `burn`         | Burning          | 8           | 18          | 24           | 0.06           | 1    | Triggers `step` events on frames 2 and 6. |
| `attack_ranged`| Ranged Attack    | 6           | 20          | 24           | 0.09           | 0    | Triggers `attack_shoot` on frame 3.       |
| `attack`       | Melee Attack     | 6           | 20          | 24           | 0.09           | 0    | Triggers `attack_melee` on frame 3.       |
| `fly_move`     | Flying Movement  | 4           | 18          | 24           | 0.09           | 1    |                                           |
| `fly_idle`     | Flying Idle      | 4           | 18          | 24           | 0.09           | 1    |                                           |
| `jump_up`      | Jumping Up       | 4           | 18          | 24           | 0.04           | 0    | Triggers `jump` on frame 0. Next: `jumping`. |
| `jumping`      | Mid-air Jump     | 4           | 18          | 24           | 0.08           | 1    |                                           |
| `jump_fall`    | Falling after Jump| 4           | 18          | 24           | 0.08           | 1    |                                           |

### Animation Event Details:

*   **`step`**: Occurs during `walk`, `run`, and `burn` animations. `check_physics_material="1"` suggests it might influence movement based on the ground material.
*   **`attack_shoot`**: Triggered during the `attack_ranged` animation. `check_physics_material="0"` indicates it's not dependent on the ground material.
*   **`attack_melee`**: Triggered during the `attack` animation. `check_physics_material="0"` indicates it's not dependent on the ground material.
*   **`jump`**: Triggered during the `jump_up` animation. `check_physics_material="1"` suggests the jump might be affected by the ground material.

### Animation Offset Variations:

Some animations, like `attack_ranged` and `attack`, have specific `offset_x` and `offset_y` values that override the global sprite offsets, allowing for precise positioning during those actions.

*   **`attack_ranged`**: `offset_x="9"`, `offset_y="20"`
*   **`attack`**: `offset_x="10"`, `offset_y="19"`