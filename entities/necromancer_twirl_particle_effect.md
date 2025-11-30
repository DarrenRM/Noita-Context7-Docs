---
title: Necromancer Twirl Particle Effect
category: entities
---

# Necromancer Twirl Particle Effect

This entity defines a particle effect used for a "necromancer twirl" visual. It primarily consists of a light source and a sprite particle emitter.

## Key Components

### LightComponent

This component adds a light source to the entity, illuminating the surrounding area.

*   **`_enabled`**: `1` (Component is active)
*   **`radius`**: `255` (Maximum reach of the light)
*   **`fade_out_time`**: `10.5` (Duration over which the light fades out)
*   **`r`, `g`, `b`**: `130`, `83`, `222` (RGB values for a purple hue)
*   **`offset_y`**: `-16` (Vertical offset of the light source)

### SpriteParticleEmitterComponent

This component is responsible for generating and managing the visual particles.

*   **`sprite_file`**: `data/particles/purple_whirl_0$[1-8].png` (Uses a sequence of 8 purple whirl sprites)
*   **`sprite_centered`**: `1` (Sprites are centered on their origin)
*   **`delay`**: `0` (Particles start emitting immediately)
*   **`lifetime`**: `1.5` (Each particle lasts for 1.5 seconds)
*   **`color.r`, `color.g`, `color.b`, `color.a`**: `0.5`, `1`, `1`, `0.75` (Initial color and alpha of particles)
*   **`color_change.a`**: `-0.8` (Alpha decreases over the particle's lifetime, causing fading)
*   **`velocity.x`, `velocity.y`**: `0`, `0` (Initial velocity is zero, particles are influenced by other factors)
*   **`gravity.x`, `gravity.y`**: `0`, `0` (No gravity applied to particles)
*   **`velocity_slowdown`**: `0.35` (Particles gradually slow down)
*   **`angular_velocity`**: `7.5` (Particles rotate at a base speed)
*   **`scale.x`, `scale.y`**: `1.0`, `1.0` (Initial scale of particles)
*   **`scale_velocity.x`, `scale_velocity.y`**: `1.0075`, `1.0075` (Particles slightly grow over time)
*   **`emission_interval_min_frames`, `emission_interval_max_frames`**: `2`, `4` (Particles are emitted every 2 to 4 frames)
*   **`count_min`, `count_max`**: `1`, `1` (One particle is emitted per emission interval)
*   **`randomize_position`**: Particles are emitted within a small random offset from the entity's origin.
*   **`randomize_velocity`**: Particles have a random initial velocity within a range of -5 to 5 on both X and Y axes.
*   **`randomize_lifetime`**: Particle lifetimes are randomized by +/- 0.2 seconds.
*   **`randomize_angular_velocity`**: Angular velocity is randomized by +/- 3.5 degrees per second.
*   **`randomize_rotation`**: Initial rotation is randomized between -90 and 90 degrees.

### LifetimeComponent

This component defines the overall lifetime of the entity itself.

*   **`lifetime`**: `90` (The entity exists for 90 seconds)