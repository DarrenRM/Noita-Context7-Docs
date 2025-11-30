---
title: Zombie Weak Sprite Animations
category: data/enemies_gfx
---

# Zombie Weak Sprite Animations

This document details the sprite animations for the "zombie_weak" enemy in Noita, as defined in its XML configuration file. It focuses on key attributes of the main `<Sprite>` element and its contained `<RectAnimation>` elements.

## Sprite Attributes

The main `<Sprite>` tag defines the base properties for all animations.

| Attribute      | Value     | Description                                     |
|----------------|-----------|-------------------------------------------------|
| `filename`     | `data/enemies_gfx/zombie_weak.png` | Path to the sprite sheet image.                 |
| `offset_x`     | `8.5`     | Horizontal offset for sprite positioning.       |
| `offset_y`     | `15`      | Vertical offset for sprite positioning.         |
| `default_animation` | `stand`   | The animation to play by default.               |

## RectAnimation Elements

Each `<RectAnimation>` element defines a specific animation sequence.

### Stand Animation

*   **Name:** `stand`
*   **Description:** The default idle animation for the zombie.
*   **Key Attributes:**
    *   `frame_count`: 6
    *   `frame_height`: 19
    *   `frame_wait`: 0.2
    *   `frame_width`: 18
    *   `frames_per_row`: 8
    *   `pos_x`: 0
    *   `pos_y`: 1

### Walk Animation

*   **Name:** `walk`
*   **Description:** The animation for the zombie walking.
*   **Key Attributes:**
    *   `frame_count`: 6
    *   `frame_height`: 19
    *   `frame_wait`: 0.082
    *   `frame_width`: 18
    *   `frames_per_row`: 8
    *   `pos_x`: 0
    *   `pos_y`: 21
*   **Events:**
    *   `step` event triggered on frame 2 and 5, with `check_physics_material="1"`.

### Run Animation

*   **Name:** `run`
*   **Description:** The animation for the zombie running.
*   **Key Attributes:**
    *   `frame_count`: 6
    *   `frame_height`: 20
    *   `frame_wait`: 0.075
    *   `frame_width`: 19
    *   `frames_per_row`: 8
    *   `pos_x`: 0
    *   `pos_y`: 41
    *   `shrink_by_one_pixel`: 1
*   **Events:**
    *   `step` event triggered on frame 1 and 5, with `check_physics_material="1"`.

### Burn Animation

*   **Name:** `burn`
*   **Description:** The animation for the zombie when burning.
*   **Key Attributes:**
    *   `frame_count`: 6
    *   `frame_height`: 20
    *   `frame_wait`: 0.075
    *   `frame_width`: 19
    *   `frames_per_row`: 8
    *   `pos_x`: 0
    *   `pos_y`: 41
    *   `shrink_by_one_pixel`: 1
*   **Events:**
    *   `step` event triggered on frame 1 and 5, with `check_physics_material="1"`.

### Jump Up Animation

*   **Name:** `jump_up`
*   **Description:** The animation for the zombie jumping upwards.
*   **Key Attributes:**
    *   `frame_count`: 3
    *   `frame_height`: 20
    *   `frame_wait`: 0.082
    *   `frame_width`: 19
    *   `frames_per_row`: 8
    *   `loop`: 0 (not looping)
    *   `pos_x`: 0
    *   `pos_y`: 61
    *   `shrink_by_one_pixel`: 1
*   **Events:**
    *   `jump` event triggered on frame 0, with `check_physics_material="1"`.
    *   `voc_jump` event triggered on frame 0, with `check_physics_material="0"`.

### Jump Fall Animation

*   **Name:** `jump_fall`
*   **Description:** The animation for the zombie falling after a jump.
*   **Key Attributes:**
    *   `frame_count`: 2
    *   `frame_height`: 20
    *   `frame_wait`: 0.082
    *   `frame_width`: 19
    *   `frames_per_row`: 8
    *   `loop`: 0 (not looping)
    *   `pos_x`: 0
    *   `pos_y`: 81
    *   `shrink_by_one_pixel`: 1

### Land Animation

*   **Name:** `land`
*   **Description:** The animation for the zombie landing.
*   **Key Attributes:**
    *   `frame_count`: 3
    *   `frame_height`: 19
    *   `frame_wait`: 0.082
    *   `frame_width`: 18
    *   `frames_per_row`: 8
    *   `loop`: 0 (not looping)
    *   `pos_x`: 0
    *   `pos_y`: 101
*   **Events:**
    *   `land` event triggered on frame 0, with `check_physics_material="1"`.

### Attack Animation

