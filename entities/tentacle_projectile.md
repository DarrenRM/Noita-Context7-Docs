---
title: Tentacle Projectile
category: entities
---

# Tentacle Projectile

This document describes the `tentacle.xml` entity, which defines a player projectile in Noita. This projectile utilizes Verlet physics for its unique behavior, creating a segmented, whip-like effect.

## Key Components and Attributes

### ProjectileComponent

This component defines the core projectile properties.

| Attribute           | Value      | Description                                                                 |
| :------------------ | :--------- | :-------------------------------------------------------------------------- |
| `projectile_type`   | `VERLET`   | Specifies that this projectile uses Verlet physics.                         |
| `speed_min`         | `8`        | Minimum projectile speed.                                                   |
| `speed_max`         | `8`        | Maximum projectile speed.                                                   |
| `die_on_low_velocity` | `0`        | Projectile does not die when its velocity becomes low.                      |
| `on_death_explode`  | `0`        | Projectile does not explode upon death.                                     |
| `on_collision_die`  | `0`        | Projectile does not die upon collision with entities.                       |
| `penetrate_entities`| `1`        | Projectile can pass through multiple entities.                              |
| `damage`            | `0`        | Base damage of the projectile.                                              |
| `attach_to_parent_trigger` | `1`        | Projectile attaches to its parent trigger (useful for player projectiles). |
| `lifetime`          | `60`       | Duration in frames before the projectile is destroyed.                      |
| `knockback_force`   | `2.0`      | The force applied to entities when hit by the projectile.                   |

#### `damage_by_type`

| Type    | Value | Description                               |
| :------ | :---- | :---------------------------------------- |
| `melee` | `0.8` | Damage multiplier for melee attacks.      |

### VerletWeaponComponent

This component governs the specific behavior of the Verlet projectile, influencing its damage and physics interaction over time.

| Attribute         | Value   | Description                                                                                             |
| :---------------- | :------ | :------------------------------------------------------------------------------------------------------ |
| `fade_duration_frames` | `20`    | Duration in frames over which the projectile's visual effect fades out.                                 |
| `damage_min_step` | `0.01`  | Minimum damage dealt per segment of the tentacle per frame.                                             |
| `damage_max`      | `0.5`   | Maximum damage dealt per segment of the tentacle per frame.                                             |
| `damage_coeff`    | `0.0002`| Coefficient used to calculate damage based on segment movement.                                         |
| `impulse_coeff`   | `0.5`   | Coefficient for applying impulse (push) to entities.                                                    |
| `physics_impulse_coeff` | `7.0`   | Coefficient for applying physics-based impulse, likely affecting how the tentacle interacts with the environment. |

### VerletPhysicsComponent

This component defines the physical simulation for the Verlet projectile.

| Attribute             | Value | Description                                                                                             |
| :-------------------- | :---- | :------------------------------------------------------------------------------------------------------ |
| `num_points`          | `16`  | The number of points (segments) that make up the Verlet chain. More points create a smoother, more flexible tentacle. |
| `stiffness`           | `0.99`| Controls how rigid the segments are. Higher values mean less bending.                                   |
| `resting_distance`    | `4.0` | The preferred distance between adjacent points when the tentacle is not under tension.                  |
| `pixelate_sprite_transforms` | `1`   | Enables pixelation for sprite transformations, contributing to the visual style.                        |
| `simulate_wind`       | `0`   | Disables wind simulation for this projectile.                                                           |
| `constrain_stretching`| `0`   | Allows the segments to stretch beyond their resting distance.                                           |
| `simulate_gravity`    | `0`   | Disables gravity simulation for this projectile.                                                        |

### Base Files

The tentacle projectile is constructed from multiple base files, each likely defining a segment or visual aspect of the tentacle.

*   `data/entities/projectiles/tentacle/tentacle_0.xml`
*   `data/entities/projectiles/tentacle/tentacle_2.xml` (repeated multiple times)
*   `data/entities/projectiles/tentacle/tentacle_2b.xml`
*   `data/entities/projectiles/tentacle/tentacle_3.xml` (repeated multiple times)
*   `data/entities/projectiles/tentacle/tentacle_3b.xml`
*   `data/entities/projectiles/tentacle/tentacle_4.xml` (repeated multiple times)

These files collectively define the visual appearance and potentially some unique behaviors of each segment of the tentacle.

### AudioComponent

| Attribute   | Value                                 | Description                               |
| :---------- | :------------------------------------ | :---------------------------------------- |
| `file`      | `data/audio/Desktop/projectiles.bank` | Path to the audio bank file.              |
| `event_root`| `player_projectiles/bullet_tentacle`  | The root event name for projectile sounds. |

### VariableStorageComponent

| Attribute    | Value                                | Description                                                               |
| :----------- | :----------------------------------- | :------------------------------------------------------------------------ |
| `name`       | `projectile_file`                    | The name of the variable.                                                 |
| `value_string`| `data/entities/projectiles/deck/tentacle.xml` | Stores the path to this entity's XML file, useful for referencing. |