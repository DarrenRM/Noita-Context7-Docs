---
title: Monk Arm Entity
category: entities
---

# Monk Arm Entity

This document describes the `monk_arm.xml` entity, representing a detached monk's arm in Noita. It details its visual representation, hitbox, damage properties, lighting, and behavioral scripts.

## Core Components

### SpriteComponent
Defines the visual appearance of the monk arm.

*   **`image_file`**: `data/enemies_gfx/monk_hand.xml` - Specifies the graphical asset used for the arm.
*   **`rect_animation`**: `open` - Indicates the animation state to be displayed.
*   **`z_index`**: `-1` - Controls the rendering layer, placing it behind other elements.

### HitboxComponent
Defines the physical boundaries of the arm for interactions.

*   **`aabb_min_x`**: `-2`
*   **`aabb_max_x`**: `2`
*   **`aabb_min_y`**: `-9`
*   **`aabb_max_y`**: `-1`

### DamageModelComponent
Manages the arm's health and how it takes damage.

*   **`hp`**: `2.6` - The arm's health points.
*   **`blood_material`**: `spark` - The material produced when damaged.
*   **`blood_multiplier`**: `0` - No blood is generated.
*   **`create_ragdoll`**: `0` - Does not create a ragdoll upon destruction.

#### Damage Multipliers
Defines how much damage the arm takes from different sources.

| Damage Type   | Multiplier |
| :------------ | :--------- |
| `projectile`  | `0.0`      |
| `explosion`   | `0.1`      |
| `electricity` | `0.5`      |
| `fire`        | `0.5`      |
| `slice`       | `0.1`      |
| `ice`         | `0.1`      |

### LightComponent
Adds a light source emanating from the arm.

*   **`radius`**: `64` - The range of the light.
*   **`r`, `g`, `b`**: `168`, `168`, `255` - The RGB color of the light (a pale blue).

## Behavioral Components

### VariableStorageComponent
Stores variables for entity behavior.

*   **`name`**: `is_right`
*   **`value_bool`**: `1` - Indicates this is the right arm.

### LuaComponent (Movement)
Handles the arm's movement logic.

*   **`script_source_file`**: `data/scripts/animals/monk_hand_move.lua`
*   **`execute_every_n_frame`**: `1` - Executes the script every frame.

### LuaComponent (Attacking)
Manages the arm's attack behavior.

*   **`script_source_file`**: `data/scripts/animals/monk_hand_shoot.lua`
*   **`execute_every_n_frame`**: `60` - Executes the script every 60 frames.

### AudioLoopComponent
Plays a looping sound effect for the arm.

*   **`file`**: `data/audio/Desktop/animals.bank`
*   **`event_name`**: `animals/monk/hand_hover_loop`
*   **`auto_play`**: `1` - The sound starts automatically.