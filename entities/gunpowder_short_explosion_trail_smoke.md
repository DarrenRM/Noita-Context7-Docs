---
title: Gunpowder Short Explosion Trail Smoke
category: entities
---

---

# Gunpowder Short Explosion Trail Smoke

This entity defines the visual and physical properties of a short-lived smoke trail effect, typically associated with gunpowder explosions in Noita. It utilizes several particle emitters to create a dynamic and fading visual.

## Key Components

### VelocityComponent
Controls the movement and physics of the entity.

| Attribute        | Description                                     |
|------------------|-------------------------------------------------|
| `gravity_y`      | The strength of gravity pulling the entity down. |
| `air_friction`   | Resistance to movement in the air.              |
| `terminal_velocity` | The maximum speed the entity can reach due to gravity and friction. |
| `liquid_death_threshold` | Speed at which the entity dies if submerged in liquid. |

### SimplePhysicsComponent
Enables basic physics interactions for the entity.

### SetStartVelocityComponent
Determines the initial speed and direction of the entity.

| Attribute              | Description                                     |
|------------------------|-------------------------------------------------|
| `randomize_speed.min`  | Minimum initial speed.                          |
| `randomize_speed.max`  | Maximum initial speed.                          |
| `randomize_angle.min`  | Minimum initial angle (in radians).             |
| `randomize_angle.max`  | Maximum initial angle (in radians).             |

### DieIfSpeedBelowComponent
Causes the entity to be destroyed if its speed drops below a certain threshold.

| Attribute   | Description                                     |
|-------------|-------------------------------------------------|
| `min_speed` | The minimum speed required to survive.          |

### SpriteComponent
Defines the main visual representation of the entity.

| Attribute               | Description                                     |
|-------------------------|-------------------------------------------------|
| `image_file`            | Path to the sprite image.                       |
| `additive`              | Whether the sprite uses additive blending.      |
| `emissive`              | Whether the sprite emits light.                 |
| `alpha`                 | The transparency of the sprite.                 |
| `z_index`               | The rendering order of the sprite.              |
| `update_transform_rotation` | Whether the sprite's rotation updates with the entity's transform. |

### SpriteParticleEmitterComponent (x2)
These components are responsible for emitting smaller sprite-based particles.

**Emitter 1 (Fire Falling):**

| Attribute                     | Description                                     |
|-------------------------------|-------------------------------------------------|
| `sprite_file`                 | Path to the sprite image for emitted particles. |
| `emission_interval_min_frames`| Minimum frames between emissions.               |
| `emission_interval_max_frames`| Maximum frames between emissions.               |
| `count_min`                   | Minimum particles emitted per interval.         |
| `count_max`                   | Maximum particles emitted per interval.         |
| `additive`                    | Whether emitted particles use additive blending.|
| `emissive`                    | Whether emitted particles emit light.           |
| `scale.x`                     | Base X scale of emitted particles.              |
| `scale.y`                     | Base Y scale of emitted particles.              |
| `lifetime`                    | Duration each emitted particle exists.          |
| `randomize_scale.min_x`       | Minimum random X scale variation.               |
| `randomize_scale.max_x`       | Maximum random X scale variation.               |
| `randomize_velocity.min_y`    | Minimum random Y velocity for emitted particles.|
| `randomize_velocity.max_y`    | Maximum random Y velocity for emitted particles.|

**Emitter 2 (Gunpowder Smoke):**

