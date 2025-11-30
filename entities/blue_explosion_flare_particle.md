---
title: Blue Explosion Flare Particle
category: entities
---

# Blue Explosion Flare Particle

This entity defines a visual particle effect for a blue explosion flare. It utilizes a sprite and a particle emitter to create a dynamic visual.

## Key Components

### `_Transform`

This component controls the spatial properties of the entity.

*   **`scale.x`**: The scaling factor along the X-axis.
*   **`scale.y`**: The scaling factor along the Y-axis.

### `SpriteComponent`

This component handles the visual rendering of the particle.

*   **`alpha`**: The transparency of the sprite (0.2 means 20% opaque).
*   **`image_file`**: The path to the image file used for the sprite. This points to a generic `explosion_flare.xml`, suggesting the color might be determined by other means or a base texture.
*   **`kill_entity_after_finished`**: If set to "1", the entity will be destroyed once the sprite animation is complete.
*   **`additive`**: If set to "1", the sprite's color will be added to the background, creating a glowing effect.

### `ParticleEmitterComponent`

This component is responsible for generating and managing the individual particles that make up the flare.

*   **`emitted_material_name`**: Specifies the material of the particles being emitted. "plasma\_fading" suggests a material that fades over time.
*   **`lifetime_min` / `lifetime_max`**: The minimum and maximum duration (in seconds) each emitted particle will exist.
*   **`x_vel_min` / `x_vel_max`**: The minimum and maximum velocity along the X-axis for emitted particles.
*   **`y_vel_min` / `y_vel_max`**: The minimum and maximum velocity along the Y-axis for emitted particles.
*   **`count_min` / `count_max`**: The minimum and maximum number of particles emitted per emission cycle.
*   **`fade_based_on_lifetime`**: If "1", particles will fade out as their lifetime approaches zero.
*   **`area_circle_radius.max`**: The maximum radius of the circular area from which particles are emitted.
*   **`airflow_force` / `airflow_time` / `airflow_scale`**: These parameters control how airflow affects the emitted particles, influencing their movement over time.
*   **`emission_interval_min_frames` / `emission_interval_max_frames`**: Controls the frame rate at which particles are emitted. "1" means they are emitted every frame.
*   **`emit_cosmetic_particles`**: If "1", these particles are considered cosmetic and may not interact with gameplay mechanics as strongly.