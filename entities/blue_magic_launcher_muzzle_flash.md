---
title: Blue Magic Launcher Muzzle Flash
category: entities
---

# Blue Magic Launcher Muzzle Flash

This entity defines the visual effect of a blue muzzle flash for a magic launcher in Noita. It utilizes sprite animations and particle emitters to create a dynamic and visually appealing effect.

## SpriteComponent

This component handles the visual representation of the muzzle flash.

### Key Attributes:

*   `image_file`: Specifies the sprite sheet containing the muzzle flash frames. The `$[1-5]` indicates a sequence of 5 frames.
*   `rect_animation`: Defines the name of the animation to be used from the sprite sheet.
*   `next_rect_animation`: Similar to `rect_animation`, often used for sequential animations.
*   `emissive`: Set to `1`, meaning the sprite emits light.
*   `additive`: Set to `1`, indicating that the sprite's color is added to the background, creating a glowing effect.
*   `kill_entity_after_finished`: Set to `1`, meaning the entity will be removed from the game once the sprite animation is complete.
*   `offset_x`, `offset_y`: Adjusts the position of the sprite relative to the entity's origin.

## ParticleEmitterComponent (First Instance)

This component emits a burst of short-lived cosmetic particles, contributing to the initial flash.

### Key Attributes:

*   `emitted_material_name`: Specifies the material of the particles to be emitted. In this case, it's "plasma\_fading".
*   `x_vel_min`, `x_vel_max`, `y_vel_min`, `y_vel_max`: Define the velocity range for the emitted particles, creating a spread effect.
*   `count_min`, `count_max`: Determines the number of particles emitted in a single burst.
*   `lifetime_min`, `lifetime_max`: Sets a very short lifetime for these particles, making them appear as a quick flash.
*   `create_real_particles`: Set to `0`, meaning these are cosmetic particles and do not interact physically with the game world.
*   `emit_cosmetic_particles`: Set to `1`, confirming these are cosmetic.
*   `is_emitting`: Set to `1`, meaning the emitter is active.

## ParticleEmitterComponent (Second Instance)

This component emits a secondary stream of particles with a longer lifetime, adding lingering visual trails.

### Key Attributes:

*   `emitted_material_name`: Again, "plasma\_fading" is used for consistency.
*   `gravity.y`: Set to `0`, meaning these particles are not affected by gravity.
*   `x_vel_min`, `x_vel_max`, `y_vel_min`, `y_vel_max`: Defines a narrower velocity range for these particles, creating a more directed trail.
*   `count_min`, `count_max`: Controls the number of particles emitted per interval.
*   `lifetime_min`, `lifetime_max`: Sets a longer lifetime for these particles, allowing them to persist for a short duration.
*   `fade_based_on_lifetime`: Set to `1`, causing particles to fade out as their lifetime progresses.
*   `render_on_grid`: Set to `1`, indicating these particles can be rendered on the game grid.
*   `airflow_force`, `airflow_time`, `airflow_scale`: These attributes suggest the particles are influenced by airflow, potentially creating subtle movement or dissipation effects.
*   `emission_interval_min_frames`, `emission_interval_max_frames`: Defines the time between particle emissions, creating a staggered effect.
*   `create_real_particles`: Set to `0` for cosmetic particles.
*   `emit_cosmetic_particles`: Set to `1`.
*   `is_emitting`: Set to `1`.