---
title: Boss Sky Damage Entity
category: entities
---

# Boss Sky Damage Entity

This entity defines the visual and functional aspects of the damage effect for the "Boss Sky" entity in Noita. It primarily handles particle effects and the duration of the damage state.

## Core Components

### LuaComponent
This component links the entity to its associated Lua script, `boss_sky_damage.lua`.

*   `script_source_file`: Specifies the path to the Lua script.
*   `execute_every_n_frame`: Controls how often the script's logic is executed. Set to `1` for continuous execution.

### LifetimeComponent
Determines how long this damage effect entity persists.

*   `lifetime`: The total duration in frames the entity will exist. Set to `90` frames. This is longer than the standard `SAVING_GRACE` (60 frames) to ensure the visual effect is visible during invulnerability.

### ParticleEmitterComponent
Manages the emission of cosmetic particles to visually represent the damage.

*   `emitted_material_name`: The material used for the emitted particles (`spark_red`).
*   `offset.x`, `offset.y`: The base position offset for particle emission.
*   `x_pos_offset_min`, `x_pos_offset_max`, `y_pos_offset_min`, `y_pos_offset_max`: Defines the random spread of particle emission around the offset.
*   `gravity.y`: The gravitational pull on the emitted particles. Set to `0` for no gravity.
*   `x_vel_min`, `x_vel_max`, `y_vel_min`, `y_vel_max`: The minimum and maximum velocity components for emitted particles.
*   `count_min`, `count_max`: The range for the number of particles emitted per emission cycle.
*   `fade_based_on_lifetime`: If `1`, particles will fade out as their lifetime decreases.
*   `lifetime_min`, `lifetime_max`: The minimum and maximum lifetime of individual particles.
*   `airflow_force`, `airflow_time`, `airflow_scale`: Parameters controlling how airflow affects the particles.
*   `create_real_particles`: If `0`, only cosmetic particles are created.
*   `emit_cosmetic_particles`: If `1`, cosmetic particles are emitted.
*   `render_on_grid`: If `1`, particles are rendered on the game grid.
*   `emission_interval_min_frames`, `emission_interval_max_frames`: The minimum and maximum frames between particle emission bursts.
*   `is_emitting`: If `1`, the particle emitter is active.

## VariableStorageComponent
This component is present but empty, suggesting it might be a placeholder or intended for future use in storing entity-specific variables.