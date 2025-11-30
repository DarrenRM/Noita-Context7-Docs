---
title: Green Meteor Projectile
category: entities
---

# Green Meteor Projectile

This document details the configuration of the "Green Meteor" projectile entity in Noita, focusing on its behavior, visual effects, and damage properties.

## Core Projectile Properties

The `ProjectileComponent` defines the fundamental behavior of the projectile.

| Attribute           | Value        | Description                                                                 |
| :------------------ | :----------- | :-------------------------------------------------------------------------- |
| `lob_min`           | `0.8`        | Minimum lob angle for projectile trajectory.                                |
| `lob_max`           | `1.0`        | Maximum lob angle for projectile trajectory.                                |
| `speed_min`         | `300`        | Minimum projectile launch speed.                                            |
| `speed_max`         | `400`        | Maximum projectile launch speed.                                            |
| `on_death_explode`  | `1`          | Triggers an explosion upon projectile death (e.g., collision, lifetime end). |
| `on_lifetime_out_explode` | `1`      | Triggers an explosion when the projectile's lifetime expires.               |
| `damage`            | `0.7`        | Base damage dealt by the projectile.                                        |
| `lifetime`          | `800`        | Duration in frames before the projectile expires.                           |
| `knockback_force`   | `3.0`        | Force applied to entities upon collision.                                   |

### Damage Types

The `damage_by_type` sub-element specifies additional damage multipliers for specific damage types.

| Damage Type | Value   | Description                               |
| :---------- | :------ | :---------------------------------------- |
| `fire`      | `10.25` | Multiplier for fire damage.               |

## Explosion Configuration

The `config_explosion` sub-element within `ProjectileComponent` defines the properties of the explosion that occurs when the projectile dies or its lifetime ends.

| Attribute                 | Value                                                              | Description                                                                                             |
| :------------------------ | :----------------------------------------------------------------- | :------------------------------------------------------------------------------------------------------ |
| `camera_shake`            | `20.5`                                                             | Intensity of camera shake upon explosion.                                                               |
| `explosion_radius`        | `45`                                                               | Radius of the explosion's effect.                                                                       |
| `explosion_sprite`        | `data/particles/explosion_040_poof_green.xml`                      | Path to the particle effect used for the explosion.                                                     |
| `create_cell_probability` | `100`                                                              | Probability (0-100) of creating material cells.                                                         |
| `create_cell_material`    | `fire`                                                             | Material of the cells created by the explosion.                                                         |
| `damage`                  | `1.0`                                                              | Damage dealt by the explosion itself.                                                                   |
| `load_this_entity`        | `data/entities/particles/particle_explosion/main_green.xml,data/entities/misc/explosion_was_here.xml` | Entities to load upon explosion.                                                                        |
| `ray_energy`              | `7500000`                                                          | Energy value for raycasting effects from the explosion.                                                 |
| `hole_enabled`            | `1`                                                                | Enables the creation of holes in terrain by the explosion.                                              |
| `physics_explosion_power` | `min="2" max="4"`                                                  | Range for the physics force applied by the explosion.                                                   |
| `sparks_enabled`          | `1`                                                                | Enables the emission of sparks from the explosion.                                                      |
| `spark_material`          | `spark_green`                                                      | Material of the sparks emitted.                                                                         |

## Visual Representation

The `SpriteComponent` handles the visual appearance of the projectile.

| Attribute     | Value                               | Description                                                              |
| :------------ | :---------------------------------- | :----------------------------------------------------------------------- |
| `image_file`  | `data/projectiles_gfx/meteor_green.xml` | Path to the sprite definition file.                                      |
| `emissive`    | `1`                                 | Makes the sprite emit light.                                             |
| `additive`    | `1`                                 | Uses additive blending for the sprite, often for glowing effects.        |
| `z_index`     | `-0.5`                              | Controls the rendering order of the sprite.                              |

## Particle Emitters

Multiple `ParticleEmitterComponent` instances are used to create various visual effects associated with the projectile.

### Smoke Emitter

| Attribute             | Value   | Description                                                              |
| :-------------------- | :------ | :----------------------------------------------------------------------- |
| `emitted_material_name` | `smoke` | Material of the particles emitted.                                       |
| `count_min`           | `5`     | Minimum number of particles emitted per emission.                        |
| `count_max`           | `5`     | Maximum number of particles emitted per emission.                        |
| `lifetime_min`        | `0.1`   | Minimum lifetime of emitted particles.                                   |
| `lifetime_max`        | `0.3`   | Maximum lifetime of emitted particles.                                   |
| `create_real_particles` | `1`     | Whether to create actual physics-simulated particles.                    |

