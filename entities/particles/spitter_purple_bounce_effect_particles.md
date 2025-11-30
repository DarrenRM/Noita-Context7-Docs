---
title: Spitter Purple Bounce Effect Particles
category: entities/particles
---

# Spitter Purple Bounce Effect Particles

This entity defines the particle effects that occur when a spitter projectile bounces. It primarily uses a `ParticleEmitterComponent` to generate these particles.

## Key Components

### LifetimeComponent

*   **lifetime**: The duration (in seconds) for which this particle effect entity exists.
    *   `lifetime="3"`

### ParticleEmitterComponent

This component is responsible for emitting the actual particles.

*   **emitted_material_name**: The material used for the emitted particles.
    *   `emitted_material_name="spark_purple_bright"`
*   **lifetime_min/lifetime_max**: The minimum and maximum lifetime (in seconds) of individual emitted particles.
    *   `lifetime_min="0.05"`
    *   `lifetime_max="0.2"`
*   **x_pos_offset_min/max, y_pos_offset_min/max**: The random offset from the emitter's position where particles can spawn.
    *   `x_pos_offset_min="-2"`
    *   `x_pos_offset_max="2"`
    *   `y_pos_offset_min="-2"`
    *   `y_pos_offset_max="2"`
*   **x_vel_min/max, y_vel_min/max**: The range of initial velocities applied to emitted particles.
    *   `x_vel_min="-120"`
    *   `x_vel_max="0"`
    *   `y_vel_min="-120"`
    *   `y_vel_max="120"`
*   **gravity.y**: The gravitational pull on the emitted particles along the Y-axis.
    *   `gravity.y="0.0"` (No vertical gravity for these particles)
*   **count_min/max**: The minimum and maximum number of particles emitted per emission cycle.
    *   `count_min="24"`
    *   `count_max="35"`
*   **render_on_grid**: Whether the particles should be rendered on the game grid.
    *   `render_on_grid="1"`
*   **fade_based_on_lifetime**: If particles should fade out as their lifetime decreases.
    *   `fade_based_on_lifetime="1"`
*   **emission_interval_min_frames/max_frames**: The interval (in frames) between particle emissions.
    *   `emission_interval_min_frames="1"`
    *   `emission_interval_max_frames="1"` (Emits continuously)
*   **emit_cosmetic_particles**: Whether to emit cosmetic particles.
    *   `emit_cosmetic_particles="1"`
*   **is_emitting**: Whether the emitter is currently active.
    *   `is_emitting="1"`