*   **Name:** `attack`
*   **Description:** The animation for the zombie attacking.
*   **Key Attributes:**
    *   `frame_count`: 4
    *   `frame_height`: 20
    *   `frame_wait`: 0.075
    *   `frame_width`: 19
    *   `frames_per_row`: 8
    *   `loop`: 0 (not looping)
    *   `pos_x`: 0
    *   `pos_y`: 121
    *   `shrink_by_one_pixel`: 1
*   **Events:**
    *   `slash` event triggered on frame 2, with `check_physics_material="0"`.
    *   `voc_attack` event triggered on frame 4, with `check_physics_material="0"`.

### Hurt Animation

*   **Name:** `hurt`
*   **Description:** The animation for the zombie when taking damage.
*   **Key Attributes:**
    *   `frame_count`: 4
    *   `frame_height`: 19
    *   `frame_wait`: 0.07
    *   `frame_width`: 18
    *   `frames_per_row`: 8
    *   `loop`: 0 (not looping)
    *   `pos_x`: 0
    *   `pos_y`: 141

### Knockback Animation

*   **Name:** `knockback`
*   **Description:** The animation for the zombie being knocked back.
*   **Key Attributes:**
    *   `frame_count`: 1
    *   `frame_height`: 19
    *   `frame_wait`: 0.07
    *   `frame_width`: 18
    *   `frames_per_row`: 8
    *   `pos_x`: 0
    *   `pos_y`: 161

### Lower Head Animation

*   **Name:** `lower_head`
*   **Description:** Animation where the zombie lowers its head.
*   **Key Attributes:**
    *   `frame_count`: 3
    *   `frame_height`: 19
    *   `frame_wait`: 0.12
    *   `frame_width`: 18
    *   `frames_per_row`: 8
    *   `loop`: 0 (not looping)
    *   `pos_x`: 0
    *   `pos_y`: 181

### Eat Animation

*   **Name:** `eat`
*   **Description:** The animation for the zombie eating.
*   **Key Attributes:**
    *   `frame_count`: 4
    *   `frame_height`: 20
    *   `frame_wait`: 0.075
    *   `frame_width`: 19
    *   `frames_per_row`: 8
    *   `loop`: 0 (not looping)
    *   `pos_x`: 0
    *   `pos_y`: 201
    *   `shrink_by_one_pixel`: 1
*   **Events:**
    *   `eat` event triggered on frame 1, with `check_physics_material="0"`.
    *   `voc_eat` event triggered on frame 4, with `check_physics_material="0"`.

### Raise Head Animation

*   **Name:** `raise_head`
*   **Description:** Animation where the zombie raises its head.
*   **Key Attributes:**
    *   `frame_count`: 3
    *   `frame_height`: 19
    *   `frame_wait`: 0.12
    *   `frame_width`: 18
    *   `frames_per_row`: 8
    *   `loop`: 0 (not looping)
    *   `pos_x`: 0
    *   `pos_y`: 221

### Alert Animation

*   **Name:** `alert`
*   **Description:** The animation for the zombie becoming alert.
*   **Key Attributes:**
    *   `frame_count`: 5
    *   `frame_height`: 19
    *   `frame_wait`: 0.06
    *   `frame_width`: 18
    *   `frames_per_row`: 8
    *   `loop`: 0 (not looping)
    *   `pos_x`: 0
    *   `pos_y`: 241

### Swim Idle Animation

*   **Name:** `swim_idle`
*   **Description:** The idle animation for the zombie when swimming.
*   **Key Attributes:**
    *   `frame_count`: 6
    *   `frame_height`: 19
    *   `frame_wait`: 0.11
    *   `frame_width`: 18
    *   `frames_per_row`: 8
    *   `pos_x`: 0
    *   `pos_y`: 261
*   **Events:**
    *   `paddle` event triggered on frame 1 and 3, with `check_physics_material="0"`.

### Swim Move Animation

*   **Name:** `swim_move`
*   **Description:** The movement animation for the zombie when swimming.
*   **Key Attributes:**
    *   `frame_count`: 6
    *   `frame_height`: 19
    *   `frame_wait`: 0.09
    *   `frame_width`: 18
    *   `frames_per_row`: 8
    *   `pos_x`: 0
    *   `pos_y`: 261
*   **Events:**
    *   `paddle` event triggered on frame 1 and 3, with `check_physics_material="0"`.

### Jump Prepare Animation

*   **Name:** `jump_prepare`
*   **Description:** The animation for the zombie preparing to jump.
*   **Key Attributes:**
    *   `frame_count`: 3
    *   `frame_height`: 19
    *   `frame_wait`: 0.05
    *   `frame_width`: 18
    *   `frames_per_row`: 8
    *   `loop`: 0 (not looping)
    *   `pos_x`: 0
    *   `pos_y`: 281
*   **Events:**
    *   `jump_start` event triggered on frame 3, with `check_physics_material="0"`.
    *   `voc_jump_prepare` event triggered on frame 0, with `check_physics_material="0"`.