---
title: Magic Launcher Trailer Muzzle Flash
category: entities/particles
---

# Magic Launcher Trailer Muzzle Flash

This entity defines a muzzle flash effect for a magic launcher, characterized by a trailer of red sparks. It utilizes two `ParticleEmitterComponent`s to create distinct visual elements.

## SpriteComponent

This component handles the visual representation of the muzzle flash itself.

*   **`image_file`**: Specifies the sprite sheet for the muzzle flash animation. It uses a numbered sequence (`muzzle_magic_launcher_large_0$[1-5].png`).
*   **`rect_animation` / `next_rect_animation`**: Defines the animation sequence for the muzzle flash.
*   **`alpha`**: Initial transparency of the sprite.
*   **`emissive`**: Makes the sprite emit light.
*   **`additive`**: Blends the sprite additively, common for light effects.
*   **`kill_entity_after_finished`**: Ensures the entity is removed once the animation completes.
*   **`offset_x` / `offset_y`**: Adjusts the sprite's position relative to the entity's origin.

## ParticleEmitterComponent (Primary Trailer)

This emitter is responsible for the main trail of red sparks.

*   **`emitted_material_name`**: The material used for the emitted particles (`spark_red`).
*   **`gravity.y`**: Applies a slight downward gravitational pull to the particles.
*   **`x_pos_offset_min`/`max` / `y_pos_offset_min`/`max`**: Defines the initial position spread of the particles.
*   **`x_vel_min`/`max` / `y_vel_min`/`max`**: Sets the initial velocity range for the particles. This emitter has a strong horizontal velocity.
*   **`direction_random_deg`**: Introduces a slight random deviation in the particle's direction.
*   **`count_min`/`max`**: The number of particles emitted per burst.
*   **`lifetime_min`/`max`**: The duration each particle exists.
*   **`fade_based_on_lifetime`**: Particles fade out as their lifetime ends.
*   **`create_real_particles`**: Set to `0`, indicating these are cosmetic particles.
*   **`render_on_grid`**: Particles are rendered on the game grid.
*   **`airflow_force` / `airflow_time` / `airflow_scale`**: Controls how particles interact with airflow.
*   **`friction`**: Slows down particles over time.
*   **`emission_interval_min_frames` / `max_frames`**: Set to `0`, meaning particles are emitted in a single burst.
*   **`is_emitting`**: Enables the emitter.

## ParticleEmitterComponent (Secondary Burst)

This emitter creates a more concentrated, shorter-lived burst of sparks.

*   **`emitted_material_name`**: The material used for the emitted particles (`spark_red`).
*   **`gravity.y`**: Set to `0`, meaning particles are not affected by gravity.
*   **`x_pos_offset_min`/`max` / `y_pos_offset_min`/`max`**: Particles originate directly from the emitter's offset.
*   **`x_vel_min`/`max` / `y_vel_min`/`max`**: Defines a moderate velocity range, with some upward and downward spread.
*   **`count_min`/`max`**: The number of particles emitted per burst.
*   **`lifetime_min`/`max`**: The duration each particle exists. This emitter's particles last longer.
*   **`fade_based_on_lifetime`**: Particles fade out as their lifetime ends.
*   **`create_real_particles`**: Set to `0`, indicating these are cosmetic particles.
*   **`render_on_grid`**: Particles are rendered on the game grid.
*   **`airflow_force` / `airflow_time` / `airflow_scale`**: Controls how particles interact with airflow.
*   **`friction`**: Slows down particles over time.
*   **`emission_interval_min_frames` / `max_frames`**: Particles are emitted in bursts over a short frame interval.
*   **`is_emitting`**: Enables the emitter.