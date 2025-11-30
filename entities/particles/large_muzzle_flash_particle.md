---
title: Large Muzzle Flash Particle
category: entities/particles
---

# Large Muzzle Flash Particle

This entity defines a large muzzle flash effect, typically used for weapon projectiles. It consists of a sprite animation and a particle emitter.

## SpriteComponent

This component handles the visual representation of the muzzle flash.

### Key Attributes:

*   `image_file`: Specifies the sprite sheet for the animation. The `$[1-5]` indicates a sequence of 5 frames.
*   `rect_animation`: Defines the name of the animation sequence.
*   `next_rect_animation`: Specifies the next animation to play after the current one finishes.
*   `emissive`: Set to `1` to make the sprite emit light.
*   `additive`: Set to `1` for additive blending, making the flash brighter.
*   `kill_entity_after_finished`: Set to `1` to automatically remove the entity once the animation is complete.
*   `offset_x`, `offset_y`: Adjusts the sprite's position relative to the entity's origin.

## ParticleEmitterComponent

This component generates cosmetic particles that contribute to the muzzle flash effect.

### Key Attributes:

*   `emitted_material_name`: The material of the particles to be emitted (e.g., "spark").
*   `offset.x`, `offset.y`: The offset of the emitter from the entity's origin.
*   `x_pos_offset_min`, `y_pos_offset_min`, `x_pos_offset_max`, `y_pos_offset_max`: Defines the area where particles can be spawned.
*   `x_vel_min`, `x_vel_max`, `y_vel_min`, `y_vel_max`: Sets the velocity range for the emitted particles.
*   `count_min`, `count_max`: The minimum and maximum number of particles to emit per emission.
*   `lifetime_min`, `lifetime_max`: The duration each particle will exist.
*   `create_real_particles`: Set to `0` to indicate these are cosmetic particles, not physical ones.
*   `emit_cosmetic_particles`: Set to `1` to enable the emission of cosmetic particles.
*   `emission_interval_min_frames`, `emission_interval_max_frames`: Controls the timing between particle emissions.
*   `is_emitting`: Set to `1` to ensure the emitter is active.