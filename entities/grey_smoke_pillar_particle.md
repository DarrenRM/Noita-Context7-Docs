---
title: Grey Smoke Pillar Particle
category: entities
---

# Grey Smoke Pillar Particle

This entity defines a particle effect that generates grey smoke pillars, typically used in explosions. It utilizes a `SpriteParticleEmitterComponent` to spawn smoke sprites and `LoadEntitiesComponent` to spawn additional entities that contribute to the pillar effect.

## Key Components and Attributes

### VelocityComponent
Controls the movement and air resistance of the particle.

*   `gravity_y="0"`: No vertical gravity applied.
*   `air_friction="4.0"`: Significant air friction, slowing down particles.

### SimplePhysicsComponent
Enables basic physics simulation for the particle.

### SetStartVelocityComponent
Determines the initial velocity of the spawned particles.

*   `randomize_speed.min="50"`: Minimum initial speed.
*   `randomize_speed.max="60"`: Maximum initial speed.
*   `randomize_angle.min="-1.57"`: Minimum initial angle (radians).
*   `randomize_angle.max="-1.57"`: Maximum initial angle (radians). This fixed angle suggests a directional emission.

### DieIfSpeedBelowComponent
Defines a condition for the particle to be destroyed.

*   `min_speed="25"`: The particle will be removed if its speed drops below this value.

### SpriteParticleEmitterComponent
The core component responsible for emitting smoke particles.

*   `sprite_file="data/particles/smoke_cloud_grey_$[1-4].xml"`: Specifies the sprite files to be used, with a pattern for variation.
*   `emission_interval_min_frames="2"`: Minimum frames between emissions.
*   `emission_interval_max_frames="2"`: Maximum frames between emissions. This creates a consistent emission rate.
*   `additive="1"`: Particles are rendered additively, contributing to brightness.
*   `emissive="0"`: Particles are not self-emissive.
*   `scale.x="1.0"`, `scale.y="1.0"`: Default scale of the emitted sprites.
*   `count_min="1"`, `count_max="2"`: Number of particles emitted per interval.
*   `sprite_random_rotation="1"`: Sprites will have random rotation.
*   `randomize_scale.min_x="-0.1"`, `randomize_scale.max_x="0.1"`: Random variation in X-axis scale.
*   `randomize_scale.min_y="-0.1"`, `randomize_scale.max_y="0.1"`: Random variation in Y-axis scale.
*   `randomize_velocity.min_y="-4"`, `randomize_velocity.max_y="4"`: Random variation in Y-axis velocity.
*   `randomize_velocity.min_x="-4"`, `randomize_velocity.max_x="4"`: Random variation in X-axis velocity.
*   `randomize_position.min_y="-10"`, `randomize_position.max_y="10"`: Random variation in emission position on the Y-axis.
*   `randomize_position.min_x="-10"`, `randomize_position.max_x="10"`: Random variation in emission position on the X-axis.
*   `randomize_animation_speed_coeff.min="0.667"`, `randomize_animation_speed_coeff.max="1.0"`: Random variation in the animation speed of the sprites.
*   `velocity_always_away_from_center="1"`: Particles are emitted outwards from the origin.
*   `render_back="1"`: Particles are rendered behind other elements.

### LoadEntitiesComponent
These components are used to spawn other entities at specific times, contributing to the overall pillar shape and duration.

*   **First Pair (timeout_frames="10"):**
    *   `entity_file="data/entities/particles/particle_explosion/explosion_smoke_pillar_top_left_grey.xml"`
    *   `entity_file="data/entities/particles/particle_explosion/explosion_smoke_pillar_top_right_grey.xml"`
    These load entities that likely form the upper parts of the smoke pillar shortly after the initial emission.
*   **Second Pair (timeout_frames="12"):**
    *   `entity_file="data/entities/particles/particle_explosion/explosion_smoke_pillar_top_left_grey.xml"`
    *   `entity_file="data/entities/particles/particle_explosion/explosion_smoke_pillar_top_right_grey.xml"`
    These load the same entities again, but with a slightly longer delay, potentially extending the visual effect or adding more density to the pillar.
*   `count.min="1"`, `count.max="1"`: Spawns one instance of the specified entity.
*   `kill_entity="0"`: The parent entity is not killed after spawning these.