---
title: Pink Smoke Pillar Particle
category: entities
---

# Pink Smoke Pillar Particle

This entity defines a particle effect that generates pink smoke pillars, typically used in explosions.

## Key Components

### VelocityComponent
Controls the particle's movement and how it interacts with the environment.

*   `gravity_y="0"`: The particle is not affected by gravity.
*   `air_friction="4.0"`: Applies a moderate amount of air friction, slowing the particle over time.

### SimplePhysicsComponent
Enables basic physics simulation for the particle.

### SetStartVelocityComponent
Determines the initial velocity of the emitted particles.

*   `randomize_speed.min="50"`: Minimum initial speed.
*   `randomize_speed.max="60"`: Maximum initial speed.
*   `randomize_angle.min="-1.57"`: Minimum initial angle (in radians).
*   `randomize_angle.max="-1.57"`: Maximum initial angle (in radians). This ensures particles are emitted upwards.

### DieIfSpeedBelowComponent
Defines a condition for the particle to be destroyed.

*   `min_speed="25"`: The particle will be removed if its speed drops below this value.

### SpriteParticleEmitterComponent
This is the core component responsible for emitting the smoke particles.

*   `sprite_file="data/particles/smoke_cloud_pink_$[1-4].xml"`: Specifies the sprite files to be used for the smoke. The `$[1-4]` indicates that one of four variations will be randomly chosen.
*   `emission_interval_min_frames="2"`: Minimum frames between particle emissions.
*   `emission_interval_max_frames="2"`: Maximum frames between particle emissions.
*   `additive="1"`: Particles are rendered additively, meaning their colors are combined.
*   `emissive="0"`: Particles do not emit light.
*   `scale.x="1.0"`, `scale.y="1.0"`: Base scale of the particles.
*   `count_min="1"`, `count_max="2"`: Number of particles emitted per emission event.
*   `sprite_random_rotation="1"`: Particles will have random rotation.
*   `randomize_scale.min_x="-0.1"`, `randomize_scale.max_x="0.1"`: Random variation in X-axis scale.
*   `randomize_scale.min_y="-0.1"`, `randomize_scale.max_y="0.1"`: Random variation in Y-axis scale.
*   `randomize_velocity.min_y="-4"`, `randomize_velocity.max_y="4"`: Random vertical velocity applied to emitted particles.
*   `randomize_velocity.min_x="-4"`, `randomize_velocity.max_x="4"`: Random horizontal velocity applied to emitted particles.
*   `randomize_position.min_y="-10"`, `randomize_position.max_y="10"`: Random offset in Y-axis position for emitted particles.
*   `randomize_position.min_x="-10"`, `randomize_position.max_x="10"`: Random offset in X-axis position for emitted particles.
*   `randomize_animation_speed_coeff.min="0.667"`, `randomize_animation_speed_coeff.max="1.0"`: Random variation in the animation speed of the particle sprites.
*   `velocity_always_away_from_center="1"`: Particles are always emitted away from the center of the emitter.
*   `render_back="1"`: Particles are rendered behind other elements.

### LoadEntitiesComponent
These components load other entities after a specified delay, creating a more complex visual effect.

*   `count.min="1"`, `count.max="1"`: Loads one instance of the specified entity.
*   `entity_file="..."`: The path to the entity to be loaded. In this case, it loads `explosion_smoke_pillar_top_left_pink.xml` and `explosion_smoke_pillar_top_right_pink.xml`.
*   `kill_entity="0"`: The parent entity is not killed after loading others.
*   `timeout_frames="10"` / `timeout_frames="12"`: The delay in frames before the entity is loaded. This creates a staggered effect for the smoke pillars.