| Attribute                     | Description                                     |
|-------------------------------|-------------------------------------------------|
| `sprite_file`                 | Path to the sprite image for emitted particles. |
| `emission_interval_min_frames`| Minimum frames between emissions.               |
| `emission_interval_max_frames`| Maximum frames between emissions.               |
| `count_min`                   | Minimum particles emitted per interval.         |
| `count_max`                   | Maximum particles emitted per interval.         |
| `additive`                    | Whether emitted particles use additive blending.|
| `emissive`                    | Whether emitted particles emit light.           |
| `scale.x`                     | Base X scale of emitted particles.              |
| `scale.y`                     | Base Y scale of emitted particles.              |
| `sprite_random_rotation`      | Whether emitted particles have random rotation. |
| `randomize_scale.min_x`       | Minimum random X scale variation.               |
| `randomize_scale.max_x`       | Maximum random X scale variation.               |
| `randomize_velocity.min_y`    | Minimum random Y velocity for emitted particles.|
| `randomize_velocity.max_y`    | Maximum random Y velocity for emitted particles.|
| `randomize_velocity.min_x`    | Minimum random X velocity for emitted particles.|
| `randomize_velocity.max_x`    | Maximum random X velocity for emitted particles.|

### ParticleEmitterComponent (x2)
These components emit "real" particles, which are more like distinct entities with their own physics.

**Emitter 1 (Smoke):**

| Attribute                   | Description                                     |
|-----------------------------|-------------------------------------------------|
| `emitted_material_name`     | The material type of the emitted particles (e.g., "smoke"). |
| `offset.x`                  | X offset from the entity's position.            |
| `offset.y`                  | Y offset from the entity's position.            |
| `x_pos_offset_min`          | Minimum random X position offset.               |
| `y_pos_offset_min`          | Minimum random Y position offset.               |
| `x_pos_offset_max`          | Maximum random X position offset.               |
| `y_pos_offset_max`          | Maximum random Y position offset.               |
| `x_vel_min`                 | Minimum X velocity of emitted particles.        |
| `x_vel_max`                 | Maximum X velocity of emitted particles.        |
| `y_vel_min`                 | Minimum Y velocity of emitted particles.        |
| `y_vel_max`                 | Maximum Y velocity of emitted particles.        |
| `count_min`                 | Minimum particles emitted per interval.         |
| `count_max`                 | Maximum particles emitted per interval.         |
| `lifetime_min`              | Minimum lifetime of emitted particles.          |
| `lifetime_max`              | Maximum lifetime of emitted particles.          |
| `create_real_particles`     | Whether to create actual particle entities.     |
| `emit_cosmetic_particles`   | Whether to emit cosmetic particles (visual only).|
| `emission_interval_min_frames`| Minimum frames between emissions.               |
| `emission_interval_max_frames`| Maximum frames between emissions.               |
| `is_emitting`               | Whether the emitter is currently active.        |

**Emitter 2 (Flame):**

| Attribute                   | Description                                     |
|-----------------------------|-------------------------------------------------|
| `emitted_material_name`     | The material type of the emitted particles (e.g., "flame"). |
| `offset.x`                  | X offset from the entity's position.            |
| `offset.y`                  | Y offset from the entity's position.            |
| `gravity.y`                 | Gravity applied to these specific particles.    |
| `x_pos_offset_min`          | Minimum random X position offset.               |
| `y_pos_offset_min`          | Minimum random Y position offset.               |
| `x_pos_offset_max`          | Maximum random X position offset.               |
| `y_pos_offset_max`          | Maximum random Y position offset.               |
| `x_vel_min`                 | Minimum X velocity of emitted particles.        |
| `x_vel_max`                 | Maximum X velocity of emitted particles.        |
| `y_vel_min`                 | Minimum Y velocity of emitted particles.        |
| `y_vel_max`                 | Maximum Y velocity of emitted particles.        |
| `count_min`                 | Minimum particles emitted per interval.         |
| `count_max`                 | Maximum particles emitted per interval.         |
| `lifetime_min`              | Minimum lifetime of emitted particles.          |
| `lifetime_max`              | Maximum lifetime of emitted particles.          |
| `create_real_particles`     | Whether to create actual particle entities.     |
| `emit_cosmetic_particles`   | Whether to emit cosmetic particles (visual only).|
| `emission_interval_min_frames`| Minimum frames between emissions.               |
| `emission_interval_max_frames`| Maximum frames between emissions.               |
| `is_emitting`               | Whether the emitter is currently active.        |