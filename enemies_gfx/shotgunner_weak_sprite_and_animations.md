---
title: Shotgunner Weak Sprite and Animations
category: data/enemies_gfx
---

# Shotgunner Weak Sprite and Animations

This document details the sprite and animation definitions for the "shotgunner_weak" enemy in Noita.

## Sprite Definition

The primary sprite for the shotgunner_weak is defined by the `<Sprite>` tag.

### Key Attributes:

*   **filename**: `data/enemies_gfx/shotgunner_weak.png` - The main image file for the sprite.
*   **hotspots_filename**: `data/enemies_gfx/shotgunner_hotspots.png` - The image file defining collision and interaction points.
*   **offset\_x**: `8` - Horizontal offset of the sprite's origin.
*   **offset\_y**: `7.5` - Vertical offset of the sprite's origin.
*   **default\_animation**: `stand` - The animation to play by default when the enemy spawns.

### Hotspots:

*   **name**: `hand`
    *   **color**: `ff0000` (Red) - Indicates a specific point of interaction, likely where projectiles are fired from.

## Animation Definitions

The `<RectAnimation>` tags define the various animations for the shotgunner_weak. Each animation is a sequence of frames from the sprite sheet.

### Key Animations:

| Animation Name    | Frame Count | Frame Width | Frame Height | Frame Wait (s) | Frames Per Row | Loop | Notes                                                              |
| :---------------- | :---------- | :---------- | :----------- | :------------- | :------------- | :--- | :----------------------------------------------------------------- |
| `stand`           | 6           | 17          | 17           | 0.16           | 6              | 1    | Idle animation.                                                    |
| `walk`            | 6           | 17          | 17           | 0.11           | 6              | 1    | Walking animation. Includes `step` events.                         |
| `run`             | 6           | 17          | 17           | 0.11           | 8              | 1    | Running animation (copied from `walk`). Includes `step` events.    |
| `burn`            | 6           | 17          | 17           | 0.08           | 8              | 1    | Burning animation (copied from `walk`). Includes `step` events.    |
| `attack`          | 6           | 17          | 17           | 0.07           | 8              | 0    | General attack animation. Triggers `hit` and `voc_attack` events. |
| `attack_ranged`   | 7           | 17          | 17           | 0.15           | 8              | 0    | Ranged attack animation. Triggers `shotgun_cock`, `shoot_bullet`, and `throw` events. |
| `jump_up`         | 3           | 17          | 17           | 0.09           | 8              | 0    | Jumping animation (ascending). Triggers `jump` and `voc_jump` events. |
| `jump_fall`       | 3           | 17          | 17           | 0.09           | 8              | 0    | Falling animation (after jump).                                    |
| `lower_head`      | 1           | 17          | 17           | 0.01           | 8              | 0    | Animation for lowering the head.                                   |
| `eat`             | 6           | 17          | 17           | 0.07           | 8              | 0    | Eating animation. Triggers `hit` and `voc_stomp` events.           |
| `raise_head`      | 1           | 17          | 17           | 0.01           | 8              | 0    | Animation for raising the head.                                    |
| `swim_idle`       | 6           | 17          | 17           | 0.12           | 8              | 1    | Swimming idle animation. Triggers `paddle` events.                 |
| `swim_move`       | 6           | 17          | 17           | 0.09           | 8              | 1    | Swimming movement animation. Triggers `paddle` events.             |
| `jump_prepare`    | 3           | 17          | 17           | 0.07           | 8              | 0    | Pre-jump animation. Triggers `jump_start` event.                   |
| `alert`           | 6           | 17          | 17           | 0.09           | 8              | 0    | Alert animation.                                                   |

### Animation Events:

Animations can trigger specific events at certain frames.

*   **`step`**: Occurs during `walk`, `run`, and `burn` animations. `check_physics_material="1"` suggests it might react to the ground type.
*   **`hit`**: Occurs during `attack` and `eat` animations. `check_physics_material="0"` indicates it's not dependent on the surface.
*   **`voc_attack`**: Occurs during `attack` animation. Likely related to a vocalization or specific attack action.
*   **`shotgun_cock`**: Occurs during `attack_ranged` animation. Indicates the weapon being readied.
*   **`shoot_bullet`**: Occurs during `attack_ranged` animation. The actual firing event.
*   **`throw`**: Occurs during `attack_ranged` animation. May indicate a thrown projectile or a general "throw" action.
*   **`jump`**: Occurs during `jump_up` animation. `check_physics_material="1"` suggests it might be influenced by the surface jumped from.
*   **`voc_jump`**: Occurs during `jump_up` animation. Likely a vocalization associated with jumping.
*   **`voc_stomp`**: Occurs during `eat` animation. Potentially a sound effect or action related to stomping.
*   **`jump_start`**: Occurs during `jump_prepare` animation. Marks the initiation of a jump.
*   **`paddle`**: Occurs during `swim_idle` and `swim_move` animations. Related to swimming actions.