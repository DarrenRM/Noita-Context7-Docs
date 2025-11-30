---
title: Explosion Flare Particle
category: entities
---

# Explosion Flare Particle

This entity defines a particle effect that simulates a "flare" explosion. It's primarily used for visual feedback when certain explosions occur.

## Key Components

### SpriteComponent
This component handles the visual representation of the particle.

*   **`alpha`**: Controls the transparency of the particle (0.2 means mostly transparent).
*   **`image_file`**: Specifies the texture used for the particle. In this case, it references itself, suggesting a custom texture or a placeholder.
*   **`kill_entity_after_finished`**: Ensures the particle entity is removed once its animation or effect is complete.
*   **`additive`**: Enables additive blending, making the particle brighter when it overlaps with other bright elements.

### ParticleEmitterComponent
This component is responsible for generating and managing the individual particles that make up the flare effect.

*   **`emitted_material_name`**: The type of material the emitted particles will be (e.g., "spark").
*   **`lifetime_min` / `lifetime_max`**: The minimum and maximum duration each individual particle will exist.
*   **`x_vel_min` / `x_vel_max`**: The range of horizontal velocity for emitted particles.
*   **`y_vel_min` / `y_vel_max`**: The range of vertical velocity for emitted particles.
*   **`count_min` / `count_max`**: The number of particles to emit per emission event.
*   **`fade_based_on_lifetime`**: Causes particles to fade out as their lifetime decreases.
*   **`area_circle_radius.max`**: The maximum radius of the circular area from which particles are emitted.
*   **`airflow_force` / `airflow_time` / `airflow_scale`**: Parameters that influence how particles are affected by simulated airflow.
*   **`emit_cosmetic_particles`**: Indicates that this emitter is intended for cosmetic effects.

### _Transform
This component defines the spatial properties of the entity.

*   **`scale.x` / `scale.y`**: The scaling factor applied to the entity. Here, it's scaled up by 10 in both dimensions.