---
title: Evaporation Particle Effect
category: entities/particles
---

# Evaporation Particle Effect

This entity defines a particle effect that simulates evaporation, typically used for steam or vapor. It emits small, short-lived particles with a subtle light effect.

## Key Components

### LifetimeComponent

*   **lifetime**: `10` - The total duration this entity will exist.

### ParticleEmitterComponent

This component is responsible for generating the actual particles.

*   **emitted_material_name**: `steam` - The material of the particles being emitted.
*   **count_min**: `1` - Minimum number of particles emitted per emission.
*   **count_max**: `4` - Maximum number of particles emitted per emission.
*   **x_pos_offset_min**: `-4` - Minimum horizontal offset for particle spawn.
*   **y_pos_offset_min**: `-4` - Minimum vertical offset for particle spawn.
*   **x_pos_offset_max**: `4` - Maximum horizontal offset for particle spawn.
*   **y_pos_offset_max**: `4` - Maximum vertical offset for particle spawn.
*   **x_vel_min**: `-50` - Minimum horizontal velocity for emitted particles.
*   **x_vel_max**: `50` - Maximum horizontal velocity for emitted particles.
*   **y_vel_min**: `-50` - Minimum vertical velocity for emitted particles.
*   **y_vel_max**: `50` - Maximum vertical velocity for emitted particles.
*   **lifetime_min**: `0.1` - Minimum lifetime of individual emitted particles.
*   **lifetime_max**: `0.2` - Maximum lifetime of individual emitted particles.
*   **create_real_particles**: `1` - Indicates that actual game particles should be created.
*   **emit_cosmetic_particles**: `0` - Cosmetic particles are not emitted.
*   **emission_interval_min_frames**: `1` - Minimum frames between particle emissions.
*   **emission_interval_max_frames**: `1` - Maximum frames between particle emissions.
*   **is_emitting**: `1` - The emitter is active and will emit particles.

### LightComponent

This component adds a light source to the entity, simulating the glow of hot steam.

*   **r**: `38` - Red component of the light color.
*   **g**: `105` - Green component of the light color.
*   **b**: `180` - Blue component of the light color.
*   **radius**: `38` - The radius of the light effect.
*   **fade_out_time**: `1` - The time it takes for the light to fade out.