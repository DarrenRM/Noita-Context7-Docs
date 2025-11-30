---
title: Orbit Lasers Entity
category: entities
---

# Orbit Lasers Entity

This entity defines the behavior and properties of orbiting laser projectiles in Noita. It primarily relies on Lua scripts for its functionality.

## Key Components

### `VariableStorageComponent`

This component is used to store and manage variables associated with the orbiting laser.

*   **`_tags="orbit_projectile_type"`**: Identifies this as a type of orbit projectile.
    *   **`name="orbit_projectile_type"`**: The name of the variable.
    *   **`value_string="orbit_lasers_laser"`**: Specifies the projectile type as "orbit\_lasers\_laser".
*   **`_tags="orbit_projectile_speed"`**: Defines the speed of the orbiting projectile.
    *   **`name="orbit_projectile_speed"`**: The name of the variable.
    *   **`value_float="0"`**: Sets the initial speed to 0. The actual movement is likely handled by the associated Lua scripts.

### `LuaComponent`

These components attach Lua scripts to the entity, dictating its behavior.

*   **Script 1**:
    *   **`script_source_file="data/scripts/projectiles/orbit_projectile.lua"`**: This script likely handles the core logic for the orbiting projectile's movement and effects.
    *   **`execute_every_n_frame="1"`**: The script executes every frame.
    *   **`remove_after_executed="1"`**: The entity is removed after the script has executed once. This suggests the script itself might manage the projectile's lifecycle or spawn subsequent entities.

*   **Script 2**:
    *   **`script_source_file="data/scripts/projectiles/orbit_projectile_rotation.lua"`**: This script is responsible for handling the rotation of the orbiting projectile.
    *   **`execute_every_n_frame="1"`**: The script executes every frame.

## Summary

The `orbit_lasers.xml` entity is a foundational element for orbiting laser projectiles. It uses `VariableStorageComponent` to define its type and initial speed, and crucially relies on two `LuaComponent`s to manage its movement, rotation, and overall behavior through external Lua scripts. The `remove_after_executed="1"` on the primary `orbit_projectile.lua` suggests that the script itself is responsible for the projectile's duration or subsequent actions.