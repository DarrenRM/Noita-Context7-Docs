---
title: Medium Explosion Flare Particle
category: entities/particles
---

# Medium Explosion Flare Particle

This entity defines a particle effect that simulates a medium-sized explosion flare. It's primarily composed of a sprite and a particle emitter.

## Key Components

### SpriteComponent

This component defines the visual appearance of the flare.

*   **`alpha`**: Controls the transparency of the sprite. A value of `0.2` makes it semi-transparent.
*   **`image_file`**: Specifies the texture file used for the sprite. In this case, it points to `data/particles/explosion_flare.xml`, suggesting a reusable flare texture.
*   **`smooth_filtering`**: When set to `1`, enables smooth filtering for the sprite, reducing pixelation.
*   **`kill_entity_after_finished`**: Set to `1`, this ensures the entity is removed from the game once the sprite animation or effect is complete.
*   **`additive`**: When `1`, the sprite's color is added to the background, creating a glowing effect.
*   **`emissive`**: Set to `0`, meaning the sprite does not emit its own light.

### ParticleEmitterComponent

This component is responsible for generating and managing the individual particles that make up the flare.

*   **`emitted_material_name`**: Defines the material of the particles being emitted. Here, it's set to `"spark"`.
*   **`lifetime_min` / `lifetime_max`**: The minimum and maximum duration (in seconds) each emitted particle will exist.
*   **`x_vel_min` / `x_vel_max`**: The minimum and maximum horizontal velocity applied to emitted particles.
*   **`y_vel_min` / `y_vel_max`**: The minimum and maximum vertical velocity applied to emitted particles.
*   **`count_min` / `count_max`**: The range for the number of particles emitted in a single burst.
*   **`fade_based_on_lifetime`**: When `1`, particles will fade out as their lifetime decreases.
*   **`area_circle_radius.max`**: The maximum radius of the circular area from which particles are emitted.
*   **`airflow_force` / `airflow_time` / `airflow_scale`**: These attributes control how particles are affected by airflow, influencing their movement over time.
*   **`emission_interval_min_frames` / `emission_interval_max_frames`**: Controls the frame interval between particle emissions. Set to `1` for continuous emission.
*   **`emit_cosmetic_particles`**: When `1`, particles are considered cosmetic and may not interact with physics in the same way as gameplay entities.
*   **`is_emitting`**: Set to `1` to enable particle emission.

### _Transform

This component handles the spatial transformation of the entity.

*   **`scale.x` / `scale.y`**: Defines the scaling factor for the entity along the X and Y axes. Here, it's scaled up by `5` in both directions, making the flare larger.