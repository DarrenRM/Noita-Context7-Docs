---
title: Large Explosion Smoke Pillar Particle
category: entities
---

# Large Explosion Smoke Pillar Particle

This entity defines a large pillar of smoke particles, typically used as a visual effect for explosions in Noita. It utilizes a `SpriteParticleEmitterComponent` to generate smoke sprites and `LoadEntitiesComponent` to spawn additional smoke entities at specific times.

## Key Components and Attributes

### `VelocityComponent`

Controls the movement and physics of the particle.

*   `gravity_y`: Set to `0`, meaning the smoke particles are not affected by gravity and will drift upwards.
*   `air_friction`: Set to `4.0`, indicating a moderate amount of air resistance.

### `SimplePhysicsComponent`

A basic physics component, likely used in conjunction with `VelocityComponent` for movement.

### `SetStartVelocityComponent`

Determines the initial velocity of the emitted particles.

*   `randomize_speed.min`: Minimum initial speed of `50`.
*   `randomize_speed.max`: Maximum initial speed of `60`.
*   `randomize_angle.min`: Minimum initial angle of `-1.57` radians (approximately -90 degrees).
*   `randomize_angle.max`: Maximum initial angle of `-1.57` radians (approximately -90 degrees). This suggests particles are primarily launched upwards.

### `DieIfSpeedBelowComponent`

Defines a condition for the particle to be destroyed.

*   `min_speed`: Particles will be removed if their speed drops below `20`.

### `SpriteParticleEmitterComponent`

The core component responsible for emitting smoke particles.

*   `sprite_file`: Specifies the sprite to be used for the smoke particles: `data/particles/smoke_cloud_big.xml`.
*   `emission_interval_min_frames`: Minimum frames between emissions: `1`.
*   `emission_interval_max_frames`: Maximum frames between emissions: `2`. This results in frequent particle emissions.
*   `additive`: Set to `1`, meaning the smoke sprites will be rendered additively, contributing to brightness.
*   `emissive`: Set to `0`, indicating the particles themselves do not emit light.
*   `scale.x`, `scale.y`: Base scale of the smoke sprites, set to `1.0`.
*   `count_min`, `count_max`: Number of particles emitted per interval, ranging from `1` to `2`.
*   `sprite_random_rotation`: Set to `1`, allowing for random rotation of emitted sprites.
*   `randomize_scale.min_x`, `randomize_scale.max_x`, `randomize_scale.min_y`, `randomize_scale.max_y`: Small random variations in scale (`-0.1` to `0.1`) for a less uniform appearance.
*   `randomize_velocity.min_x`, `randomize_velocity.max_x`, `randomize_velocity.min_y`, `randomize_velocity.max_y`: Randomizes the velocity of emitted particles within a range of `-10` to `10` for both X and Y axes, creating a dispersed effect.
*   `randomize_position.min_x`, `randomize_position.max_x`, `randomize_position.min_y`, `randomize_position.max_y`: Randomizes the spawn position of particles within a range of `-10` to `10` for both X and Y axes, adding to the spread.
*   `randomize_animation_speed_coeff.min`, `randomize_animation_speed_coeff.max`: Randomizes the animation speed of the smoke sprites between `0.667` and `1.0`.
*   `velocity_always_away_from_center`: Set to `1`, causing particles to always move away from their emission center, contributing to the pillar shape.
*   `render_back`: Set to `1`, indicating these particles should be rendered behind other elements.

### `LoadEntitiesComponent`

This component is used to spawn other entities after a delay, creating a more complex and evolving smoke effect.

*   `count.min`, `count.max`: Spawns `1` entity per execution.
*   `entity_file`: Specifies the entity to load. This component is used multiple times to load `explosion_smoke_pillar_top_left.xml` and `explosion_smoke_pillar_top_right.xml`.
*   `kill_entity`: Set to `0`, meaning the parent entity (the smoke pillar itself) is not destroyed when these entities are loaded.
*   `timeout_frames`: Determines when the entity is loaded. This is varied to create a staggered effect:
    *   `10` frames for `explosion_smoke_pillar_top_left.xml`
    *   `10` frames for `explosion_smoke_pillar_top_right.xml`
    *   `12` frames for `explosion_smoke_pillar_top_left.xml`
    *   `12` frames for `explosion_smoke_pillar_top_right.xml`

This staggered loading of additional smoke entities likely creates a more dynamic and layered smoke effect that expands outwards and upwards.