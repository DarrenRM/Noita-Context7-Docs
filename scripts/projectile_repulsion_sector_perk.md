---
title: Projectile Repulsion Sector Perk
category: data
---

---

# Projectile Repulsion Sector Perk

This entity defines the visual and functional aspects of the "Projectile Repulsion Sector" perk in Noita. It primarily uses particle emitters to create a visual effect and relies on a Lua script for its core behavior.

## Key Components

### InheritTransformComponent
This component is used to inherit the transform properties of another entity, specifically its position.

*   **`only_position="1"`**: Indicates that only the position is inherited, not rotation or scale.
*   **`Transform`**: Defines the relative position.
    *   **`position.x="0"`**: No horizontal offset.
    *   **`position.y="-8"`**: A vertical offset of -8 units.

### LuaComponent
This component links the entity to a Lua script that handles its logic.

*   **`script_source_file="data/scripts/perks/projectile_repulsion_sector.lua"`**: Specifies the path to the Lua script responsible for the perk's functionality.
*   **`execute_every_n_frame="2"`**: The script will execute every 2 frames, controlling the frequency of its updates.

### ParticleEmitterComponent (x3)
These components are responsible for generating visual particle effects. Each emitter has distinct parameters to create different visual layers.

#### Emitter 1 (Inner Glow/Spark)
This emitter creates a subtle, glowing spark effect.

*   **`emitted_material_name="spark_purple_bright"`**: The material used for the particles.
*   **`gravity.y="0.0"`**: Particles are not affected by gravity.
*   **`lifetime_min="0.1"`, `lifetime_max="0.5"`**: Particles exist for a short duration.
*   **`count_min="2"`, `count_max="4"`**: A small number of particles are emitted.
*   **`render_on_grid="1"`**: Particles are rendered on the game grid.
*   **`fade_based_on_lifetime="1"`**: Particles fade out as their lifetime ends.
*   **`area_circle_radius.max="50"`**: Particles are emitted within a radius of 50 units.
*   **`cosmetic_force_create="0"`**: Not a cosmetic-only particle.
*   **`airflow_force="0.5"`, `airflow_time="0.1"`, `airflow_scale="0.5"`**: Moderate airflow applied to particles.
*   **`emission_interval_min_frames="1"`, `emission_interval_max_frames="1"`**: Particles are emitted every frame.
*   **`emit_cosmetic_particles="1"`**: Emits cosmetic particles.
*   **`is_emitting="1"`**: This emitter is active.
*   **`area_circle_sector_degrees="30"`**: Particles are emitted within a 30-degree sector of the circle.

#### Emitter 2 (Outer Ring/Flicker)
This emitter creates a more diffuse, flickering effect at the edge of the sector.

*   **`emitted_material_name="spark_purple_bright"`**: The material used for the particles.
*   **`gravity.y="0.0"`**: Particles are not affected by gravity.
*   **`lifetime_min="0.02"`, `lifetime_max="0.05"`**: Very short-lived particles.
*   **`count_min="40"`, `count_max="60"`**: A moderate number of particles are emitted.
*   **`render_on_grid="1"`**: Particles are rendered on the game grid.
*   **`fade_based_on_lifetime="1"`**: Particles fade out as their lifetime ends.
*   **`area_circle_radius.min="50"`, `area_circle_radius.max="50"`**: Particles are emitted precisely at a radius of 50 units.
*   **`cosmetic_force_create="0"`**: Not a cosmetic-only particle.
*   **`airflow_force="0.3"`, `airflow_time="0.01"`, `airflow_scale="0.05"`**: Subtle airflow applied to particles.
*   **`emission_interval_min_frames="0"`, `emission_interval_max_frames="0"`**: Continuous emission.
*   **`emit_cosmetic_particles="1"`**: Emits cosmetic particles.
*   **`is_emitting="1"`**: This emitter is active.
*   **`area_circle_sector_degrees="30"`**: Particles are emitted within a 30-degree sector of the circle.

#### Emitter 3 (Main Repulsion Effect - Potentially for active state)
This emitter appears to be designed for a more intense visual effect, possibly when the perk is actively repelling projectiles. It is currently set to `is_emitting="0"`, suggesting it might be triggered by the Lua script.

*   **`emitted_material_name="spark_purple_bright"`**: The material used for the particles.
*   **`gravity.y="0.0"`**: Particles are not affected by gravity.
*   **`lifetime_min="0.3"`, `lifetime_max="1"`**: Longer-lived particles.
*   **`count_min="100"`, `count_max="160"`**: A large number of particles are emitted.
*   **`render_on_grid="1"`**: Particles are rendered on the game grid.
*   **`fade_based_on_lifetime="1"`**: Particles fade out as their lifetime ends.
*   **`area_circle_radius.min="50"`, `area_circle_radius.max="50"`**: Particles are emitted precisely at a radius of 50 units.
*   **`cosmetic_force_create="0"`**: Not a cosmetic-only particle.
*   **`airflow_force="2.8"`, `airflow_time="0.03"`, `airflow_scale="0.8"`**: Strong airflow applied to particles, suggesting a forceful effect.
*   **`emission_interval_min_frames="0"`, `emission_interval_max_frames="0"`**: Continuous emission.
*   **`emit_cosmetic_particles="1"`**: Emits cosmetic particles.
*   **`is_emitting="0"`**: This emitter is *not* active by default.
*   **`area_circle_sector_degrees="30"`**: Particles are emitted within a 30-degree sector of the circle.