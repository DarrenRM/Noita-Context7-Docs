---
title: Projectile Repulsion Field Particle Emitter
category: entities
---

# Projectile Repulsion Field Particle Emitter

This entity defines the visual effects for the "Projectile Repulsion Field" perk in Noita. It utilizes two `ParticleEmitterComponent`s to generate distinct particle behaviors.

## Key Components

### InheritTransformComponent

This component is used to inherit the transform properties of another entity, specifically its position.

*   **`only_position="1"`**: Indicates that only the position should be inherited, not rotation or scale.
*   **`Transform`**:
    *   **`position.x="0"`**: Sets the x-coordinate of the inherited position.
    *   **`position.y="-8"`**: Sets the y-coordinate of the inherited position.

### ParticleEmitterComponent (Primary)

This emitter is responsible for the initial burst of particles when the repulsion field is active.

*   **`emitted_material_name="spark_purple"`**: Specifies the material used for the emitted particles.
*   **`gravity.y="0.0"`**: Particles have no vertical gravity.
*   **`lifetime_min="0.06"`, `lifetime_max="0.12"`**: Defines the lifespan of individual particles in seconds.
*   **`count_min="15"`, `count_max="25"`**: The number of particles emitted per burst.
*   **`render_on_grid="1"`**: Particles are rendered on the game grid.
*   **`fade_based_on_lifetime="1"`**: Particles fade out as their lifetime decreases.
*   **`area_circle_radius.min="50"`, `area_circle_radius.max="50"`**: Particles are emitted within a circular area of radius 50.
*   **`airflow_force="0.3"`, `airflow_time="0.01"`, `airflow_scale="0.05"`**: Subtle airflow effects applied to the particles.
*   **`emit_cosmetic_particles="1"`**: Emits cosmetic particles.
*   **`is_emitting="1"`**: The emitter is active.

### ParticleEmitterComponent (Secondary)

This emitter creates a more sustained and dynamic particle effect, likely representing the ongoing repulsion.

*   **`emitted_material_name="spark_purple"`**: Same material as the primary emitter.
*   **`gravity.y="0.0"`**: No vertical gravity.
*   **`lifetime_min="0.4"`, `lifetime_max="0.7"`**: Longer lifespan for these particles.
*   **`count_min="5"`, `count_max="10"`**: Fewer particles emitted per interval.
*   **`render_on_grid="1"`**: Particles are rendered on the game grid.
*   **`fade_based_on_lifetime="1"`**: Particles fade out over their lifetime.
*   **`area_circle_radius.min="1"`, `area_circle_radius.max="30"`**: Particles are emitted within a smaller, more variable circular area.
*   **`airflow_force="1.5"`, `airflow_time="1.9"`, `airflow_scale="0.15"`**: Stronger and longer-lasting airflow effects.
*   **`emission_interval_min_frames="1"`, `emission_interval_max_frames="1"`**: Particles are emitted every frame.
*   **`emit_cosmetic_particles="1"`**: Emits cosmetic particles.
*   **`draw_as_long="1"`**: Particles are drawn for their full duration.
*   **`x_vel_min="-1"`, `x_vel_max="1"`, `y_vel_min="-1"`, `y_vel_max="1"`**: Initial velocity range for particles.
*   **`is_emitting="1"`**: The emitter is active.
*   **`velocity_always_away_from_center="100"`**: Particles are consistently pushed away from the emitter's center with a force of 100.