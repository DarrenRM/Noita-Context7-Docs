---
title: Scavenger SMG Sprite and Animations
category: enemies_gfx
---

# Scavenger SMG Sprite and Animations

This document details the sprite and animation definitions for the "Scavenger SMG" enemy in Noita, as found in `scavenger_smg.xml`.

## Sprite Definition

The main sprite for the Scavenger SMG is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/enemies_gfx/scavenger_smg.png` - The primary image file for the enemy's graphics.
*   **hotspots_filename**: `data/enemies_gfx/scavenger_smg_hotspots.png` - An associated image file defining clickable or interactive areas.
*   **offset\_x**: `8` - Horizontal offset for the sprite's origin.
*   **offset\_y**: `15` - Vertical offset for the sprite's origin.
*   **default\_animation**: `"stand"` - The animation that plays by default when the enemy is idle.

### Hotspots:

Hotspots define specific points on the sprite, often used for targeting or interaction.

| Name | Color    |
| :--- | :------- |
| hand | `00ff0000` |
| eye  | `000000ff` |

## Animations

The Scavenger SMG utilizes several `RectAnimation` definitions to represent different actions and states. Each animation is a sequence of frames extracted from the sprite sheet.

### Animation Table:

| Name           | Frame Count | Frame Width | Frame Height | Frame Wait | Loop | Notes                               |
| :------------- | :---------- | :---------- | :----------- | :--------- | :--- | :---------------------------------- |
| `stand`        | 6           | 20          | 21           | 0.2        | 1    | Idle animation.                     |
| `walk`         | 6           | 20          | 21           | 0.082      | 1    | Walking animation.                  |
| `run`          | 6           | 20          | 21           | 0.082      | 1    | Copied from `walk`.                 |
| `burn`         | 6           | 20          | 21           | 0.06       | 1    | Burning animation.                  |
| `jump_up`      | 3           | 20          | 21           | 0.082      | 0    | Jump ascent.                        |
| `jump_fall`    | 2           | 20          | 21           | 0.082      | 0    | Falling after jump.                 |
| `attack_ranged`| 4           | 20          | 21           | 0.07       | 0    | Ranged attack animation.            |
| `fly_idle`     | 4           | 20          | 21           | 0.12       | 1    | Hovering/idle flying animation.     |
| `fly_move`     | 4           | 20          | 21           | 0.09       | 1    | Flying movement animation.          |
| `attack`       | 4           | 20          | 21           | 0.09       | 0    | Melee attack animation.             |
| `jump_prepare` | 3           | 20          | 21           | 0.1        | 0    | Preparation for jump.               |
| `throw`        | 4           | 20          | 21           | 0.09       | 0    | Throwing animation.                 |
| `reload`       | 6           | 20          | 21           | 0.05       | 0    | Reloading animation.                |

### Animation Details:

Each `RectAnimation` tag defines a specific animation.

#### `stand`

*   **name**: `stand`
*   **pos\_x**: `0`
*   **pos\_y**: `0`
*   **frame\_count**: `6`
*   **frame\_width**: `20`
*   **frame\_height**: `21`
*   **frame\_wait**: `0.2`
*   **frames\_per\_row**: `8`
*   **loop**: `1`

#### `walk`

*   **name**: `walk`
*   **pos\_x**: `0`
*   **pos\_y**: `21`
*   **frame\_count**: `6`
*   **frame\_width**: `20`
*   **frame\_height**: `21`
*   **frame\_wait**: `0.082`
*   **frames\_per\_row**: `8`
*   **loop**: `1`
*   **Events**:
    *   Frame `2`: `step` (probability 1, check\_physics\_material 1)
    *   Frame `5`: `step` (probability 1, check\_physics\_material 1)

#### `run`

*   **name**: `run`
*   **pos\_x**: `0`
*   **pos\_y**: `21`
*   **frame\_count**: `6`
*   **frame\_width**: `20`
*   **frame\_height**: `21`
*   **frame\_wait**: `0.082`
*   **frames\_per\_row**: `8`
*   **loop**: `1`
*   **Events**:
    *   Frame `2`: `step` (probability 1, check\_physics\_material 1)
    *   Frame `5`: `step` (probability 1, check\_physics\_material 1)
*   **Note**: This animation is a direct copy of `walk`.

#### `burn`

*   **name**: `burn`
*   **pos\_x**: `0`
*   **pos\_y**: `168`
*   **frame\_count**: `6`
*   **frame\_width**: `20`
*   **frame\_height**: `21`
*   **frame\_wait**: `0.06`
*   **frames\_per\_row**: `8`
*   **loop**: `1`
*   **Events**:
    *   Frame `2`: `step` (probability 1, check\_physics\_material 1)
    *   Frame `5`: `step` (probability 1, check\_physics\_material 1)
*   **Note**: This animation is a direct copy of `walk`.

#### `jump_up`

*   **name**: `jump_up`
*   **pos\_x**: `0`
*   **pos\_y**: `42`
*   **frame\_count**: `3`
*   **frame\_width**: `20`
*   **frame\_height**: `21`
*   **frame\_wait**: `0.082`
*   **frames\_per\_row**: `8`
*   **loop**: `0`
*   **Events**:
    *   Frame `0`: `jump` (probability 1, check\_physics\_material 1)

#### `jump_fall`

*   **name**: `jump_fall`
*   **pos\_x**: `0`
*   **pos\_y**: `63`
*   **frame\_count**: `2`
*   **frame\_width**: `20`
*   **frame\_height**: `21`
*   **frame\_wait**: `0.082`
*   **frames\_per\_row**: `8`
*   **loop**: `0`

#### `attack_ranged`

*   **name**: `attack_ranged`
*   **pos\_x**: `0`
*   **pos\_y**: `84`
*   **frame\_count**: `4`
*   **frame\_width**: `20`
*   **frame\_height**: `21`
*   **frame\_wait**: `0.07`
*   **frames\_per\_row**: `8`
*   **loop**: `0`
*   **Events**:
    *   Frame `1`: `shoot_bullet` (probability 1, check\_physics\_material 0)

#### `fly_idle`

*   **name**: `fly_idle`
*   **pos\_x**: `0`
*   **pos\_y**: `105`
*   **frame\_count**: `4`
*   **frame\_width**: `20`
*   **frame\_height**: `21`
*   **frame\_wait**: `0.12`
*   **frames\_per\_row**: `8`
*   **loop**: `1`

#### `fly_move`

*   **name**: `fly_move`
*   **pos\_x**: `0`
*   **pos\_y**: `126`
*   **frame\_count**: `4`
*   **frame\_width**: `20`
*   **frame\_height**: `21`
*   **frame\_wait**: `0.09`
*   **frames\_per\_row**: `8`
*   **loop**: `1`

#### `attack`

*   **name**: `attack`
*   **pos\_x**: `0`
*   **pos\_y**: `147`
*   **frame\_count**: `4`
*   **frame\_width**: `20`
*   **frame\_height**: `21`
*   **frame\_wait**: `0.09`
*   **frames\_per\_row**: `8`
*   **loop**: `0`
*   **Events**:
    *   Frame `1`: `hit` (probability 1, check\_physics\_material 0)

#### `jump_prepare`

*   **name**: `jump_prepare`
*   **pos\_x**: `0`
*   **pos\_y**: `189`
*   **frame\_count**: `3`
*   **frame\_width**: `20`
*   **frame\_height**: `21`
*   **frame\_wait**: `0.1`
*   **frames\_per\_row**: `8`
*   **loop**: `0`
*   **Events**:
    *   Frame `3`: `jump_start`

#### `throw`

*   **name**: `throw`
*   **pos\_x**: `0`
*   **pos\_y**: `147`
*   **frame\_count**: `4`
*   **frame\_width**: `20`
*   **frame\_height**: `21`
*   **frame\_wait**: `0.09`
*   **frames\_per\_row**: `8`
*   **loop**: `0`
*   **Events**:
    *   Frame `1`: `throw_release` (probability 1)

#### `reload`

*   **name**: `reload`
*   **pos\_x**: `0`
*   **pos\_y**: `210`
*   **frame\_count**: `6`
*   **frame\_width**: `20`
*   **frame\_height**: `21`
*   **frame\_wait**: `0.05`
*   **frames\_per\_row**: `8`
*   **loop**: `0`