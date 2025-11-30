---
title: Red Smoke Pillar Particle
category: entities
---

# Red Smoke Pillar Particle

This entity defines a red smoke pillar effect, typically used in explosions. It utilizes a `SpriteParticleEmitterComponent` to generate smoke particles and `LoadEntitiesComponent` to spawn additional smoke entities at specific times.

## Key Components and Attributes

### VelocityComponent
Controls the movement and physics of the particle.

*   `gravity_y="0"`: No vertical gravity applied.
*   `air_friction="4.0"`: Moderate air friction.

### SimplePhysicsComponent
Enables basic physics simulation for the entity.

### SetStartVelocityComponent
Initializes the velocity of the particles.

*   `randomize_speed.min="50"`: Minimum initial speed.
*   `randomize_speed.max="60"`: Maximum initial speed.
*   `randomize_angle.min="-1.57"`: Minimum initial angle (radians).
*   `randomize_angle.max="-1.57"`: Maximum initial angle (radians). This ensures particles are emitted upwards.

### DieIfSpeedBelowComponent
Determines when the particle should be removed.

*   `min_speed="25"`: The particle will be removed if its speed drops below this value.

### SpriteParticleEmitterComponent
The core component for generating smoke particles.

*   `sprite_file="data/particles/smoke_cloud_red_$[1-4].xml"`: Specifies the sprite files for the smoke particles. The `$[1-4]` indicates that one of four variations will be randomly chosen.
*   `emission_interval_min_frames="2"`: Minimum frames between particle emissions.
*   `emission_interval_max_frames="2"`: Maximum frames between particle emissions.
*   `additive="1"`: Particles are rendered additively, creating a glowing effect.
*   `emissive="0"`: Particles are not emissive.
*   `scale.x="1.0"`, `scale.y="1.0"`: Default scale of the particles.
*   `count_min="1"`, `count_max="2"`: Number of particles emitted per emission interval.
*   `sprite_random_rotation="1"`: Particles will have random rotation.
*   `randomize_scale.min_x="-0.1"`, `randomize_scale.max_x="0.1"`: Random variation in X-axis scale.
*   `randomize_scale.min_y="-0.1"`, `randomize_scale.max_y="0.1"`: Random variation in Y-axis scale.
*   `randomize_velocity.min_y="-4"`, `randomize_velocity.max_y="4"`: Random vertical velocity variation.
*   `randomize_velocity.min_x="-4"`, `randomize_velocity.max_x="4"`: Random horizontal velocity variation.
*   `randomize_position.min_y="-10"`, `randomize_position.max_y="10"`: Random positional offset for particle emission.
*   `randomize_position.min_x="-10"`, `randomize_position.max_x="10"`: Random positional offset for particle emission.
*   `randomize_animation_speed_coeff.min="0.667"`, `randomize_animation_speed_coeff.max="1.0"`: Random variation in particle animation speed.
*   `velocity_always_away_from_center="1"`: Particles are always emitted away from the center of the emitter.
*   `render_back="1"`: Particles are rendered behind other elements.

### LoadEntitiesComponent
These components spawn additional entities after a delay, contributing to the pillar effect.

*   `count.min="1"`, `count.max="1"`: Spawns one entity per component.
*   `entity_file`: Specifies the entity to load. In this case, it loads variations of smoke pillar tops.
*   `kill_entity="0"`: The main entity is not killed after spawning others.
*   `timeout_frames`: The delay in frames before the entity is spawned.

    *   `timeout_frames="10"`: Spawns top-left and top-right smoke entities after 10 frames.
    *   `timeout_frames="12"`: Spawns top-left and top-right smoke entities after 12 frames, creating a staggered effect.