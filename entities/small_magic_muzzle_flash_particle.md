---
title: Small Magic Muzzle Flash Particle
category: entities
---

# Small Magic Muzzle Flash Particle

This entity defines a small, magical muzzle flash effect for projectiles. It utilizes two `ParticleEmitterComponent`s to generate different types of cosmetic particles, creating a dynamic visual.

## SpriteComponent

This component handles the visual representation of the muzzle flash itself.

*   **`image_file`**: Specifies the sprite sheet for the animation. It uses a pattern `muzzle_magic_small_0$[1-5].png` indicating 5 frames of animation.
*   **`rect_animation` / `next_rect_animation`**: Defines the animation sequence named "muzzle".
*   **`emissive`**: Set to `1`, meaning the sprite emits light.
*   **`additive`**: Set to `1`, indicating additive blending for a brighter, glowing effect.
*   **`kill_entity_after_finished`**: Set to `1`, the entity will be removed once its animation is complete.
*   **`offset_x` / `offset_y`**: Adjusts the sprite's position relative to the entity's origin.

## ParticleEmitterComponent (Spark Particles)

This emitter generates small, fast-moving "spark" particles.

*   **`emitted_material_name`**: `spark_blue` - the material used for these particles.
*   **`x_vel_min` / `x_vel_max`**: Defines the horizontal velocity range for the sparks. Note the unusual `max` being less than `min`, which can lead to interesting velocity behavior.
*   **`y_vel_min` / `y_vel_max`**: Defines the vertical velocity range.
*   **`count_min` / `count_max`**: The number of sparks emitted per burst.
*   **`lifetime_min` / `lifetime_max`**: The duration each spark particle exists.
*   **`create_real_particles`**: Set to `0`, meaning these are cosmetic particles and don't interact physically.
*   **`emit_cosmetic_particles`**: Set to `1`, confirming these are cosmetic.
*   **`is_emitting`**: Set to `1`, the emitter is active.

## ParticleEmitterComponent (Plasma Fading Particles)

This emitter generates larger, slower, fading "plasma" particles.

*   **`emitted_material_name`**: `plasma_fading` - the material used for these particles.
*   **`gravity.y`**: Set to `0`, these particles are not affected by gravity.
*   **`x_vel_min` / `x_vel_max`**: Defines the horizontal velocity range.
*   **`y_vel_min` / `y_vel_max`**: Defines the vertical velocity range.
*   **`count_min` / `count_max`**: The number of plasma particles emitted per burst.
*   **`lifetime_min` / `lifetime_max`**: The duration each plasma particle exists.
*   **`fade_based_on_lifetime`**: Set to `1`, particles will fade out as their lifetime progresses.
*   **`render_on_grid`**: Set to `1`, particles are rendered on the game grid.
*   **`airflow_force` / `airflow_time` / `airflow_scale`**: These parameters suggest the particles are influenced by airflow, adding a subtle drift effect.
*   **`create_real_particles`**: Set to `0`, cosmetic particles.
*   **`emit_cosmetic_particles`**: Set to `1`, confirming these are cosmetic.
*   **`emission_interval_min_frames` / `emission_interval_max_frames`**: Controls the timing between bursts of plasma particles.
*   **`is_emitting`**: Set to `1`, the emitter is active.