---
title: Quantum Split FX Red
category: entities
---

# Quantum Split FX Red

This entity defines a visual effect for the "quantum split" mechanic, specifically a red variant. It primarily uses a `SpriteComponent` for its visual representation and a `ParticleEmitterComponent` to generate cosmetic particles.

## Key Components

### SpriteComponent

This component defines the visual appearance of the entity.

| Attribute      | Value                                     | Description                                                                 |
|----------------|-------------------------------------------|-----------------------------------------------------------------------------|
| `emissive`     | `0`                                       | Indicates that the sprite does not emit light.                              |
| `additive`     | `1`                                       | The sprite uses additive blending, making it appear brighter when layered.  |
| `image_file`   | `data/projectiles_gfx/quantum_fx_red.xml` | Specifies the graphical asset used for the sprite.                          |

### ParticleEmitterComponent

This component is responsible for emitting cosmetic particles to enhance the visual effect.

| Attribute                 | Value   | Description                                                                                                |
|---------------------------|---------|------------------------------------------------------------------------------------------------------------|
| `emitted_material_name`   | `spark_red_bright` | The material name of the particles to be emitted.                                                          |
| `gravity.y`               | `0.0`   | The particles have no vertical gravity.                                                                    |
| `x_vel_min`, `x_vel_max`  | `0`     | The particles have no horizontal velocity.                                                                 |
| `y_vel_min`, `y_vel_max`  | `0`     | The particles have no vertical velocity.                                                                   |
| `friction`                | `10`    | A high friction value, suggesting particles quickly lose any imparted momentum.                              |
| `count_min`, `count_max`  | `1`     | A very small number of particles are emitted per emission event.                                           |
| `lifetime_min`, `lifetime_max` | `0.25` - `4.0` | The duration for which emitted particles will exist.                                                       |
| `emit_real_particles`     | `0`     | This emitter does not emit actual game physics particles, only cosmetic ones.                              |
| `render_on_grid`          | `1`     | The particles are rendered on the game grid.                                                               |
| `is_trail`                | `1`     | The particles are emitted as a trail.                                                                      |
| `trail_gap`               | `6`     | The spacing between particles in the trail.                                                                |
| `fade_based_on_lifetime`  | `1`     | Particles will fade out as their lifetime decreases.                                                       |
| `emit_cosmetic_particles` | `1`     | This emitter is specifically for cosmetic particles.                                                       |
| `emission_interval_min_frames`, `emission_interval_max_frames` | `1` | Particles are emitted continuously with no delay between emissions.                                          |
| `is_emitting`             | `1`     | The particle emitter is active and will emit particles.                                                    |