---
title: Explosion Smoke Pillar Particle
category: entities
---

# Explosion Smoke Pillar Particle

This entity defines the visual effect of smoke pillars rising from an explosion in Noita. It utilizes a particle emitter to generate smoke sprites and spawns additional entities to create a more dynamic and layered effect.

## Key Components and Attributes

### VelocityComponent
Controls the movement and physics of the particle.

*   `gravity_y="0"`: The particle is not affected by gravity in the y-axis, allowing it to rise.
*   `air_friction="4.0"`: Applies friction to slow down the particle's movement.

### SimplePhysicsComponent
A basic physics component, likely for simpler interactions.

### SetStartVelocityComponent
Determines the initial velocity of the particles.

*   `randomize_speed.min="50"`: Minimum initial speed.
*   `randomize_speed.max="60"`: Maximum initial speed.
*   `randomize_angle.min="-1.57"`: Minimum initial angle (in radians).
*   `randomize_angle.max="-1.57"`: Maximum initial angle (in radians). This fixed angle suggests particles are primarily launched upwards.

### DieIfSpeedBelowComponent
Defines when a particle should be removed.

*   `min_speed="25"`: Particles with a speed below this value will be destroyed.

### SpriteParticleEmitterComponent
The core component responsible for generating smoke particles.

*   `sprite_file="data/particles/smoke_cloud_$[1-4].xml"`: Specifies the sprite files to be used for the smoke. The `$[1-4]` indicates it will randomly pick one of four variations.
*   `emission_interval_min_frames="2"`: Minimum frames between particle emissions.
*   `emission_interval_max_frames="2"`: Maximum frames between particle emissions. This creates a consistent emission rate.
*   `additive="1"`: Particles are rendered additively, meaning their colors are added to what's behind them, creating a glowing or transparent effect.
*   `count_min="1"`: Minimum number of particles emitted per interval.
*   `count_max="2"`: Maximum number of particles emitted per interval.
*   `sprite_random_rotation="1"`: Randomly rotates each emitted sprite.
*   `randomize_scale.min_x/max_x`, `randomize_scale.min_y/max_y`: Introduces slight variations in the scale of emitted sprites.
*   `randomize_velocity.min/max_x/y`: Adds small random velocity changes to emitted particles, creating a more dispersed effect.
*   `randomize_position.min/max_x/y`: Offsets the emission position slightly for each particle.
*   `randomize_animation_speed_coeff.min/max`: Varies the animation speed of the smoke sprites.
*   `velocity_always_away_from_center="1"`: Ensures particles move away from their emission point, contributing to the pillar effect.
*   `render_back="1"`: Renders these particles behind other elements.

### LoadEntitiesComponent
These components are used to spawn other entities at specific times, creating a layered effect for the smoke pillar.

*   `entity_file`: The path to the entity file to be loaded. In this case, it loads `explosion_smoke_pillar_top_left.xml` and `explosion_smoke_pillar_top_right.xml`. These likely contain sprites or effects that form the upper parts of the smoke pillar.
*   `kill_entity="0"`: The spawned entity will not be immediately killed.
*   `timeout_frames`: The number of frames after which the spawned entity will be killed. This controls the duration and lifespan of the spawned elements. The different `timeout_frames` values (10 and 12) suggest staggered appearances of these top elements.