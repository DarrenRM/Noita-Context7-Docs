---
title: Boss Alchemist Key Particles (First Alt)
category: entities
---

# Boss Alchemist Key Particles (First Alt)

This entity defines particle effects associated with the Boss Alchemist's "key" ability, specifically an alternative set. It utilizes two `ParticleEmitterComponent`s to generate different visual effects.

## Key Components

### InheritTransformComponent

This component is present to ensure the entity inherits transformations, likely for positioning and scaling within the game world. The `_tags` indicate it's active in various states: `first`, `enabled_in_hand`, `enabled_in_world`, and `item_identified`.

### ParticleEmitterComponent (Spark Blue)

This component is responsible for emitting blue sparks.

*   **`emitted_material_name`**: `spark_blue` - Specifies the material used for the emitted particles.
*   **`gravity.y`**: `0.0` - Particles are not affected by gravity in the Y-axis.
*   **`lifetime_min` / `lifetime_max`**: `1.5` / `8.5` - The duration each particle exists, ranging from 1.5 to 8.5 seconds.
*   **`count_min` / `count_max`**: `0` / `1` - The number of particles emitted per emission event, typically 0 or 1.
*   **`render_on_grid`**: `1` - Particles are rendered on the game grid.
*   **`fade_based_on_lifetime`**: `1` - Particles fade out as their lifetime decreases.
*   **`area_circle_radius.max`**: `6` - Particles are emitted within a circular area with a maximum radius of 6 units.
*   **`airflow_force` / `airflow_time` / `airflow_scale`**: `0.5` / `0.01` / `0.05` - Parameters controlling the effect of airflow on particles.
*   **`attractor_force`**: `2` - Particles are attracted with a force of 2.
*   **`emission_interval_min_frames` / `emission_interval_max_frames`**: `4` / `30` - The interval between particle emissions, ranging from 4 to 30 frames.
*   **`emit_cosmetic_particles`**: `1` - Emits cosmetic particles.
*   **`collide_with_grid`**: `0` - Particles do not collide with the game grid.
*   **`cosmetic_force_create`**: `1` - Forces the creation of cosmetic particles.
*   **`is_emitting`**: `1` - The emitter is active and emitting particles.

### ParticleEmitterComponent (Plasma Fading)

This component emits fading plasma effects.

*   **`emitted_material_name`**: `plasma_fading` - Specifies the material for these particles.
*   **`gravity.y`**: `0.0` - No gravity effect on the Y-axis.
*   **`lifetime_min` / `lifetime_max`**: `2.5` / `13.5` - Particle lifetime ranges from 2.5 to 13.5 seconds.
*   **`count_min` / `count_max`**: `0` / `1` - Typically 0 or 1 particle emitted per event.
*   **`render_on_grid`**: `1` - Particles are rendered on the game grid.
*   **`fade_based_on_lifetime`**: `1` - Particles fade out over their lifetime.
*   **`area_circle_radius.max`**: `16` - Particles are emitted within a larger circular area, up to 16 units in radius.
*   **`airflow_force` / `airflow_time` / `airflow_scale`**: `0.5` / `0.01` / `0.05` - Airflow parameters for these particles.
*   **`attractor_force`**: `2` - Particles are attracted with a force of 2.
*   **`emission_interval_min_frames` / `emission_interval_max_frames`**: `2` / `10` - Particles are emitted more frequently, with intervals between 2 and 10 frames.
*   **`emit_cosmetic_particles`**: `1` - Emits cosmetic particles.
*   **`collide_with_grid`**: `0` - Particles do not collide with the game grid.
*   **`cosmetic_force_create`**: `1` - Forces the creation of cosmetic particles.