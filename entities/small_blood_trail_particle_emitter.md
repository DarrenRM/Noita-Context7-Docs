---
title: Small Blood Trail Particle Emitter
category: entities
---

# Small Blood Trail Particle Emitter

This entity defines a particle emitter that creates small blood trails. It's designed to be attached to other entities to leave a visual trail of blood.

## Key Components

### ParticleEmitterComponent

This is the core component responsible for emitting particles.

| Attribute                  | Description                                                                                                |
| :------------------------- | :--------------------------------------------------------------------------------------------------------- |
| `emitted_material_name`    | The material of the particles to be emitted. Here, it's `blood_fading_slow`, indicating a slow-fading blood effect. |
| `gravity.y`                | The gravitational pull on the emitted particles along the Y-axis. A value of `400` suggests a moderate downward pull. |
| `x_vel_min`, `x_vel_max`   | The minimum and maximum velocity of particles along the X-axis. This controls horizontal spread.            |
| `y_vel_min`, `y_vel_max`   | The minimum and maximum velocity of particles along the Y-axis. This controls vertical spread.             |
| `count_min`, `count_max`   | The minimum and maximum number of particles emitted per emission event.                                    |
| `is_trail`                 | Set to `1` to indicate that this emitter is intended to create a trail effect.                             |
| `trail_gap`                | The spacing between particles in the trail. A value of `4` means particles are spaced apart.               |
| `lifetime_min`, `lifetime_max` | The minimum and maximum duration (in seconds) each particle will exist.                                    |
| `emit_real_particles`      | Set to `1` to emit actual game particles that can interact with the world.                                 |
| `emit_cosmetic_particles`  | Set to `0` to disable the emission of purely cosmetic particles.                                           |
| `emission_interval_min_frames`, `emission_interval_max_frames` | The minimum and maximum number of frames between particle emission events. This controls the rate of emission. |
| `is_emitting`              | Set to `1` to enable particle emission.                                                                    |