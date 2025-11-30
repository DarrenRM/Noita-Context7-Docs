---
title: Projectile Eater Sector
category: entities
---

# Projectile Eater Sector

This entity defines the visual and functional components of the "Projectile Eater" perk's sector effect in Noita. It primarily uses particle emitters to create a visual representation of the perk's area of effect, which is designed to absorb projectiles.

## Core Components

### InheritTransformComponent
This component is used to inherit the transform properties (position, rotation, scale) from another entity. In this case, it's used to offset the entity's position slightly.

*   **`only_position="1"`**: Indicates that only the position should be inherited, not rotation or scale.
*   **`Transform position.x="0" position.y="-8"`**: Sets the relative position of this entity to be 0 units on the X-axis and -8 units on the Y-axis from its parent.

### LuaComponent
This component links the entity to a Lua script that handles its behavior.

*   **`script_source_file="data/scripts/perks/projectile_eater_sector.lua"`**: Specifies the path to the Lua script responsible for the perk's logic.
*   **`execute_every_n_frame="1"`**: The script will execute every frame, allowing for real-time updates and interactions.

## ParticleEmitterComponent (x3)

This entity utilizes three `ParticleEmitterComponent` instances to create different visual effects associated with the Projectile Eater sector. All emitters are configured to emit `spark_red` particles and have a `cosmetic_force_create="0"`, meaning they are not intended to be physically interactive beyond their visual representation. The `area_circle_sector_degrees="30"` attribute on all emitters suggests a directional or limited arc of emission.

### Emitter 1: Core Visual Effect

This emitter creates the primary visual representation of the sector.

*   **`emitted_material_name="spark_red"`**: The type of particle to emit.
*   **`gravity.y="0.0"`**: Particles are not affected by gravity.
*   **`lifetime_min="0.1"`, `lifetime_max="0.5"`**: Particles exist for a short duration.
*   **`count_min="1"`, `count_max="2"`**: A small number of particles are emitted per interval.
*   **`render_on_grid="1"`**: Particles are rendered on the game grid.
*   **`fade_based_on_lifetime="1"`**: Particles fade out as their lifetime ends.
*   **`area_circle_radius.max="24"`**: Particles are emitted within a radius of up to 24 units.
*   **`airflow_force="0.5"`, `airflow_time="0.1"`, `airflow_scale="0.5"`**: Particles are influenced by airflow.
*   **`emission_interval_min_frames="1"`, `emission_interval_max_frames="1"`**: Particles are emitted every frame.
*   **`emit_cosmetic_particles="1"`**: Emits particles that are purely visual.
*   **`is_emitting="1"`**: This emitter is active.
*   **`area_circle_sector_degrees="30"`**: Emission is limited to a 30-degree sector.

### Emitter 2: Subtle Detail

This emitter adds finer, more fleeting visual details.

*   **`emitted_material_name="spark_red"`**: The type of particle to emit.
*   **`gravity.y="0.0"`**: Particles are not affected by gravity.
*   **`lifetime_min="0.02"`, `lifetime_max="0.05"`**: Particles have a very short lifespan.
*   **`count_min="10"`, `count_max="20"`**: A moderate number of particles are emitted.
*   **`render_on_grid="1"`**: Particles are rendered on the game grid.
*   **`fade_based_on_lifetime="1"`**: Particles fade out as their lifetime ends.
*   **`area_circle_radius.min="24"`, `area_circle_radius.max="24"`**: Particles are emitted precisely at a radius of 24 units.
*   **`airflow_force="0.3"`, `airflow_time="0.01"`, `airflow_scale="0.05"`**: Particles have minimal airflow influence.
*   **`emission_interval_min_frames="0"`, `emission_interval_max_frames="0"`**: Particles are emitted continuously (effectively every frame).
*   **`emit_cosmetic_particles="1"`**: Emits particles that are purely visual.
*   **`is_emitting="1"`**: This emitter is active.
*   **`area_circle_sector_degrees="30"`**: Emission is limited to a 30-degree sector.

### Emitter 3: Infrequent Burst (Likely for activation/deactivation or special events)

This emitter appears to be designed for less frequent, more impactful particle bursts.

*   **`emitted_material_name="spark_red"`**: The type of particle to emit.
*   **`gravity.y="0.0"`**: Particles are not affected by gravity.
*   **`lifetime_min="0.3"`, `lifetime_max="1"`**: Particles have a longer lifespan.
*   **`count_min="40"`, `count_max="60"`**: A large number of particles are emitted.
*   **`render_on_grid="1"`**: Particles are rendered on the game grid.
*   **`fade_based_on_lifetime="1"`**: Particles fade out as their lifetime ends.
*   **`area_circle_radius.min="24"`, `area_circle_radius.max="24"`**: Particles are emitted precisely at a radius of 24 units.
*   **`airflow_force="2.8"`, `airflow_time="0.03"`, `airflow_scale="0.8"`**: Particles are strongly influenced by airflow, suggesting a more dynamic visual effect.
*   **`emission_interval_min_frames="0"`, `emission_interval_max_frames="0"`**: Particles are emitted continuously (effectively every frame).
*   **`emit_cosmetic_particles="1"`**: Emits particles that are purely visual.
*   **`is_emitting="0"`**: **Crucially, this emitter is inactive by default.** It would likely be triggered by the associated Lua script for specific events.
*   **`area_circle_sector_degrees="30"`**: Emission is limited to a 30-degree sector.