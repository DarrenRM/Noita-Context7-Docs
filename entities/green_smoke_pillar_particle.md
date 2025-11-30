---
title: Green Smoke Pillar Particle
category: entities
---

# Green Smoke Pillar Particle

This entity defines a particle effect that creates a pillar of green smoke, typically used for explosions. It utilizes a `SpriteParticleEmitterComponent` to generate individual smoke sprites with randomized properties and `LoadEntitiesComponent` to spawn additional smoke entities at specific times.

## Key Components and Attributes

### `VelocityComponent`

Controls the movement and physics of the particle.

*   `gravity_y`: Set to `0`, meaning no gravity affects the smoke particles.
*   `air_friction`: Set to `4.0`, indicating moderate air resistance.

### `SimplePhysicsComponent`

Enables basic physics simulation for the particle.

### `SetStartVelocityComponent`

Determines the initial velocity of the emitted particles.

*   `randomize_speed.min`: Minimum initial speed of `50`.
*   `randomize_speed.max`: Maximum initial speed of `60`.
*   `randomize_angle.min`: Minimum initial angle of `-1.57` radians (approximately -90 degrees).
*   `randomize_angle.max`: Maximum initial angle of `-1.57` radians. This ensures particles are initially emitted upwards.

### `DieIfSpeedBelowComponent`

Defines a condition for particle destruction.

*   `min_speed`: Particles are destroyed if their speed drops below `25`.

### `SpriteParticleEmitterComponent`

The core component responsible for emitting the smoke sprites.

*   `sprite_file`: Specifies the sprite to be used, referencing `data/particles/smoke_cloud_green_$[1-4].xml`. The `$[1-4]` indicates that one of four variations of the green smoke cloud sprite will be randomly chosen.
*   `emission_interval_min_frames`: Minimum frames between emissions (`2`).
*   `emission_interval_max_frames`: Maximum frames between emissions (`2`). This creates a consistent emission rate.
*   `additive`: Set to `1`, meaning the sprite's color will be added to the background, creating a glowing effect.
*   `emissive`: Set to `0`, indicating the sprite itself does not emit light.
*   `scale.x`, `scale.y`: Base scale of `1.0` for the sprites.
*   `count_min`, `count_max`: Emits between `1` and `2` particles per emission.
*   `sprite_random_rotation`: Set to `1`, allowing sprites to have random rotations.
*   `randomize_scale.min_x`, `randomize_scale.max_x`, `randomize_scale.min_y`, `randomize_scale.max_y`: Randomizes the scale of emitted sprites by +/- `0.1` on both axes, creating variation.
*   `randomize_velocity.min_x`, `randomize_velocity.max_x`, `randomize_velocity.min_y`, `randomize_velocity.max_y`: Randomizes the velocity of emitted particles within a range of -4 to 4 on both axes, contributing to a dispersed effect.
*   `randomize_position.min_x`, `randomize_position.max_x`, `randomize_position.min_y`, `randomize_position.max_y`: Randomizes the spawn position of emitted particles within a range of -10 to 10 on both axes, creating a spread.
*   `randomize_animation_speed_coeff.min`, `randomize_animation_speed_coeff.max`: Randomizes the animation speed of the sprites between `0.667` and `1.0`, adding visual variety.
*   `velocity_always_away_from_center`: Set to `1`, causing particles to always move away from their emission point.
*   `render_back`: Set to `1`, ensuring these particles are rendered behind other elements.

### `LoadEntitiesComponent`

This component is used to spawn other entities after a delay, contributing to the pillar effect.

*   `count.min`, `count.max`: Spawns `1` entity per load.
*   `entity_file`: Specifies the entity to load. In this case, it loads `explosion_smoke_pillar_top_left_green.xml` and `explosion_smoke_pillar_top_right_green.xml`.
*   `kill_entity`: Set to `0`, meaning the parent entity is not destroyed after loading others.
*   `timeout_frames`: Determines when the entity is loaded.
    *   The first two `LoadEntitiesComponent` instances load the top-left and top-right smoke pillars after `10` frames.
    *   The next two instances load them again after `12` frames, creating a staggered and more dynamic pillar effect.