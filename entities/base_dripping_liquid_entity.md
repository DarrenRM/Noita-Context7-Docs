---
title: Base Dripping Liquid Entity
category: entities
---

# Base Dripping Liquid Entity

This document describes the `base_dripping_liquid.xml` entity, which serves as a foundational template for entities that drip liquid in Noita. It defines the core properties related to damage, collision, and particle emission for these dripping effects.

## Key Components

### DamageModelComponent

This component governs how the entity interacts with damage and its health.

| Attribute                 | Description                                                                 |
| :------------------------ | :-------------------------------------------------------------------------- |
| `hp`                      | The health points of the entity. Set to a very low value (0.2) for dripping effects. |
| `falling_damages`         | Whether the entity takes damage from falling. Set to "0".                   |
| `fire_damage_amount`      | The amount of damage taken from fire. Set to "0.2".                         |
| `fire_probability_of_ignition` | The chance of igniting from fire. Set to "0".                               |
| `blood_material`          | The material associated with blood effects (if any). Set to "water".        |
| `drop_items_on_death`     | Whether items are dropped upon death. Set to "0".                           |

### HitboxComponent

Defines the collision boundaries of the entity.

| Attribute     | Description                               |
| :------------ | :---------------------------------------- |
| `aabb_min_x`  | Minimum X-axis coordinate of the bounding box. |
| `aabb_max_x`  | Maximum X-axis coordinate of the bounding box. |
| `aabb_min_y`  | Minimum Y-axis coordinate of the bounding box. |
| `aabb_max_y`  | Maximum Y-axis coordinate of the bounding box. |

### CameraBoundComponent

Controls how the entity interacts with the camera's view.

| Attribute   | Description                                                              |
| :---------- | :----------------------------------------------------------------------- |
| `max_count` | The maximum number of this entity that can be active within the camera's view. |
| `distance`  | The maximum distance from the camera at which the entity can exist.      |

### ParticleEmitterComponent (x2)

These components are responsible for emitting particles to simulate the dripping effect. The entity uses two `ParticleEmitterComponent` instances, likely for different types of particle emissions (cosmetic vs. real).

**Emitter 1 (Cosmetic Particles):**

| Attribute                 | Description                                                                 |
| :------------------------ | :-------------------------------------------------------------------------- |
| `emitted_material_name`   | The material of the particles to be emitted. Set to "water".                |
| `x_pos_offset_min/max`    | The range of horizontal offset for particle emission.                       |
| `y_pos_offset_min/max`    | The range of vertical offset for particle emission.                         |
| `x_vel_min/max`           | The range of horizontal velocity for emitted particles.                     |
| `y_vel_min/max`           | The range of vertical velocity for emitted particles.                       |
| `count_min/max`           | The minimum and maximum number of particles emitted per interval.           |
| `lifetime_min/max`        | The minimum and maximum lifetime of emitted particles.                      |
| `emit_cosmetic_particles` | Whether to emit cosmetic particles. Set to "1".                             |
| `emission_interval_min_frames/max_frames` | The range of frames between particle emissions.                             |
| `is_emitting`             | Whether the emitter is currently active. Set to "1".                        |

**Emitter 2 (Real Particles):**

| Attribute                 | Description                                                                 |
| :------------------------ | :-------------------------------------------------------------------------- |
| `emitted_material_name`   | The material of the particles to be emitted. Set to "water".                |
| `x_pos_offset_min/max`    | The range of horizontal offset for particle emission.                       |
| `y_pos_offset_min/max`    | The range of vertical offset for particle emission.                         |
| `x_vel_min/max`           | The range of horizontal velocity for emitted particles.                     |
| `y_vel_min/max`           | The range of vertical velocity for emitted particles.                       |
| `count_min/max`           | The minimum and maximum number of particles emitted per interval.           |
| `lifetime_min/max`        | The minimum and maximum lifetime of emitted particles.                      |
| `create_real_particles`   | Whether to create actual game particles. Set to "1".                        |
| `emission_interval_min_frames/max_frames` | The range of frames between particle emissions.                             |
| `is_emitting`             | Whether the emitter is currently active. Set to "1".                        |

---