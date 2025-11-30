---
title: Necromancer Shop Spawn Entity
category: entities
---

# Necromancer Shop Spawn Entity

This entity defines the visual and functional aspects of the Necromancer Shop spawn point. It primarily handles visual effects and the logic for spawning the actual Necromancer Shop entity.

## Key Components

### LightComponent

This component adds a persistent light source to the spawn point.

*   **`radius`**: The maximum reach of the light.
*   **`fade_out_time`**: How long the light takes to fade.
*   **`r`, `g`, `b`**: The RGB color values of the light, creating a distinct purple hue.
*   **`offset_y`**: Adjusts the vertical position of the light source.

### SpriteParticleEmitterComponent

This component generates a continuous stream of purple, swirling particles around the spawn point, contributing to its magical atmosphere.

*   **`sprite_file`**: Specifies the texture file for the particles, using a sequence of purple whirl images.
*   **`lifetime`**: The duration each particle exists.
*   **`color.a`**: Initial transparency of the particles.
*   **`color_change.a`**: How the transparency changes over the particle's lifetime (fades out).
*   **`velocity_slowdown`**: How quickly particles lose their speed.
*   **`angular_velocity`**: The speed at which particles rotate.
*   **`scale_velocity`**: How the scale of particles changes over their lifetime.
*   **`emission_interval_min_frames`, `emission_interval_max_frames`**: Controls the rate at which new particles are emitted.
*   **`count_min`, `count_max`**: The number of particles emitted per interval.
*   **`randomize_position`**: Adds slight random offsets to particle spawn positions.
*   **`randomize_velocity`**: Adds random velocity to particles for a more dynamic effect.
*   **`randomize_lifetime`**: Varies the lifespan of individual particles.
*   **`randomize_angular_velocity`**: Varies the rotation speed of particles.
*   **`randomize_rotation`**: Varies the initial rotation of particles.

### LuaComponent

This component links the entity to a Lua script responsible for its behavior.

*   **`script_source_file`**: The path to the Lua script that manages the Necromancer Shop spawning logic.
*   **`execute_every_n_frame`**: Determines how frequently the Lua script's logic is executed, controlling the spawn rate.

### LoadEntitiesComponent (Commented Out)

This component, currently commented out, would be responsible for loading the actual Necromancer Shop entity.

*   **`count.min`, `count.max`**: The number of entities to load.
*   **`timeout_frames`**: How long to wait before attempting to load.
*   **`kill_entity`**: Whether to destroy this spawn entity after loading.
*   **`entity_file`**: The path to the entity XML file to be loaded (e.g., `data/entities/animals/necromancer_shop.xml`).