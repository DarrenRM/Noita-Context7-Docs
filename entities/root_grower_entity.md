---
title: Root Grower Entity
category: entities
---

# Root Grower Entity

This entity represents a "root grower" in Noita, a prop that can spread and grow roots when certain conditions are met. It's primarily controlled by Lua scripts that manage its growth behavior, branching, and eventual fruiting.

## Key Components

### HitboxComponent
Defines the physical boundaries of the root grower.

*   `aabb_min_x`, `aabb_max_x`: Horizontal bounds (-3 to 3).
*   `aabb_min_y`, `aabb_max_y`: Vertical bounds (-3 to 3).

### DamageModelComponent
Manages how the root grower takes damage and its properties.

*   `hp`: Health points (1).
*   `fire_damage_amount`: Amount of damage from fire (0.5).
*   `fire_probability_of_ignition`: Chance to ignite from fire (0.5).
*   `materials_damage`: Whether it's damaged by materials (1 - yes).
*   `materials_that_damage`: List of materials that damage it (`acid`, `lava`).
*   `materials_how_much_damage`: Damage amount from specified materials (0.004 for each).
*   `blood_material`: Material created when damaged (`grass`).
*   `blood_multiplier`: Multiplier for blood creation (2).

### VelocityComponent
Controls velocity, though it's disabled for this entity's primary function.

*   `updates_velocity`: Whether velocity is updated (0 - no).
*   `gravity_y`: Gravity effect (0 - none).

### ParticleEmitterComponent
Responsible for emitting `root_growth` particles, visually representing growth.

*   `_tags`: Tagged as `grow`.
*   `emitted_material_name`: The material emitted (`root_growth`).
*   `count_min`, `count_max`: Number of particles emitted per interval (6).
*   `lifetime_min`, `lifetime_max`: Duration of emitted particles (0.1 to 0.3 seconds).
*   `emission_interval_min_frames`, `emission_interval_max_frames`: How often particles are emitted (1 frame).
*   `is_emitting`: Whether emission is active (1 - yes).

### CollisionTriggerComponent
Detects when the player enters its radius to initiate growth.

*   `width`, `height`, `radius`: Trigger dimensions (150).
*   `required_tag`: The tag required to trigger it (`player_unit`).
*   `remove_component_when_triggered`: Removes this component after triggering (1 - yes).

### LuaComponent (Multiple)
These are the core logic controllers for the root grower.

1.  **Growth Movement Script:**
    *   `_tags`: Tagged as `grow`.
    *   `script_source_file`: `data/scripts/props/root_grower_spread.lua`.
    *   `execute_every_n_frame`: How often the script runs (5 frames).

2.  **Branching Script:**
    *   `_tags`: Tagged as `grow`.
    *   `script_source_file`: `data/scripts/props/root_grower_split.lua`.
    *   `execute_every_n_frame`: How often the script runs (16 frames).

3.  **Fruiting Script:**
    *   `script_source_file`: `data/scripts/props/root_grower_fruit.lua`.
    *   `execute_on_removed`: Executes when the entity is removed (1 - yes).

4.  **Initiation Script:**
    *   `script_collision_trigger_hit`: Script to run when collision trigger is hit (`data/scripts/props/root_grower_start.lua`).
    *   `script_damage_received`: Script to run when damage is received (`data/scripts/props/root_grower_start.lua`).
    *   `remove_after_executed`: Removes this component after it runs (1 - yes).

### LifetimeComponent
Determines how long the root grower exists while actively growing.

*   `_tags`: Tagged as `grow`.
*   `lifetime`: Duration in frames (250).

### AudioLoopComponent
Plays a sound effect while the root grower is active.

*   `_tags`: Tagged as `grow`.
*   `file`: Audio bank (`data/audio/Desktop/misc.bank`).
*   `event_name`: Sound event (`misc/root_grow`).
*   `auto_play`: Starts playing automatically (1 - yes).