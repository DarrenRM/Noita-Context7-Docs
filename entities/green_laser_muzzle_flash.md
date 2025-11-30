---
title: Green Laser Muzzle Flash
category: entities
---

# Green Laser Muzzle Flash

This entity defines the visual effect of a green laser muzzle flash in Noita. It utilizes sprite animations and particle emitters to create a dynamic and visually appealing effect.

## SpriteComponent

This component handles the primary visual representation of the muzzle flash.

### Key Attributes:

*   `image_file`: Specifies the sprite sheet used for the animation. The `$[1-5]` indicates a sequence of 5 frames.
*   `rect_animation`: Defines the name of the animation sequence within the sprite sheet.
*   `next_rect_animation`: Specifies the animation to transition to after the current one finishes.
*   `emissive`: Set to `1` to make the sprite emit light.
*   `kill_entity_after_finished`: Set to `1` to automatically remove the entity once the animation is complete.
*   `offset_x`, `offset_y`: Adjusts the position of the sprite relative to the entity's origin.

## ParticleEmitterComponent (Plasma Fading Green)

This component emits small, fading green plasma particles.

### Key Attributes:

*   `emitted_material_name`: The material name of the particles to be emitted (`plasma_fading_green`).
*   `x_pos_offset_min`, `y_pos_offset_min`, `x_pos_offset_max`, `y_pos_offset_max`: Defines the random spread of particle emission around the entity's origin.
*   `x_vel_min`, `x_vel_max`, `y_vel_min`, `y_vel_max`: Sets the initial velocity range for the emitted particles.
*   `count_min`, `count_max`: The number of particles to emit per emission event.
*   `lifetime_min`, `lifetime_max`: The duration each particle will exist.
*   `create_real_particles`: Set to `0` to emit cosmetic particles, not actual physics-simulated ones.
*   `emit_cosmetic_particles`: Set to `1` to ensure these are cosmetic effects.
*   `is_emitting`: Set to `1` to enable emission.

## ParticleEmitterComponent (Spark Green)

This component emits green sparks, adding a secondary visual element to the muzzle flash.

### Key Attributes:

*   `emitted_material_name`: The material name of the particles to be emitted (`spark_green`).
*   `gravity.y`: Controls the gravitational pull on the sparks. Set to `0` for no gravity.
*   `x_pos_offset_min`, `y_pos_offset_min`, `x_pos_offset_max`, `y_pos_offset_max`: Defines the emission spread. Here, it's set to `0` for a concentrated emission point.
*   `x_vel_min`, `x_vel_max`, `y_vel_min`, `y_vel_max`: Sets the initial velocity range for the sparks.
*   `count_min`, `count_max`: The number of sparks to emit per emission event.
*   `lifetime_min`, `lifetime_max`: The duration each spark will exist.
*   `fade_based_on_lifetime`: Set to `1` to make sparks fade out as their lifetime ends.
*   `render_on_grid`: Set to `1` to ensure sparks are rendered even on the game grid.
*   `airflow_force`, `airflow_time`, `airflow_scale`: Parameters related to how airflow affects the sparks.
*   `create_real_particles`: Set to `0` for cosmetic particles.
*   `emit_cosmetic_particles`: Set to `1` for cosmetic effects.
*   `emission_interval_min_frames`, `emission_interval_max_frames`: Controls the delay between emission bursts.
*   `is_emitting`: Set to `1` to enable emission.