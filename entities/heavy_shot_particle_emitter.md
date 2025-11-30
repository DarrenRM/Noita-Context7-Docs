---
title: Heavy Shot Particle Emitter
category: entities
---

# Heavy Shot Particle Emitter

This document details the configuration of particle emitters used for the "heavy_shot" entity in Noita, focusing on AI-assisted modding.

## Overview

The `heavy_shot.xml` file defines two primary particle emitters responsible for visual effects associated with a heavy shot. These emitters control the appearance, behavior, and emission patterns of particles.

## Key Components

### SpriteParticleEmitterComponent

This component is responsible for emitting particles based on a sprite sheet.

#### Key Attributes:

*   **`sprite_file`**: Specifies the sprite sheet to use for particles.
    *   Example: `"data/particles/explosion_012.xml"`
*   **`lifetime`**: Duration each particle exists.
    *   `"0"` indicates it's likely controlled by other factors or is a very short-lived effect.
*   **`color`**: Initial color of the particles (RGBA).
    *   `color.r="1" color.g="1" color.b="1" color.a="1"` represents white.
*   **`color_change`**: How the color changes over the particle's lifetime.
    *   `"0"` for all channels means no color change.
*   **`velocity`**: Initial velocity of the particles (X, Y).
    *   `velocity.x="0" velocity.y="0"` means no initial directional movement.
*   **`gravity`**: Gravity applied to the particles (X, Y).
    *   `gravity.y="10"` indicates downward acceleration.
*   **`scale`**: Initial scale of the particles (X, Y).
    *   `scale.x="1" scale.y="1"` means particles start at normal size.
*   **`scale_velocity`**: How the scale changes over time (X, Y).
    *   `scale_velocity.x="-0.1" scale_velocity.y="-0.1"` means particles shrink over time.
*   **`emission_interval_min_frames` / `emission_interval_max_frames`**: Controls the timing between particle emissions.
    *   `"3"` to `"5"` frames.
*   **`count_min` / `count_max`**: The number of particles emitted per interval.
    *   `"1"` to `"1"` means exactly one particle is emitted.
*   **`randomize_position`**: Defines a random offset for particle emission.
    *   `min_x="-7" max_x="7"`
    *   `min_y="-3" max_y="3"`
*   **`_enabled`**: Controls whether the emitter is active.
    *   `"0"` means this emitter is disabled by default.

### ParticleEmitterComponent

This component emits simpler, material-based particles.

#### Key Attributes:

*   **`emitted_material_name`**: The material of the particles to be emitted.
    *   Example: `"spark_red"`
*   **`offset`**: Offset from the entity's origin for emission.
    *   `offset.x="0" offset.y="0"`
*   **`x_pos_offset_min` / `x_pos_offset_max`**: Random horizontal position offset for emission.
    *   `"-1"` to `"1"`
*   **`y_pos_offset_min` / `y_pos_offset_max`**: Random vertical position offset for emission.
    *   `"-1"` to `"1"`
*   **`gravity`**: Gravity applied to the particles.
    *   `gravity.y="0"` means no vertical gravity for these particles.
*   **`x_vel_min` / `x_vel_max`**: Minimum and maximum horizontal velocity.
    *   `"-2"` to `"2"`
*   **`y_vel_min` / `y_vel_max`**: Minimum and maximum vertical velocity.
    *   `"-2"` to `"2"`
*   **`count_min` / `count_max`**: Number of particles emitted per interval.
    *   `"3"` to `"10"`
*   **`is_trail`**: Whether the particles form a trail.
    *   `"1"` means yes.
*   **`trail_gap`**: Spacing between trail particles.
    *   `"0.2"`
*   **`fade_based_on_lifetime`**: Whether particles fade as they age.
    *   `"1"` means yes.
*   **`lifetime_min` / `lifetime_max`**: Minimum and maximum particle lifetime.
    *   `"0.8"` to `"2.0"` seconds.
*   **`airflow_force` / `airflow_time` / `airflow_scale`**: Parameters for airflow effects on particles.
    *   `airflow_force="1.5"`
    *   `airflow_time="0.401"`
    *   `airflow_scale="0.05"`
*   **`create_real_particles`**: Whether to create actual game entities for particles.
    *   `"0"` means no.
*   **`emit_cosmetic_particles`**: Whether to emit particles purely for visual effect.
    *   `"1"` means yes.
*   **`render_on_grid`**: Whether particles are rendered on the game grid.
    *   `"1"` means yes.
*   **`emission_interval_min_frames` / `emission_interval_max_frames`**: Timing between emissions.
    *   `"1"` to `"2"` frames.
*   **`is_emitting`**: Whether the emitter is active.
    *   `"1"` means yes.