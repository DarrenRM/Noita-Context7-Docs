---
title: Sampo Working Entity
category: entities
---

# Sampo Working Entity

This entity represents a "Sampo Working" object, likely a decorative or functional element within the game world. It primarily consists of visual components and particle effects.

## Key Components

### SpriteComponent

This component defines the visual appearance of the entity.

| Attribute      | Value                                       | Description                                                                 |
|----------------|---------------------------------------------|-----------------------------------------------------------------------------|
| `image_file`   | `data/entities/animals/boss_centipede/sampo_working_sprite.xml` | Path to the sprite definition file.                                         |
| `offset_x`     | `12`                                        | Horizontal offset for the sprite.                                           |
| `offset_y`     | `12`                                        | Vertical offset for the sprite.                                             |
| `z_index`      | `1.5`                                       | Determines the rendering order (higher values are drawn on top).            |
| `_tags`        | `enabled_in_world,enabled_in_hand`          | Tags indicating when this sprite should be active.                          |

### ParticleEmitterComponent (World)

This component emits blue sparks when the entity is in the world.

| Attribute                 | Value   | Description                                                                 |
|---------------------------|---------|-----------------------------------------------------------------------------|
| `_tags`                   | `enabled_in_world,enabled_in_hand` | Tags indicating when this emitter should be active.                         |
| `emitted_material_name`   | `spark_blue` | The material of the particles to be emitted.                                |
| `gravity.y`               | `0.0`   | Vertical gravity applied to particles.                                      |
| `lifetime_min`            | `1`     | Minimum lifetime of emitted particles in seconds.                           |
| `lifetime_max`            | `3`     | Maximum lifetime of emitted particles in seconds.                           |
| `x_vel_min`               | `-5`    | Minimum horizontal velocity of emitted particles.                           |
| `x_vel_max`               | `5`     | Maximum horizontal velocity of emitted particles.                           |
| `y_vel_min`               | `-20`   | Minimum vertical velocity of emitted particles.                             |
| `y_vel_max`               | `5`     | Maximum vertical velocity of emitted particles.                             |
| `count_min`               | `55`    | Minimum number of particles emitted per emission.                           |
| `count_max`               | `55`    | Maximum number of particles emitted per emission.                           |
| `emission_interval_min_frames` | `12` | Minimum frames between particle emissions.                                  |
| `emission_interval_max_frames` | `12` | Maximum frames between particle emissions.                                  |
| `area_circle_radius.max`  | `12`    | Maximum radius of the circular emission area.                               |
| `cosmetic_force_create`   | `1`     | Forces the creation of cosmetic particles.                                  |
| `collide_with_grid`       | `0`     | Whether particles should collide with the game grid.                        |
| `render_back`             | `1`     | Whether particles should be rendered behind other elements.                 |
| `is_emitting`             | `1`     | Whether the emitter is currently active.                                    |

### ParticleEmitterComponent (Inventory) - Sparks

This component emits yellow sparks when the entity is in the inventory.

| Attribute                 | Value   | Description                                                                 |
|---------------------------|---------|-----------------------------------------------------------------------------|
| `_tags`                   | `enabled_in_inventory` | Tags indicating when this emitter should be active.                         |
| `emitted_material_name`   | `spark_yellow` | The material of the particles to be emitted.                                |
| `lifetime_min`            | `1.5`   | Minimum lifetime of emitted particles in seconds.                           |
| `lifetime_max`            | `8.5`   | Maximum lifetime of emitted particles in seconds.                           |
| `count_min`               | `0`     | Minimum number of particles emitted per emission.                           |
| `count_max`               | `1`     | Maximum number of particles emitted per emission.                           |
| `area_circle_radius.max`  | `6`     | Maximum radius of the circular emission area.                               |
| `attractor_force`         | `2`     | Force that attracts particles towards a point.                              |
| `emission_interval_min_frames` | `4` | Minimum frames between particle emissions.                                  |
| `emission_interval_max_frames` | `30` | Maximum frames between particle emissions.                                  |
| `is_emitting`             | `1`     | Whether the emitter is currently active.                                    |

### ParticleEmitterComponent (Inventory) - Gold

This component emits gold particles when the entity is in the inventory.

| Attribute                 | Value   | Description                                                                 |
|---------------------------|---------|-----------------------------------------------------------------------------|
| `_tags`                   | `enabled_in_inventory` | Tags indicating when this emitter should be active.                         |
| `emitted_material_name`   | `gold`  | The material of the particles to be emitted.                                |
| `lifetime_min`            | `2.5`   | Minimum lifetime of emitted particles in seconds.                           |
| `lifetime_max`            | `13.5`  | Maximum lifetime of emitted particles in seconds.                           |
| `count_min`               | `0`     | Minimum number of particles emitted per emission.                           |
| `count_max`               | `1`     | Maximum number of particles emitted per emission.                           |
| `area_circle_radius.max`  | `4`     | Maximum radius of the circular emission area.                               |
| `attractor_force`         | `2`     | Force that attracts particles towards a point.                              |
| `emission_interval_min_frames` | `4` | Minimum frames between particle emissions.                                  |
| `emission_interval_max_frames` | `30` | Maximum frames between particle emissions.                                  |
| `is_emitting`             | `1`     | Whether the emitter is currently active.                                    |

### SpriteAnimatorComponent

This component enables sprite animations for the entity.

## Entity Tags

*   `teleportable_NOT`: This entity cannot be teleported.