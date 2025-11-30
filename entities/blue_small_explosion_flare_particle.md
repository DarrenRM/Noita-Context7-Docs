---
title: Blue Small Explosion Flare Particle
category: entities
---

# Blue Small Explosion Flare Particle

This entity defines a small, blue, explosive flare particle effect. It's designed to be spawned as part of larger explosion effects.

## Key Components

### SpriteComponent
This component handles the visual representation of the particle.

*   `image_file`: Specifies the sprite sheet or texture to use. In this case, it references `data/particles/explosion_flare_small.xml`, suggesting a pre-defined small flare sprite.
*   `alpha`: Controls the transparency of the sprite, set to `0.2` for a semi-transparent effect.
*   `kill_entity_after_finished`: Set to `1`, meaning the particle entity will be destroyed once its sprite animation or emission is complete.
*   `additive`: Set to `1`, indicating that the sprite's color will be added to the background, common for bright or glowing effects.
*   `emissive`: Set to `0`, meaning the sprite itself does not emit light, but rather relies on its color and alpha for its visual impact.

### ParticleEmitterComponent
This component is responsible for generating and managing the individual particles that make up the flare effect.

*   `emitted_material_name`: Defines the material of the particles being emitted, set to `"plasma_fading"`. This suggests the particles will behave like fading plasma.
*   `lifetime_min`, `lifetime_max`: Sets the duration each emitted particle will exist, ranging from `0.5` to `2.5` seconds.
*   `x_vel_min`, `x_vel_max`, `y_vel_min`, `y_vel_max`: Define the initial velocity range for emitted particles, creating a spread effect.
*   `count_min`, `count_max`: Determines the number of particles emitted per emission cycle, between `10` and `20`.
*   `fade_based_on_lifetime`: Set to `1`, meaning particles will fade out as their lifetime approaches zero.
*   `area_circle_radius.max`: The maximum radius of the circular area from which particles are emitted, set to `18`.
*   `airflow_force`, `airflow_time`, `airflow_scale`: These parameters control how airflow affects the emitted particles, creating a subtle drift.
*   `emission_interval_min_frames`, `emission_interval_max_frames`: Set to `1`, meaning particles are emitted continuously without delay between frames.
*   `emit_cosmetic_particles`: Set to `1`, indicating that these are cosmetic particles, not affecting gameplay mechanics directly.

### _Transform
This component defines the spatial properties of the entity.

*   `scale.x`, `scale.y`: The entity is scaled up by `10` in both the X and Y directions, making the visual effect larger.