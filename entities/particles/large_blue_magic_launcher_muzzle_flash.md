---
title: Large Blue Magic Launcher Muzzle Flash
category: entities/particles
---

# Large Blue Magic Launcher Muzzle Flash

This entity defines a visual effect for a large blue muzzle flash, likely used by a magic launcher weapon in Noita. It consists of a sprite animation and two particle emitters that create cosmetic particles.

## Sprite Component

This component handles the visual appearance of the muzzle flash.

### Key Attributes:

*   `image_file`: Specifies the sprite sheet used for the animation. It uses a numbered sequence for different frames (`muzzle_magic_launcher_large_blue_0$[1-5].png`).
*   `rect_animation`: Defines the name of the animation sequence to use from the sprite sheet.
*   `next_rect_animation`: Specifies the animation to transition to after the current one finishes.
*   `emissive`: Set to `1`, indicating the sprite emits light.
*   `additive`: Set to `1`, meaning the sprite's color is added to the background, creating a glowing effect.
*   `kill_entity_after_finished`: Set to `1`, meaning the entity (the muzzle flash itself) is removed from the game once the sprite animation is complete.
*   `offset_x`, `offset_y`: Adjusts the sprite's position relative to its origin.

## Particle Emitter Components

There are two `ParticleEmitterComponent` instances, both designed to emit cosmetic particles for visual flair.

### Emitter 1: Initial Burst

This emitter creates a short-lived, intense burst of particles immediately upon emission.

#### Key Attributes:

*   `emitted_material_name`: The material used for the emitted particles (`plasma_fading`).
*   `x_vel_min`, `x_vel_max`, `y_vel_min`, `y_vel_max`: Defines the velocity range for the emitted particles, creating a spread effect.
*   `count_min`, `count_max`: The number of particles emitted per burst.
*   `lifetime_min`, `lifetime_max`: The very short lifespan of these particles (0.0 to 0.05 seconds).
*   `create_real_particles`: Set to `0`, meaning these are purely cosmetic and do not interact physically.
*   `emit_cosmetic_particles`: Set to `1`, confirming these are cosmetic.
*   `is_emitting`: Set to `1`, meaning the emitter is active.

### Emitter 2: Lingering Particles

This emitter creates a more sustained, less intense stream of particles that fade over time.

#### Key Attributes:

*   `emitted_material_name`: The material used for the emitted particles (`plasma_fading`).
*   `gravity.y`: Set to `0`, meaning these particles are not affected by gravity.
*   `x_vel_min`, `x_vel_max`, `y_vel_min`, `y_vel_max`: Defines the velocity range for these particles, generally slower and less spread than the first emitter.
*   `count_min`, `count_max`: The number of particles emitted per burst.
*   `lifetime_min`, `lifetime_max`: The longer lifespan of these particles (1.0 to 4.1 seconds).
*   `fade_based_on_lifetime`: Set to `1`, causing particles to fade out as their lifetime progresses.
*   `render_on_grid`: Set to `1`, indicating these particles can be rendered on the game grid.
*   `airflow_force`, `airflow_time`, `airflow_scale`: These attributes suggest the particles are influenced by airflow, adding a subtle movement effect.
*   `emission_interval_min_frames`, `emission_interval_max_frames`: Controls the timing between particle bursts, creating a staggered effect.
*   `create_real_particles`: Set to `0`, indicating cosmetic particles.
*   `emit_cosmetic_particles`: Set to `1`, confirming these are cosmetic.
*   `is_emitting`: Set to `1`, meaning the emitter is active.