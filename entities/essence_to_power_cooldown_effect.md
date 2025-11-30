---
title: Essence to Power Cooldown Effect
category: entities
---

# Essence to Power Cooldown Effect

This entity defines a visual and functional effect that plays when the "Essence to Power" spell is on cooldown. It primarily consists of a particle effect and a Lua script to manage its behavior.

## Key Components

### LifetimeComponent
This component dictates how long the cooldown effect will persist.

*   `lifetime`: The duration in seconds the effect will last.
    *   **Value:** `120`

### LuaComponent
This component links the entity to a Lua script that handles its logic.

*   `script_source_file`: Specifies the path to the Lua script.
    *   **Value:** `data/scripts/projectiles/essence_to_power_cooldown.lua`
*   `execute_on_removed`: Determines if the script should execute when the entity is removed.
    *   **Value:** `1` (True)
*   `execute_every_n_frame`: Controls how often the script logic is executed. A value of `-1` typically means it's not tied to frame updates in a regular interval.
    *   **Value:** `-1`

### ParticleEmitterComponent
This component defines the visual particle effect associated with the cooldown.

*   `emitted_material_name`: The material used for the particles.
    *   **Value:** `spark_blue_dark`
*   `x_pos_offset_min`, `x_pos_offset_max`, `y_pos_offset_min`, `y_pos_offset_max`: Define the area around the entity where particles can spawn.
    *   **Values:** `-12` to `12` for both X and Y.
*   `gravity.y`: The gravitational pull on the particles.
    *   **Value:** `0` (No gravity)
*   `x_vel_min`, `x_vel_max`, `y_vel_min`, `y_vel_max`: The range of initial velocities for the particles.
    *   **Values:** `-2` to `2` for both X and Y.
*   `count_min`, `count_max`: The number of particles emitted per emission.
    *   **Values:** `1` to `3`
*   `lifetime_min`, `lifetime_max`: The duration each individual particle will exist.
    *   **Values:** `0.8` to `2.0` seconds.
*   `emission_interval_min_frames`, `emission_interval_max_frames`: The frame interval between particle emissions.
    *   **Values:** `1` to `2` frames.
*   `emit_cosmetic_particles`: Whether to emit cosmetic particles (visual only).
    *   **Value:** `1` (True)
*   `render_on_grid`: Whether the particles should be rendered on the game grid.
    *   **Value:** `1` (True)