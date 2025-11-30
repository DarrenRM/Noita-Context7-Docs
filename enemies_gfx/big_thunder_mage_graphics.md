---
title: Big Thunder Mage Graphics
category: enemies_gfx
---

# Big Thunder Mage Graphics

This document details the graphical assets and animations for the "Big Thunder Mage" enemy in Noita.

## Sprite Definition

The main sprite definition for the Big Thunder Mage.

### Key Attributes:

*   **filename**: `data/enemies_gfx/thundermage_big.png` - The primary image file for the sprite.
*   **hotspots_filename**: `data/enemies_gfx/thundermage_big_hotspots.png` - The image file defining collision and interaction points.
*   **offset_x**: `14` - Horizontal offset for the sprite's origin.
*   **offset_y**: `30` - Vertical offset for the sprite's origin.
*   **default\_animation**: `"stand"` - The animation to play by default.

### Hotspots:

*   **hand**: Defines a point of interaction, likely for attacks or spellcasting.

## Animations

The Big Thunder Mage utilizes several `RectAnimation` elements to define its various movements and actions. Each animation is defined by a set of frames within the sprite sheet.

### Animation Table:

| Name         | Frame Count | Frame Width | Frame Height | Frames Per Row | Frame Wait | Pos Y | Loop | Notes                               |
| :----------- | :---------- | :---------- | :----------- | :------------- | :--------- | :---- | :--- | :---------------------------------- |
| `stand`      | 6           | 28          | 34           | 8              | 0.09       | 0     | Yes  | Idle animation.                     |
| `walk`       | 6           | 28          | 34           | 8              | 0.09       | 34    | Yes  | Walking animation.                  |
| `run`        | 6           | 28          | 34           | 8              | 0.09       | 34    | Yes  | Running animation (visually similar to walk). |
| `burn`       | 6           | 28          | 34           | 8              | 0.09       | 34    | Yes  | Burning animation.                  |
| `attack`     | 8           | 28          | 34           | 8              | 0.09       | 136   | No   | Primary attack animation.           |
| `fly_move`   | 4           | 28          | 34           | 8              | 0.09       | 102   | Yes  | Flying movement animation.          |
| `fly_idle`   | 4           | 28          | 34           | 8              | 0.09       | 68    | Yes  | Flying idle animation.              |
| `attack_ranged` | 8           | 28          | 34           | 10             | 0.07       | 136   | No   | Ranged attack animation.            |

### Animation Events:

Animations can trigger specific game events at certain frames.

*   **`walk`, `run`, `burn` animations**:
    *   **`step`**: Triggered at frame 2 and 5. `check_physics_material="1"` suggests this event might be related to footstep sounds or effects that depend on the ground material. `max_distance="500"` is a common value for such events.
*   **`attack` animation**:
    *   **`shoot_thunder`**: Triggered at frame 4. `check_physics_material="0"` indicates this event is not dependent on the ground material. This event is responsible for the actual thunder spell being cast.
*   **`attack_ranged` animation**:
    *   **`shoot_thunder`**: Triggered at frame 4. Similar to the `attack` animation's event, this also triggers the thunder spell.

**Note**: The `walk`, `run`, and `burn` animations share the same `pos_y` value (34), implying they are visually similar or use the same row of frames in the sprite sheet, differentiated by their animation name. The `attack` and `attack_ranged` animations also share a `pos_y` of 136.