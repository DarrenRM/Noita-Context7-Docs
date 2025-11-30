---
title: Orbit Discs Projectile Base
category: entities
---

# Orbit Discs Projectile Base

This entity defines the base properties for projectiles that orbit a target. It primarily uses Lua scripts to manage their behavior.

## Key Components

### `VariableStorageComponent`

This component is used to store variables that can be accessed by Lua scripts.

*   **`_tags="orbit_projectile_type"`**: Identifies this as a projectile type for orbiting.
    *   `name="orbit_projectile_type"`
    *   `value_string="orbit_discs_disc"`: Specifies the projectile's internal type name.
*   **`_tags="orbit_projectile_speed"`**: Defines the initial speed of the orbiting projectile.
    *   `name="orbit_projectile_speed"`
    *   `value_float="0"`: Indicates the projectile starts with zero speed, likely controlled by scripts.

### `LuaComponent`

These components execute Lua scripts to define the projectile's behavior.

*   **`script_source_file="data/scripts/projectiles/orbit_projectile.lua"`**: This script likely handles the core logic of how the projectile orbits a target.
    *   `execute_every_n_frame="1"`: The script runs every frame.
    *   `remove_after_executed="1"`: The script is executed only once.
*   **`script_source_file="data/scripts/projectiles/orbit_projectile_rotation.lua"`**: This script is responsible for managing the rotation of the orbiting projectile.
    *   `execute_every_n_frame="1"`: The script runs every frame.