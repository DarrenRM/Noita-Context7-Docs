---
title: Laser Muzzle Flash Particle Entity
category: entities
---

# Laser Muzzle Flash Particle Entity

This entity defines the visual effect of a laser muzzle flash, primarily using particle emitters.

## SpriteComponent

This component handles the visual representation of the muzzle flash.

### Key Attributes:

*   `image_file`: Specifies the sprite sheet for the animation. It uses a pattern `muzzle_laser_0$[1-5].png` to cycle through 5 different frames.
*   `rect_animation`: Defines the name of the animation to use from the sprite sheet.
*   `next_rect_animation`: Specifies the next animation to play after the current one finishes.
*   `emissive`: Set to `1`, meaning the sprite emits light.
*   `additive`: Set to `1`, indicating additive blending for the sprite, making it appear brighter when overlapping.
*   `kill_entity_after_finished`: Set to `1`, meaning the entity will be destroyed once the sprite animation is complete.
*   `offset_x`, `offset_y`: Adjusts the sprite's position relative to the entity's origin.

## ParticleEmitterComponent (Primary Flash)

This component emits a short-lived burst of particles to create the initial flash effect.

### Key Attributes:

*   `emitted_material_name`: The material of the particles being emitted (`plasma_fading`).
*   `x_pos_offset_min`, `y_pos_offset_min`, `x_pos_offset_max`, `y_pos_offset_max`: Defines a small area around the emitter where particles can spawn.
*   `x_vel_min`, `x_vel_max`, `y_vel_min`, `y_vel_max`: Sets the initial velocity range for the emitted particles. Note the unusual `x_vel_max` being less than `x_vel_min`, which might lead to unexpected behavior or be a typo.
*   `count_min`, `count_max`: The number of particles to emit per burst.
*   `lifetime_min`, `lifetime_max`: The duration each particle will exist. These are very short, creating a quick flash.
*   `create_real_particles`: Set to `0`, meaning these are cosmetic particles, not physical ones.
*   `emit_cosmetic_particles`: Set to `1`, confirming these are cosmetic.
*   `is_emitting`: Set to `1`, enabling the emitter.

## ParticleEmitterComponent (Secondary Glow/Trail)

This component emits particles that persist longer, creating a lingering glow or trail effect.

### Key Attributes:

*   `emitted_material_name`: The material of the particles being emitted (`plasma_fading`).
*   `gravity.y`: Set to `0`, meaning these particles are not affected by gravity.
*   `x_pos_offset_min` to `y_pos_offset_max`: Set to `0`, meaning particles spawn exactly at the emitter's origin.
*   `x_vel_min`, `x_vel_max`, `y_vel_min`, `y_vel_max`: Defines the velocity range for these particles.
*   `count_min`, `count_max`: The number of particles to emit per burst.
*   `lifetime_min`, `lifetime_max`: The duration each particle will exist. These are significantly longer than the primary flash particles.
*   `fade_based_on_lifetime`: Set to `1`, causing particles to fade out as their lifetime decreases.
*   `render_on_grid`: Set to `1`, allowing particles to be rendered on the game grid.
*   `airflow_force`, `airflow_time`, `airflow_scale`: Parameters related to how particles interact with airflow in the game world.
*   `create_real_particles`: Set to `0`, indicating cosmetic particles.
*   `emit_cosmetic_particles`: Set to `1`, confirming these are cosmetic.
*   `emission_interval_min_frames`, `emission_interval_max_frames`: Controls the delay between particle emission bursts.
*   `is_emitting`: Set to `1`, enabling the emitter.