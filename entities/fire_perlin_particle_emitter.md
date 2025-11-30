---
title: Fire Perlin Particle Emitter
category: entities
---

# Fire Perlin Particle Emitter

This entity defines a simple particle emitter that generates "spark" particles with a "FIRE" custom style. It's primarily used for visual effects, as it doesn't create real physics-based particles.

## Key Components

### ParticleEmitterComponent

This is the core component responsible for emitting particles.

| Attribute                 | Description                                                                 |
| :------------------------ | :-------------------------------------------------------------------------- |
| `emitted_material_name`   | The name of the material to be emitted as particles (e.g., "spark").        |
| `custom_style`            | A custom style to apply to the emitted particles (e.g., "FIRE").            |
| `offset.x`, `offset.y`    | The base offset of the emitter from the entity's origin.                    |
| `x_pos_offset_min/max`    | The minimum and maximum horizontal offset for particle spawn positions.     |
| `y_pos_offset_min/max`    | The minimum and maximum vertical offset for particle spawn positions.       |
| `x_vel_min/max`           | The minimum and maximum horizontal velocity for emitted particles.          |
| `y_vel_min/max`           | The minimum and maximum vertical velocity for emitted particles.            |
| `count_min/max`           | The minimum and maximum number of particles emitted per emission event.     |
| `lifetime_min/max`        | The minimum and maximum lifespan of emitted particles in seconds.           |
| `is_trail`                | If set to "1", particles will leave a trail.                                |
| `emission_interval_min/max_frames` | The minimum and maximum frames between particle emission events.          |
| `emit_cosmetic_particles` | If set to "1", emits cosmetic particles (visual effects only).              |
| `create_real_particles`   | If set to "0", particles are purely visual and do not interact physically.  |
| `is_emitting`             | If set to "1", the emitter is active and will emit particles.             |