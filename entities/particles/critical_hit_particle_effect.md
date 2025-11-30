---
title: Critical Hit Particle Effect
category: entities/particles
---

# Critical Hit Particle Effect

This entity defines the visual and auditory feedback for a critical hit in Noita. It spawns a burst of particles and plays a specific sound effect.

## Key Components

### LifetimeComponent
Controls the overall duration of the particle effect.

*   **lifetime**: `2` (seconds) - The effect will persist for 2 seconds.

### ParticleEmitterComponent
Responsible for generating the visual particles.

*   **emitted_material_name**: `spark_red` - The material used for the spawned particles.
*   **lifetime_min**: `0.5` (seconds) - Minimum lifespan of individual particles.
*   **lifetime_max**: `2` (seconds) - Maximum lifespan of individual particles.
*   **x_pos_offset_min/max**: `-5` to `5` - Horizontal spread of particle origin.
*   **y_pos_offset_min/max**: `-5` to `5` - Vertical spread of particle origin.
*   **x_vel_min/max**: `70` to `100` - Horizontal velocity of spawned particles.
*   **y_vel_min/max**: `0` to `0` - Vertical velocity of spawned particles (initially no vertical movement).
*   **direction_random_deg**: `15` - Randomizes the emission direction within +/- 15 degrees.
*   **gravity.y**: `300` - Downward acceleration applied to particles.
*   **count_min/max**: `10` to `20` - Number of particles spawned per emission.
*   **render_on_grid**: `1` - Particles are rendered on the game grid.
*   **fade_based_on_lifetime**: `1` - Particles fade out as their lifetime ends.
*   **collide_with_grid**: `1` - Particles can collide with the game grid.
*   **is_emitting**: `1` - The emitter is active.

### AudioComponent
Handles the sound effect played during a critical hit.

*   **file**: `data/audio/Desktop/projectiles.bank` - The audio bank containing the sound.
*   **event_root**: `player_projectiles/critical_hit` - The specific sound event to trigger.

---
**Note:** The commented-out `SpriteParticleEmitterComponent` suggests an alternative or previous implementation for particle generation, likely using a sprite sheet for more complex particle visuals. This current implementation relies on `ParticleEmitterComponent` with a defined material.