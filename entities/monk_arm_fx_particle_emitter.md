---
title: Monk Arm FX Particle Emitter
category: entities
---

# Monk Arm FX Particle Emitter

This entity defines a particle emitter used for visual effects on a monk's arm. It's designed to emit small, green sparks with minimal movement and short lifespans.

## Key Components

### ParticleEmitterComponent

This component controls the behavior of the emitted particles.

| Attribute                 | Description                                                              |
| :------------------------ | :----------------------------------------------------------------------- |
| `emitted_material_name`   | The material of the particles to be emitted. Set to `spark_green`.       |
| `offset.x`, `offset.y`    | The position offset for the emitter. Set to `0` for no offset.           |
| `gravity.y`               | The gravitational pull on the particles. Set to `0` for no gravity.      |
| `x_vel_min`, `x_vel_max`  | Minimum and maximum horizontal velocity of emitted particles. Set to `0`. |
| `y_vel_min`, `y_vel_max`  | Minimum and maximum vertical velocity of emitted particles. Set to `0`.   |
| `friction`                | The friction applied to particles. Set to `0` for no friction.           |
| `count_min`, `count_max`  | Minimum and maximum number of particles emitted per burst. Set to `1`.   |
| `lifetime_min`, `lifetime_max` | Minimum and maximum lifespan of emitted particles in seconds.            |
| `emit_real_particles`     | Whether to emit actual game entities as particles. Set to `0`.           |
| `is_trail`                | Whether the particles should form a trail. Set to `0`.                   |
| `emit_cosmetic_particles` | Whether to emit cosmetic particles (visual effects only). Set to `1`.    |
| `emission_interval_min_frames`, `emission_interval_max_frames` | The frame interval between particle emissions. Set to `1` for continuous emission. |
| `is_emitting`             | Whether the emitter is currently active. Set to `1`.                     |