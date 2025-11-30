---
title: Knockback Star Particle
category: entities
---

# Knockback Star Particle

This entity defines a particle effect that appears as a "knockback star." It's primarily visual and designed to be emitted by other entities to indicate a knockback effect.

## Key Components

### VelocityComponent
Controls the particle's movement physics.

*   `gravity_y="0"`: No vertical gravity applied.
*   `mass="0"`: Zero mass, meaning it's not affected by physics in a traditional sense.
*   `air_friction="12.0"`: High air friction, causing it to slow down quickly.

### SimplePhysicsComponent
A placeholder component, likely indicating it doesn't require complex physics simulation.

### SetStartVelocityComponent
Determines the initial velocity of the particle.

*   `randomize_speed.min="20"`: Minimum initial speed.
*   `randomize_speed.max="120"`: Maximum initial speed.
*   `randomize_angle.min="0"`: Minimum initial direction angle (in radians).
*   `randomize_angle.max="6.283185"`: Maximum initial direction angle (full circle).

### SpriteComponent
Defines the visual appearance of the particle.

*   `image_file="data/particles/knockback_star_$[1-4].xml"`: Uses a set of four different sprite files, randomly selected.
*   `additive="0"`: Not an additive blend.
*   `emissive="0"`: Not emissive (doesn't glow on its own).
*   `alpha="1"`: Fully opaque.
*   `z_index="-1.2"`: Rendered behind most other elements.

### LifetimeComponent
Determines how long the particle exists.

*   `lifetime="40"`: The particle will exist for 40 game frames.
*   `randomize_lifetime.min="0"`: No randomization for minimum lifetime.
*   `randomize_lifetime.max="0"`: No randomization for maximum lifetime.

## Commented-Out Components

The following `ParticleEmitterComponent` sections are commented out. They likely represent alternative or older implementations of particle emission logic that are not currently active for this specific entity.

### ParticleEmitterComponent (Commented Out - First Instance)
This emitter was likely responsible for creating a burst of cosmetic particles.

*   `emitted_material_name="spark"`: Emits particles of the "spark" material.
*   `count_min="4"`, `count_max="8"`: Emits between 4 and 8 particles.
*   `velocity_always_away_from_center="80"`: Particles are pushed away from the emitter's center.
*   `lifetime_min="0.9"`, `lifetime_max="3.2"`: Particles last between 0.9 and 3.2 seconds.
*   `create_real_particles="0"`: Does not create actual game entities, only visual effects.
*   `emit_cosmetic_particles="1"`: Emits cosmetic particles.
*   `emitter_lifetime_frames="2"`: The emitter itself only lasts for 2 frames.

### ParticleEmitterComponent (Commented Out - Second Instance)
This emitter was likely responsible for creating a smaller, more delayed burst of particles.

*   `emitted_material_name="spark"`: Emits particles of the "spark" material.
*   `delay_frames="35"`: Starts emitting after 35 frames.
*   `x_vel_min="-60"`, `x_vel_max="60"`: Horizontal velocity range.
*   `y_vel_min="-60"`, `y_vel_max="40"`: Vertical velocity range.
*   `count_min="1"`, `count_max="1"`: Emits a single particle.
*   `lifetime_min="0.3"`, `lifetime_max="2.0"`: Particles last between 0.3 and 2.0 seconds.
*   `emit_cosmetic_particles="1"`: Emits cosmetic particles.
*   `emission_interval_min_frames="1"`, `emission_interval_max_frames="9"`: Emission interval varies.