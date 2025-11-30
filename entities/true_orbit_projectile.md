---
title: True Orbit Projectile
category: entities
---

# True Orbit Projectile

This entity defines a projectile that orbits its target. It utilizes a Lua script for its behavior and stores variables for distance and direction.

## Key Components

### LuaComponent
This component dictates the projectile's behavior through an external Lua script.

*   **`script_source_file`**: `data/scripts/projectiles/true_orbit.lua` - The path to the script that controls the orbiting logic.
*   **`execute_every_n_frame`**: `1` - The script's logic is executed every frame, allowing for smooth, continuous orbiting.

### VariableStorageComponent
These components are used to store and manage state for the orbiting projectile.

*   **`true_orbit_dist`**:
    *   **`name`**: `true_orbit_dist`
    *   **`value_float`**: `0` - Likely stores the current orbital distance from the target.
*   **`true_orbit_dir`**:
    *   **`name`**: `true_orbit_dir`
    *   **`value_float`**: `0` - Likely stores the current direction or angle of the orbit.