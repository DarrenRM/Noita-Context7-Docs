---
title: Large Launcher Muzzle Flash Particle
category: entities
---

# Large Launcher Muzzle Flash Particle

This entity defines a large muzzle flash effect for launchers in Noita. It utilizes a sprite animation and a particle emitter to create a dynamic visual effect.

## SpriteComponent

This component handles the visual representation of the muzzle flash.

### Key Attributes:

*   `image_file`: Specifies the sprite sheet used for the animation. It uses a pattern `muzzle_launcher_large_0$[1-5].png` indicating 5 frames.
*   `rect_animation`: Defines the name of the animation sequence to be played.
*   `next_rect_animation`: Specifies the animation to transition to after the current one finishes.
*   `emissive`: Set to `1`, meaning the sprite emits light.
*   `additive`: Set to `1`, indicating additive blending for the sprite, common for light effects.
*   `kill_entity_after_finished`: Set to `1`, meaning the entity will be destroyed once the animation is complete.
*   `offset_x`, `offset_y`: Adjusts the sprite's position relative to its origin.

## ParticleEmitterComponent

This component generates smaller particles that contribute to the muzzle flash effect.

### Key Attributes:

*   `emitted_material_name`: The material of the particles to be emitted (e.g., "spark").
*   `x_pos_offset_min`, `y_pos_offset_min`, `x_pos_offset_max`, `y_pos_offset_max`: Define the area where particles are emitted relative to the emitter's origin.
*   `x_vel_min`, `x_vel_max`, `y_vel_min`, `y_vel_max`: Control the initial velocity range of the emitted particles.
*   `count_min`, `count_max`: The number of particles to emit per emission event.
*   `lifetime_min`, `lifetime_max`: The duration each particle exists. Here, it's set to a very short duration (0.0 to 0.05 seconds).
*   `create_real_particles`: Set to `0`, meaning these are cosmetic particles and don't interact physically.
*   `emit_cosmetic_particles`: Set to `1`, ensuring these particles are rendered.
*   `emission_interval_min_frames`, `emission_interval_max_frames`: Set to `0`, meaning particles are emitted instantly rather than over time.
*   `is_emitting`: Set to `1`, enabling the particle emission.