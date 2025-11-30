---
title: Greed Curse Effect Particles
category: entities
---

# Greed Curse Effect Particles

This entity defines the visual particle effects associated with the "Greed Curse" in Noita. It utilizes multiple `ParticleEmitterComponent` and `SpriteParticleEmitterComponent` to generate various visual elements, primarily sparks and gold particles, to signify the curse's presence.

## Key Components

### ParticleEmitterComponent (Yellow Sparks)

This component is responsible for emitting yellow sparks.

*   **`_tags`**: "curse" - Identifies this as part of the curse system.
*   **`emitted_material_name`**: "spark\_yellow" - Specifies the material for the emitted particles.
*   **`lifetime_min` / `lifetime_max`**: Controls the duration each spark exists.
*   **`area_circle_radius.max`**: Defines the maximum radius of the emission area.
*   **`emission_interval_min_frames` / `emission_interval_max_frames`**: Determines the frequency of particle emissions.
*   **`airflow_force` / `airflow_time` / `airflow_scale`**: Influences how particles react to air currents.
*   **`attractor_force`**: A force that pulls particles towards a specific point.

### ParticleEmitterComponent (Gold Particles)

This component emits particles representing gold.

*   **`_tags`**: "curse" - Identifies this as part of the curse system.
*   **`emitted_material_name`**: "gold" - Specifies the material for the emitted particles.
*   **`lifetime_min` / `lifetime_max`**: Controls the duration each gold particle exists.
*   **`area_circle_radius.max`**: Defines the maximum radius of the emission area.
*   **`emission_interval_min_frames` / `emission_interval_max_frames`**: Determines the frequency of particle emissions.
*   **`airflow_force` / `airflow_time` / `airflow_scale`**: Influences how particles react to air currents.
*   **`attractor_force`**: A force that pulls particles towards a specific point.

### SpriteParticleEmitterComponent (Shine 08)

This component emits sprite-based particles, specifically using `shine_08.xml`.

*   **`_tags`**: "curse" - Identifies this as part of the curse system.
*   **`sprite_file`**: "data/particles/shine\_08.xml" - The sprite asset used for these particles.
*   **`lifetime` / `randomize_lifetime.min` / `randomize_lifetime.max`**: Controls the particle's lifespan.
*   **`emission_interval_min_frames` / `emission_interval_max_frames`**: Controls the emission rate.
*   **`count_min` / `count_max`**: The number of particles emitted per interval.
*   **`additive` / `emissive`**: Rendering properties for the sprites.
*   **`sprite_random_rotation`**: Applies random rotation to emitted sprites.
*   **`gravity.y`**: The gravitational pull on the particles.
*   **`randomize_velocity.min_y` / `randomize_velocity.max_y` / `randomize_velocity.min_x` / `randomize_velocity.max_x`**: Defines the initial velocity range for particles.
*   **`randomize_position.min_x` / `randomize_position.max_x` / `randomize_position.min_y` / `randomize_position.max_y`**: Defines the area where particles can spawn relative to the emitter.
*   **`velocity_slowdown`**: How quickly particles lose velocity.
*   **`randomize_animation_speed_coeff.min` / `randomize_animation_speed_coeff.max`**: Controls the animation speed of the sprites.

### SpriteParticleEmitterComponent (Shine 07 - Bigger Blinkys)

Similar to the previous sprite emitter, but uses `shine_07.xml` and has slightly different parameters, potentially for a more pronounced visual effect.

*   **`_tags`**: "curse" - Identifies this as part of the curse system.
*   **`sprite_file`**: "data/particles/shine\_07.xml" - The sprite asset used for these particles.
*   **`lifetime` / `randomize_lifetime.min` / `randomize_lifetime.max`**: Controls the particle's lifespan.
*   **`emission_interval_min_frames` / `emission_interval_max_frames`**: Controls the emission rate.
*   **`count_min` / `count_max`**: The number of particles emitted per interval.
*   **`additive` / `emissive`**: Rendering properties for the sprites.
*   **`sprite_random_rotation`**: Applies random rotation to emitted sprites.
*   **`gravity.y`**: The gravitational pull on the particles.
*   **`randomize_velocity.min_y` / `randomize_velocity.max_y` / `randomize_velocity.min_x` / `randomize_velocity.max_x`**: Defines the initial velocity range for particles.
*   **`randomize_position.min_x` / `randomize_position.max_x` / `randomize_position.min_y` / `randomize_position.max_y`**: Defines the area where particles can spawn relative to the emitter.
*   **`velocity_slowdown`**: How quickly particles lose velocity.
*   **`randomize_animation_speed_coeff.min` / `randomize_animation_speed_coeff.max`**: Controls the animation speed of the sprites.

## Summary

This entity is a collection of particle emitters designed to create a distinct visual flair for the Greed Curse. Modders can adjust parameters within these components to alter the appearance, behavior, and intensity of the curse's visual effects. For instance, changing `emitted_material_name` could swap the type of particles, while modifying `lifetime` or `gravity` would change how they move and persist.