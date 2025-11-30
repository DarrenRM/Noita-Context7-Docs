---
title: Small Explosion Flare Particle
category: entities/particles
---

# Small Explosion Flare Particle

This entity defines a small, short-lived particle effect that resembles a flare or spark explosion. It's primarily used for visual feedback in explosions.

## Key Components

### `_Transform`

This component controls the spatial properties of the entity.

*   `scale.x`: The scaling factor along the X-axis.
*   `scale.y`: The scaling factor along the Y-axis.

### `SpriteComponent`

This component handles the visual rendering of the particle.

*   `alpha`: The transparency of the sprite (0.2 means mostly transparent).
*   `image_file`: Specifies the texture file used for the sprite. In this case, it points to a particle definition itself, suggesting a self-referential or pre-defined particle texture.
*   `smooth_filtering`: Enables smooth filtering for the sprite, reducing pixelation.
*   `kill_entity_after_finished`: Ensures the entity is removed once its sprite animation or effect is complete.
*   `additive`: Enables additive blending, making the sprite's colors brighter when overlaid on other elements.
*   `emissive`: Indicates whether the sprite emits light. Set to `0` here, meaning it doesn't emit light itself.

### `ParticleEmitterComponent`

This component is responsible for generating and managing the individual particles that make up the flare effect.

*   `emitted_material_name`: The name of the material that the emitted particles will be. Here, it's set to "spark".
*   `gravity.y`: The gravitational pull on the emitted particles along the Y-axis. Set to `0.0` for no gravity.
*   `lifetime_min`: The minimum lifetime of an emitted particle in seconds.
*   `lifetime_max`: The maximum lifetime of an emitted particle in seconds.
*   `x_vel_min`, `x_vel_max`: The minimum and maximum velocity along the X-axis for emitted particles.
*   `y_vel_min`, `y_vel_max`: The minimum and maximum velocity along the Y-axis for emitted particles.
*   `count_min`, `count_max`: The minimum and maximum number of particles to emit per burst.
*   `render_on_grid`: Whether the particles should be rendered on the game grid.
*   `fade_based_on_lifetime`: If `1`, particles will fade out as their lifetime decreases.
*   `area_circle_radius.max`: The maximum radius of the circular area from which particles are emitted.
*   `cosmetic_force_create`: Controls if particles are created purely for cosmetic purposes.
*   `airflow_force`, `airflow_time`, `airflow_scale`: Parameters related to how airflow affects the emitted particles.
*   `emission_interval_min_frames`, `emission_interval_max_frames`: Controls the frame interval between particle emissions. Set to `1` for continuous emission.
*   `emit_cosmetic_particles`: If `1`, the emitter will generate cosmetic particles.
*   `is_emitting`: A flag to enable or disable particle emission.