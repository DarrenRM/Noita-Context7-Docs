---
title: Player Gas Effect
category: entities
---

# Player Gas Effect

This entity defines the visual and physical effects of gas emitted by the player, specifically a "fart" effect.

## Key Components

### ParticleEmitterComponent

This component controls the emission of particles that create the gas effect.

| Attribute              | Description                                                                 |
| :--------------------- | :-------------------------------------------------------------------------- |
| `_tags`                | Identifies the particle effect, here set to "fart".                         |
| `emitted_material_name`| The material of the particles being emitted, set to "acid_gas".             |
| `offset.x`, `offset.y` | The initial offset of the particle emitter relative to the entity's position. |
| `x_pos_offset_min/max` | The minimum and maximum horizontal offset for particle emission.            |
| `y_pos_offset_min/max` | The minimum and maximum vertical offset for particle emission.              |
| `x_vel_min/max`        | The minimum and maximum horizontal velocity of emitted particles.           |
| `y_vel_min/max`        | The minimum and maximum vertical velocity of emitted particles.             |
| `count_min/max`        | The minimum and maximum number of particles emitted per emission cycle.     |
| `lifetime_min/max`     | The minimum and maximum lifetime of individual particles in seconds.        |
| `create_real_particles`| If set to "1", creates actual physics-simulated particles.                  |
| `emit_cosmetic_particles`| If set to "1", emits visual-only particles.                                 |
| `emission_interval_min_frames/max_frames` | Controls the frame rate of particle emission. Set to "0" and "1" for continuous emission. |
| `is_emitting`          | If set to "1", the emitter is active.                                       |

### LifetimeComponent

This component defines how long the entity itself persists.

| Attribute | Description                               |
| :-------- | :---------------------------------------- |
| `lifetime`| The total lifetime of the entity in seconds. Set to "3600" (1 hour). |