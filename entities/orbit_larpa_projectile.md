---
title: Orbit Larpa Projectile
category: entities
---

# Orbit Larpa Projectile

This entity defines a projectile that orbits the player, specifically a "larpa" type. It utilizes Lua scripts for its behavior and rotation.

## Key Components

### `VariableStorageComponent`

This component stores variables related to the projectile's type and speed.

*   **`orbit_projectile_type`**:
    *   `name`: "orbit_projectile_type"
    *   `value_string`: "orbit_larpa" - Identifies this projectile as a larpa type for orbiting behavior.
*   **`orbit_projectile_speed`**:
    *   `name`: "orbit_projectile_speed"
    *   `value_float`: "0" - While set to 0 here, this likely influences the orbiting speed when used in conjunction with scripts.

### `LuaComponent`

These components execute Lua scripts to define the projectile's functionality.

*   **Orbiting Behavior**:
    *   `script_source_file`: "data/scripts/projectiles/orbit_projectile.lua"
    *   `execute_every_n_frame`: "1" - Executes the script every frame.
    *   `remove_after_executed`: "1" - The script runs once and then the component is removed.
*   **Orbiting Rotation**:
    *   `script_source_file`: "data/scripts/projectiles/orbit_projectile_rotation.lua"
    *   `execute_every_n_frame`: "1" - Executes the script every frame.

## Summary

The `orbit_larpa.xml` entity is a simple projectile definition that relies heavily on external Lua scripts (`orbit_projectile.lua` and `orbit_projectile_rotation.lua`) to manage its orbiting movement and rotation around the player. The `VariableStorageComponent` is used to tag and potentially influence the projectile's behavior.