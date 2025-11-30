---
title: Explosion Smoke Pillar Top Left Particle
category: entities/particles
---

# Explosion Smoke Pillar Top Left Particle

This entity defines a particle effect that generates smoke pillars originating from the top-left of an explosion. It's designed to create a visual representation of rising smoke.

## Key Components

### VelocityComponent
Controls the particle's movement and interaction with the environment.

*   `gravity_y="0"`: The particle is not affected by gravity in the y-axis.
*   `air_friction="7.0"`: Applies significant friction, slowing the particle down over time.

### SimplePhysicsComponent
Enables basic physics interactions for the particle.

### SetStartVelocityComponent
Determines the initial velocity of the emitted particles.

*   `randomize_speed.min="120"`: Minimum initial speed.
*   `randomize_speed.max="140"`: Maximum initial speed.
*   `randomize_angle.min="3.14159"`: Minimum initial angle (approximately 180 degrees).
*   `randomize_angle.max="3.34159"`: Maximum initial angle (slightly more than 180 degrees), directing particles generally upwards and slightly left.

### DieIfSpeedBelowComponent
Defines the condition under which the particle will be destroyed.

*   `min_speed="50"`: The particle will disappear if its speed drops below 50.

### SpriteParticleEmitterComponent
This is the core component responsible for emitting and managing the smoke particles.

*   `sprite_file="data/particles/smoke_cloud_tiny_$[1-4].xml"`: Specifies the sprite files used for the smoke particles. The `$[1-4]` indicates that one of four variations of `smoke_cloud_tiny` will be randomly chosen.
*   `emission_interval_min_frames="4"` and `emission_interval_max_frames="4"`: Particles are emitted every 4 frames, creating a consistent stream.
*   `additive="1"`: The particle's color is added to the background, common for smoke effects.
*   `emissive="0"`: The particle does not emit light.
*   `scale.x="1.0"` and `scale.y="1.0"`: The base scale of the emitted sprites.
*   `sprite_random_rotation="1"`: Each emitted sprite will have a random rotation.
*   `randomize_scale.min_x="-0.1"`, `randomize_scale.max_x="0.1"`, `randomize_scale.min_y="-0.1"`, `randomize_scale.max_y="0.1"`: Applies a slight random variation to the scale of each particle.
*   `randomize_velocity.min_y="-10"`, `randomize_velocity.max_y="0"`: Adds a slight upward random velocity component to the particles.
*   `randomize_velocity.min_x="-10"`, `randomize_velocity.max_x="-5"`: Adds a slight leftward random velocity component to the particles.
*   `randomize_position.min_y="-5"`, `randomize_position.max_y="5"`, `randomize_position.min_x="-5"`, `randomize_position.max_x="5"`: Introduces a small random offset to the emission position of each particle.
*   `randomize_animation_speed_coeff.min="0.667"` and `randomize_animation_speed_coeff.max="1.5"`: Varies the animation speed of the smoke sprites, making the effect more dynamic.
*   `render_back="1"`: Renders these particles behind other elements.