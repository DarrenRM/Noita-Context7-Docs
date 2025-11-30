---
title: Scavenger Clusterbomb Sprite Animations
category: enemies_gfx
---

# Scavenger Clusterbomb Sprite Animations

This document details the sprite animations for the "Scavenger Clusterbomb" enemy in Noita, focusing on key attributes for AI-assisted modding.

## Sprite Sheet Information

The primary sprite sheet for this enemy is located at: `data/enemies_gfx/scavenger_clusterbomb.png`.

*   **Filename**: `data/enemies_gfx/scavenger_clusterbomb.png`
*   **Offset X**: `12` (Horizontal offset of the sprite on the sheet)
*   **Offset Y**: `21` (Vertical offset of the sprite on the sheet)
*   **Default Animation**: `stand` (The animation played when the enemy is idle)

## Key Animation Definitions

Each `RectAnimation` tag defines a specific animation. The following are the most important ones for understanding the enemy's visual behavior.

### Stand Animation

*   **Name**: `stand`
*   **Purpose**: Idle animation.
*   **Sprite Row**: `pos_y="0"`
*   **Frame Count**: `6`
*   **Frame Dimensions**: `frame_width="25"`, `frame_height="26"`
*   **Frame Delay**: `frame_wait="0.2"` (seconds per frame)
*   **Frames Per Row**: `8`
*   **Looping**: `loop="1"` (Yes)

### Walk Animation

*   **Name**: `walk`
*   **Purpose**: Movement animation.
*   **Sprite Row**: `pos_y="26"`
*   **Frame Count**: `6`
*   **Frame Dimensions**: `frame_width="25"`, `frame_height="26"`
*   **Frame Delay**: `frame_wait="0.095"` (seconds per frame)
*   **Frames Per Row**: `8`
*   **Looping**: `loop="1"` (Yes)
*   **Events**:
    *   `frame="0"`: `step` (with `probability="1"`, `check_physics_material="1"`)
    *   `frame="3"`: `step` (with `probability="1"`, `check_physics_material="1"`)

### Run Animation (Fake)

*   **Name**: `run`
*   **Purpose**: Appears to be a duplicate of the `walk` animation, likely for visual consistency or future implementation.
*   **Sprite Row**: `pos_y="26"`
*   **Frame Count**: `6`
*   **Frame Dimensions**: `frame_width="25"`, `frame_height="26"`
*   **Frame Delay**: `frame_wait="0.095"`
*   **Frames Per Row**: `8`
*   **Looping**: `loop="1"`
*   **Events**: Similar to `walk`.

### Burn Animation (Fake)

*   **Name**: `burn`
*   **Purpose**: Appears to be a duplicate of the `walk` animation, likely for visual consistency or future implementation.
*   **Sprite Row**: `pos_y="26"`
*   **Frame Count**: `6`
*   **Frame Dimensions**: `frame_width="25"`, `frame_height="26"`
*   **Frame Delay**: `frame_wait="0.095"`
*   **Frames Per Row**: `8`
*   **Looping**: `loop="1"`
*   **Events**: Similar to `walk`.

### Jump Up Animation

*   **Name**: `jump_up`
*   **Purpose**: Animation for the upward phase of a jump.
*   **Sprite Row**: `pos_y="52"`
*   **Frame Count**: `3`
*   **Frame Dimensions**: `frame_width="25"`, `frame_height="26"`
*   **Frame Delay**: `frame_wait="0.082"`
*   **Frames Per Row**: `8`
*   **Looping**: `loop="0"` (No)
*   **Events**:
    *   `frame="0"`: `jump` (with `probability="1"`, `check_physics_material="1"`)

### Jump Falling Animation

*   **Name**: `jump_fall`
*   **Purpose**: Animation for the falling phase of a jump.
*   **Sprite Row**: `pos_y="78"`
*   **Frame Count**: `3`
*   **Frame Dimensions**: `frame_width="25"`, `frame_height="26"`
*   **Frame Delay**: `frame_wait="0.082"`
*   **Frames Per Row**: `8`
*   **Looping**: `loop="0"` (No)

### Land Animation

*   **Name**: `land`
*   **Purpose**: Animation played upon landing after a jump.
*   **Sprite Row**: `pos_y="104"`
*   **Frame Count**: `2`
*   **Frame Dimensions**: `frame_width="25"`, `frame_height="26"`
*   **Frame Delay**: `frame_wait="0.082"`
*   **Frames Per Row**: `8`
*   **Looping**: `loop="0"` (No)
*   **Events**:
    *   `frame="0"`: `land` (with `probability="1"`, `check_physics_material="1"`)

### Attack Ranged Animation

*   **Name**: `attack_ranged`
*   **Purpose**: Animation for performing a ranged attack.
*   **Sprite Row**: `pos_y="182"`
*   **Frame Count**: `6`
*   **Frame Dimensions**: `frame_width="25"`, `frame_height="26"`
*   **Frame Delay**: `frame_wait="0.09"`
*   **Frames Per Row**: `8`
*   **Looping**: `loop="0"` (No)
*   **Events**:
    *   `frame="3"`: `shoot_bullet` (with `probability="1"`, `check_physics_material="0"`)

### Fly Idle Animation

*   **Name**: `fly_idle`
*   **Purpose**: Idle animation while hovering or flying.
*   **Sprite Row**: `pos_y="234"`
*   **Frame Count**: `4`
*   **Frame Dimensions**: `frame_width="25"`, `frame_height="26"`
*   **Frame Delay**: `frame_wait="0.12"`
*   **Frames Per Row**: `8`
*   **Looping**: `loop="1"` (Yes)

### Fly Move Animation

*   **Name**: `fly_move`
*   **Purpose**: Animation for movement while flying.
*   **Sprite Row**: `pos_y="130"`
*   **Frame Count**: `4`
*   **Frame Dimensions**: `frame_width="25"`, `frame_height="26"`
*   **Frame Delay**: `frame_wait="0.09"`
*   **Frames Per Row**: `8`
*   **Looping**: `loop="1"` (Yes)

### Attack Animation

*   **Name**: `attack`
*   **Purpose**: General attack animation (likely melee or close-range).
*   **Sprite Row**: `pos_y="156"`
*   **Frame Count**: `4`
*   **Frame Dimensions**: `frame_width="25"`, `frame_height="26"`
*   **Frame Delay**: `frame_wait="0.09"`
*   **Frames Per Row**: `8`
*   **Looping**: `loop="0"` (No)
*   **Events**:
    *   `frame="2"`: `hit` (with `probability="1"`, `check_physics_material="0"`)

### Jump Prepare Animation

*   **Name**: `jump_prepare`
*   **Purpose**: Animation played just before initiating a jump.
*   **Sprite Row**: `pos_y="208"`
*   **Frame Count**: `3`
*   **Frame Dimensions**: `frame_width="25"`, `frame_height="26"`
*   **Frame Delay**: `frame_wait="0.1"`
*   **Frames Per Row**: `8`
*   **Looping**: `loop="0"` (No)
*   **Events**:
    *   `frame="3"`: `jump_start`