---
title: Orbit Fireballs Entity
category: entities
---

# Orbit Fireballs Entity

This entity defines the configuration for "orbit fireballs" projectiles in Noita. It primarily relies on Lua scripts to manage their behavior and appearance.

## Key Components

### `VariableStorageComponent`

This component is used to store and pass variables to the associated scripts.

*   **`_tags="orbit_projectile_type"`**: Identifies this as a configuration for the type of projectile.
    *   `name="orbit_projectile_type"`
    *   `value_string="orbit_fireballs_fireball"`: Specifies the internal name or identifier for the fireball projectile.
*   **`_tags="orbit_projectile_speed"`**: Defines the initial speed of the orbiting projectile.
    *   `name="orbit_projectile_speed"`
    *   `value_float="0"`: Indicates that the projectile starts with zero speed, likely meaning its movement is entirely dictated by the orbiting script.

### `LuaComponent`

These components execute Lua scripts to define the entity's behavior.

*   **Script 1**:
    *   `script_source_file="data/scripts/projectiles/orbit_projectile.lua"`: This script likely handles the core logic of the orbiting projectile, including its movement pattern, targeting, and damage.
    *   `execute_every_n_frame="1"`: The script executes every frame.
    *   `remove_after_executed="1"`: The script is removed after its first execution. This suggests the core orbiting logic is set up once and then continues to run via other mechanisms or the script itself manages its lifecycle.
*   **Script 2**:
    *   `script_source_file="data/scripts/projectiles/orbit_projectile_rotation.lua"`: This script is responsible for managing the rotation of the orbiting projectile.
    *   `execute_every_n_frame="1"`: The script executes every frame.

## Summary

The `orbit_fireballs.xml` entity is a foundational configuration for a specific type of projectile in Noita. It leverages two Lua scripts: one for the projectile's primary behavior and another for its rotation. The `VariableStorageComponent` is used to pass essential parameters like the projectile's type and initial speed to these scripts. The `value_float="0"` for speed suggests that the orbiting script is solely responsible for imparting motion.