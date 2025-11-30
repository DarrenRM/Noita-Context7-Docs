---
title: Large Pink Muzzle Flash Particle
category: entities
---

# Large Pink Muzzle Flash Particle

This entity defines a large, pink muzzle flash effect, commonly used for spells or weapons. It utilizes a combination of sprite animation and particle emitters to create a dynamic visual.

## Sprite Component

This component handles the visual representation of the muzzle flash itself.

### Key Attributes:

*   `image_file`: Specifies the sprite sheet for the animation. It uses a sequence of images named `muzzle_large_pink_01.png` through `muzzle_large_pink_05.png`.
*   `rect_animation`: Defines the name of the animation sequence to use from the sprite sheet.
*   `next_rect_animation`: Specifies the name of the animation to transition to after the current one finishes.
*   `emissive`: Set to `1`, meaning the sprite emits light.
*   `additive`: Set to `1`, indicating additive blending for the sprite, which enhances the glow effect.
*   `kill_entity_after_finished`: Set to `1`, meaning the entity will be destroyed once the sprite animation completes.
*   `offset_x`, `offset_y`: Adjusts the sprite's position relative to the entity's origin.

## Particle Emitter Components

This entity uses two `ParticleEmitterComponent` instances to generate secondary particle effects.

### Emitter 1: Quick Burst

This emitter creates a very short-lived burst of particles immediately upon activation.

#### Key Attributes:

*   `emitted_material_name`: The material used for the emitted particles (`plasma_fading_pink`).
*   `x_pos_offset_min`, `y_pos_offset_min`, `x_pos_offset_max`, `y_pos_offset_max`: Defines a small area around the emitter origin from which particles can spawn.
*   `x_vel_min`, `x_vel_max`, `y_vel_min`, `y_vel_max`: Sets the initial velocity range for the particles. Note the `x_vel_max` is smaller than `x_vel_min`, which is unusual and might lead to unexpected behavior or a specific visual effect.
*   `count_min`, `count_max`: The number of particles to emit per burst.
*   `lifetime_min`, `lifetime_max`: The extremely short lifespan of these particles (0.0 to 0.05 seconds).
*   `create_real_particles`: Set to `0`, meaning these are cosmetic particles and don't interact physically.
*   `emit_cosmetic_particles`: Set to `1`, confirming these are cosmetic.
*   `emission_interval_min_frames`, `emission_interval_max_frames`: Set to `0`, indicating a single, immediate burst.
*   `is_emitting`: Set to `1`, meaning the emitter is active.

### Emitter 2: Lingering Particles

This emitter generates a more sustained stream of particles with a longer lifespan and some interaction with airflow.

#### Key Attributes:

*   `emitted_material_name`: The material used for the emitted particles (`plasma_fading_pink`).
*   `gravity.y`: Set to `0`, meaning these particles are not affected by gravity.
*   `x_pos_offset_min`, `y_pos_offset_min`, `x_pos_offset_max`, `y_pos_offset_max`: Particles spawn directly at the emitter origin.
*   `x_vel_min`, `x_vel_max`, `y_vel_min`, `y_vel_max`: Defines the velocity range for these particles.
*   `count_min`, `count_max`: The number of particles to emit per interval.
*   `lifetime_min`, `lifetime_max`: The lifespan of these particles (1.0 to 4.1 seconds).
*   `fade_based_on_lifetime`: Set to `1`, meaning particles will fade out as their lifetime progresses.
*   `render_on_grid`: Set to `1`, allowing particles to be rendered on the game grid.
*   `airflow_force`, `airflow_time`, `airflow_scale`: These attributes control how particles interact with airflow, giving them a subtle drift.
*   `create_real_particles`: Set to `0`, indicating cosmetic particles.
*   `emit_cosmetic_particles`: Set to `1`, confirming these are cosmetic.
*   `emission_interval_min_frames`, `emission_interval_max_frames`: Controls the timing between particle emissions (2 to 8 frames).
*   `is_emitting`: Set to `1`, meaning the emitter is active.