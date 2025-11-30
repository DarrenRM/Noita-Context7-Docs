---
title: Forge Item Check Building
category: entities
---

# Forge Item Check Building

This entity represents a building component used in Noita for checking items within a forge. It primarily utilizes a Lua script for its functionality and emits particles for visual feedback.

## Key Components

### LuaComponent
This component defines the core logic of the building.

*   **`script_source_file`**: `data/scripts/buildings/forge_item_check.lua` - Specifies the Lua script responsible for the building's behavior.
*   **`execute_every_n_frame`**: `36` - The script will execute its logic every 36 frames.

### ParticleEmitterComponent
This component handles the visual particle effects associated with the building, specifically for a "buildup" effect.

*   **`_tags`**: `buildup_particles` - Identifies these particles as part of a buildup effect.
*   **`emitted_material_name`**: `spark_purple` - The material used for the emitted particles.
*   **`lifetime_min`**: `0.1` - Minimum lifetime of emitted particles in seconds.
*   **`lifetime_max`**: `1.5` - Maximum lifetime of emitted particles in seconds.
*   **`count_min`**: `20` - Minimum number of particles emitted per emission.
*   **`count_max`**: `20` - Maximum number of particles emitted per emission.
*   **`render_on_grid`**: `1` - Particles are rendered on the game grid.
*   **`fade_based_on_lifetime`**: `1` - Particles fade out as their lifetime decreases.
*   **`airflow_force`**: `4.1` - The force applied to particles by airflow.
*   **`airflow_time`**: `1.01` - The duration airflow affects particles.
*   **`airflow_scale`**: `0.05` - The scaling factor for airflow effects.
*   **`emission_interval_min_frames`**: `1` - Minimum frames between particle emissions.
*   **`emission_interval_max_frames`**: `1` - Maximum frames between particle emissions.
*   **`emit_cosmetic_particles`**: `1` - Emits cosmetic particles.
*   **`image_animation_file`**: `data/particles/image_emitters/circle_reverse_64.png` - The image file used for particle animation.
*   **`image_animation_speed`**: `4` - The speed of the particle image animation.
*   **`image_animation_loop`**: `0` - The particle animation does not loop.
*   **`is_emitting`**: `0` - The particle emitter is initially not emitting.