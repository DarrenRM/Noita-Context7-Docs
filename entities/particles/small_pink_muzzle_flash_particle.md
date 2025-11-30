---
title: Small Pink Muzzle Flash Particle
category: entities/particles
---

# Small Pink Muzzle Flash Particle

This entity defines a small, pink muzzle flash effect for projectiles in Noita. It utilizes two `ParticleEmitterComponent`s to create a layered visual and particle effect.

## SpriteComponent

This component handles the visual representation of the muzzle flash.

### Key Attributes:

*   `image_file`: Specifies the sprite sheet for the animation. The `$[1-5]` indicates a sequence of 5 frames.
*   `rect_animation`: Defines the name of the animation sequence.
*   `next_rect_animation`: Specifies the next animation to play after the current one finishes.
*   `emissive`: Set to `1` to make the sprite emit light.
*   `additive`: Set to `1` for additive blending, common for bright light effects.
*   `kill_entity_after_finished`: Set to `1` to automatically remove the entity once the animation is complete.
*   `offset_x`, `offset_y`: Adjusts the sprite's position relative to the entity's origin.

## ParticleEmitterComponent (Primary)

This emitter is responsible for the initial, quick burst of the muzzle flash.

### Key Attributes:

*   `emitted_material_name`: The material of the particles to be emitted. Here, it's `plasma_fading_pink`.
*   `x_pos_offset_min`, `y_pos_offset_min`, `x_pos_offset_max`, `y_pos_offset_max`: Defines the area where particles can spawn around the emitter's origin.
*   `x_vel_min`, `x_vel_max`, `y_vel_min`, `y_vel_max`: Sets the initial velocity range for the emitted particles.
*   `count_min`, `count_max`: The number of particles to emit per burst.
*   `lifetime_min`, `lifetime_max`: The duration each particle will exist.
*   `create_real_particles`: Set to `0` to emit cosmetic particles only.
*   `emit_cosmetic_particles`: Set to `1` to ensure cosmetic particles are emitted.
*   `is_emitting`: Set to `1` to enable emission.

## ParticleEmitterComponent (Secondary)

This emitter creates a more sustained, trailing effect for the muzzle flash.

### Key Attributes:

*   `emitted_material_name`: Same as the primary emitter, `plasma_fading_pink`.
*   `gravity.y`: Controls the gravitational pull on the particles. `0` means no gravity.
*   `x_pos_offset_min` to `y_pos_offset_max`: These are set to `0` to ensure particles spawn directly at the emitter's origin.
*   `x_vel_min`, `x_vel_max`, `y_vel_min`, `y_vel_max`: Defines a wider, more varied velocity for these trailing particles.
*   `count_min`, `count_max`: The number of particles emitted per interval.
*   `lifetime_min`, `lifetime_max`: A longer lifetime for these trailing particles.
*   `fade_based_on_lifetime`: Set to `1` to make particles fade out as their lifetime ends.
*   `render_on_grid`: Set to `1` to allow particles to be rendered on the game grid.
*   `airflow_force`, `airflow_time`, `airflow_scale`: These attributes introduce airflow effects, making the particles move and swirl.
*   `emission_interval_min_frames`, `emission_interval_max_frames`: Controls the delay between particle emissions, creating a more continuous stream.
*   `is_emitting`: Set to `1` to enable emission.