---
title: Sun Spot 1 Building
category: entities
---

# Sun Spot 1 Building

This entity defines a building that acts as a "sun spot," likely a visual effect or a component that emits light or particles.

## Key Components

### LuaComponent
This component links the entity to a Lua script that controls its behavior.

*   **`script_source_file`**: `data/scripts/buildings/sun/spot_1.lua` - The primary script governing this entity's logic.
*   **`execute_every_n_frame`**: `36` - The script will execute its logic every 36 frames.

### ParticleEmitterComponent
This component is responsible for emitting particles, likely for visual effects.

*   **`_tags`**: `buildup_particles` - Indicates these particles are part of a buildup or initialization effect.
*   **`emitted_material_name`**: `spark` - The material of the particles being emitted.
*   **`lifetime_min`**: `0.1` - Minimum lifetime of emitted particles in seconds.
*   **`lifetime_max`**: `1.5` - Maximum lifetime of emitted particles in seconds.
*   **`count_min`**: `20` - Minimum number of particles emitted per emission.
*   **`count_max`**: `20` - Maximum number of particles emitted per emission.
*   **`render_on_grid`**: `1` - Particles will be rendered on the game grid.
*   **`fade_based_on_lifetime`**: `1` - Particles will fade out as their lifetime decreases.
*   **`airflow_force`**: `4.1` - The force applied to particles by airflow.
*   **`airflow_time`**: `1.01` - The duration for which airflow affects particles.
*   **`airflow_scale`**: `0.05` - The scaling factor for airflow effects.
*   **`emission_interval_min_frames`**: `1` - Minimum frames between particle emissions.
*   **`emission_interval_max_frames`**: `1` - Maximum frames between particle emissions.
*   **`emit_cosmetic_particles`**: `1` - Indicates these are cosmetic particles, not gameplay-affecting.
*   **`image_animation_file`**: `data/particles/image_emitters/circle_reverse_64.png` - The texture file used for particle animation.
*   **`image_animation_speed`**: `4` - The speed of the particle image animation.
*   **`image_animation_loop`**: `0` - The particle animation does not loop.
*   **`render_ultrabright`**: `1` - Particles will be rendered with an ultrabright effect.
*   **`is_emitting`**: `0` - The particle emitter is initially not active.