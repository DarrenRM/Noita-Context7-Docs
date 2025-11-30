---
title: Base Smoke Trail Particle
category: entities
---

# Base Smoke Trail Particle

This entity defines the behavior and appearance of a basic smoke trail particle effect in Noita. It's designed to be a foundational element for creating more complex smoke and fire effects.

## Key Components and Attributes

This entity utilizes several components to manage its physics, particle emission, and visual properties.

### VelocityComponent

Controls the movement physics of the particle.

*   `gravity_y`: The strength of gravity applied to the particle along the Y-axis.
*   `air_friction`: The resistance to movement caused by air.

### SimplePhysicsComponent

A basic physics component that allows the particle to interact with the physics engine.

### SetStartVelocityComponent

Determines the initial velocity of the particle when it's spawned.

*   `randomize_speed.min`: The minimum initial speed.
*   `randomize_speed.max`: The maximum initial speed.
*   `randomize_angle.min`: The minimum initial angle (in radians).
*   `randomize_angle.max`: The maximum initial angle (in radians).

### DieIfSpeedBelowComponent

Defines a condition for the particle to be destroyed.

*   `min_speed`: The minimum speed the particle must maintain to survive.

### SpriteParticleEmitterComponent (x2)

These components are responsible for emitting other particles, creating the visual trail.

#### First SpriteParticleEmitterComponent (Fire Particles)

*   `sprite_file`: Specifies the sprite file for the emitted particles (e.g., `data/particles/fire.xml`).
*   `emission_interval_min_frames`, `emission_interval_max_frames`: Controls how frequently particles are emitted.
*   `additive`, `emissive`: Affects how the particles are rendered (e.g., additive blending for glow).
*   `scale.x`, `scale.y`: Base scale of the emitted particles.
*   `sprite_random_rotation`: Whether the emitted sprites should have random rotation.
*   `randomize_scale.min_x`, `randomize_scale.max_x`, `randomize_scale.min_y`, `randomize_scale.max_y`: Random variation applied to the scale of emitted particles.
*   `randomize_velocity.min_y`, `randomize_velocity.max_y`: Random variation applied to the vertical velocity of emitted particles.

#### Second SpriteParticleEmitterComponent (Smoke Cloud Particles)

*   `sprite_file`: Specifies the sprite file for the emitted particles (e.g., `data/particles/smoke_cloud_tiny_$[1-4].xml`). The `$[1-4]` suggests it can use variations of this sprite.
*   `emission_interval_min_frames`, `emission_interval_max_frames`: Controls how frequently particles are emitted.
*   `additive`, `emissive`: Affects rendering. `emissive="0"` indicates these smoke particles are not self-illuminating.
*   `scale.x`, `scale.y`: Base scale of the emitted particles.
*   `sprite_random_rotation`: Whether the emitted sprites should have random rotation.
*   `randomize_scale.min_x`, `randomize_scale.max_x`, `randomize_scale.min_y`, `randomize_scale.max_y`: Random variation applied to the scale of emitted particles.
*   `randomize_velocity.min_y`, `randomize_velocity.max_y`: Random variation applied to the vertical velocity of emitted particles.
*   `randomize_velocity.min_x`, `randomize_velocity.max_x`: Random variation applied to the horizontal velocity of emitted particles.

### ParticleEmitterComponent (x2)

These components emit actual game materials as particles, rather than just sprites.

#### First ParticleEmitterComponent (Smoke Material)

*   `emitted_material_name`: The material to be emitted (e.g., "smoke").
*   `offset.x`, `offset.y`: Offset from the entity's position where particles are emitted.
*   `x_pos_offset_min`, `y_pos_offset_min`, `x_pos_offset_max`, `y_pos_offset_max`: Defines a rectangular area for particle emission.
*   `x_vel_min`, `x_vel_max`, `y_vel_min`, `y_vel_max`: Initial velocity range for emitted particles.
*   `count_min`, `count_max`: The number of particles emitted per emission event.
*   `lifetime_min`, `lifetime_max`: The duration each emitted particle will exist.
*   `create_real_particles`: Set to `1` to create actual game particles.
*   `emit_cosmetic_particles`: Set to `0` to prevent cosmetic particle emission.
*   `emission_interval_min_frames`, `emission_interval_max_frames`: Controls emission frequency.
*   `is_emitting`: Set to `1` to enable emission.

#### Second ParticleEmitterComponent (Flame Material)

*   `emitted_material_name`: The material to be emitted (e.g., "flame").
*   `offset.x`, `offset.y`: Offset from the entity's position.
*   `gravity.y`: Gravity applied to these emitted flame particles.
*   `x_pos_offset_min`, `y_pos_offset_min`, `x_pos_offset_max`, `y_pos_offset_max`: Defines the emission area.
*   `x_vel_min`, `x_vel_max`, `y_vel_min`, `y_vel_max`: Initial velocity range for emitted particles.
*   `count_min`, `count_max`: Number of particles emitted per event.
*   `lifetime_min`, `lifetime_max`: Duration of emitted particles.
*   `create_real_particles`: Set to `1` to create actual game particles.
*   `emit_cosmetic_particles`: Set to `0` to prevent cosmetic particle emission.
*   `emission_interval_min_frames`, `emission_interval_max_frames`: Controls emission frequency.
*   `is_emitting`: Set to `1` to enable emission.