### Fire Emitters (Multiple)

These emitters contribute to the fiery appearance of the projectile and its explosion.

| Attribute             | Value   | Description                                                              |
| :-------------------- | :------ | :----------------------------------------------------------------------- |
| `emitted_material_name` | `fire`  | Material of the particles emitted.                                       |
| `count_min`           | `1`     | Minimum number of particles emitted per emission.                        |
| `count_max`           | `1`     | Maximum number of particles emitted per emission.                        |
| `lifetime_min`        | `0.1`   | Minimum lifetime of emitted particles.                                   |
| `lifetime_max`        | `0.3`   | Maximum lifetime of emitted particles.                                   |
| `create_real_particles` | `1`     | Whether to create actual physics-simulated particles.                    |
| `custom_style`        | `FIRE`  | Custom style for fire particles.                                         |
| `color`               | `ff9ae74a` | Specific color for this fire emitter.                                    |

### Green Spark Emitters (Multiple)

These emitters generate green sparks, contributing to the projectile's visual flair and explosion effects.

| Attribute             | Value   | Description                                                              |
| :-------------------- | :------ | :----------------------------------------------------------------------- |
| `emitted_material_name` | `spark_green` | Material of the particles emitted.                                       |
| `count_min`           | `40`    | Minimum number of particles emitted per emission.                        |
| `count_max`           | `100`   | Maximum number of particles emitted per emission.                        |
| `lifetime_min`        | `0.1`   | Minimum lifetime of emitted particles.                                   |
| `lifetime_max`        | `0.4`   | Maximum lifetime of emitted particles.                                   |
| `emit_cosmetic_particles` | `1`     | Whether to emit cosmetic particles (non-physics simulated).              |
| `create_real_particles` | `0`     | Whether to create actual physics-simulated particles.                    |
| `airflow_force`       | `2.5`   | Force applied to particles by airflow.                                   |
| `airflow_time`        | `1.401` | Duration of airflow effect.                                              |

### Large Green Fire Sprite Emitter

This emitter uses a specific sprite file for larger fire effects.

| Attribute             | Value                               | Description                                                              |
| :-------------------- | :---------------------------------- | :----------------------------------------------------------------------- |
| `sprite_file`         | `data/particles/fire_large_green.xml` | Path to the sprite definition for the emitted particles.                 |
| `count_min`           | `3`                                 | Minimum number of particles emitted per emission.                        |
| `count_max`           | `5`                                 | Maximum number of particles emitted per emission.                        |
| `emissive`            | `1`                                 | Makes the sprite emit light.                                             |
| `additive`            | `1`                                 | Uses additive blending for the sprite.                                   |
| `gravity.y`           | `10`                                | Gravity applied to the emitted sprites.                                  |
| `randomize_position`  | `min_x="-7" max_x="7" min_y="-7" max_y="7"` | Randomizes the spawn position of particles within this range.            |

## Lighting

The `LightComponent` adds a light source to the projectile.

| Attribute | Value | Description                               |
| :-------- | :---- | :---------------------------------------- |
| `radius`  | `150` | The radius of the light emitted.          |

## Audio

The `AudioComponent` and `AudioLoopComponent` handle the sound effects associated with the projectile.

| Component           | File                                | Event Root / Name                 | Description                               |
| :------------------ | :---------------------------------- | :-------------------------------- | :---------------------------------------- |
| `AudioComponent`    | `data/audio/Desktop/projectiles.bank` | `player_projectiles/meteor`       | Plays a sound event when the projectile is fired. |
| `AudioLoopComponent`| `data/audio/Desktop/projectiles.bank` | `player_projectiles/meteor/loop`  | Plays a looping sound while the projectile is active. |

## Variable Storage

The `VariableStorageComponent` stores a reference to the projectile's own entity file.

| Name             | Value                                   | Description                               |
| :--------------- | :-------------------------------------- | :---------------------------------------- |
| `projectile_file`| `data/entities/projectiles/deck/meteor_green.xml` | Stores the path to this entity's XML file. |