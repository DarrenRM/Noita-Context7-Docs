---
title: Wall Builder Projectile
category: entities
---

# Wall Builder Projectile

This entity defines the behavior and appearance of the "Wall Builder" projectile in Noita. It's a player-fired projectile designed to construct walls.

## Key Attributes

### Projectile Component

This is the core component defining the projectile's physical and functional properties.

| Attribute                 | Value        | Description                                                                                                |
| :------------------------ | :----------- | :--------------------------------------------------------------------------------------------------------- |
| `_enabled`                | `1`          | Enables the projectile component.                                                                            |
| `lob_min`, `lob_max`      | `0.8`, `1.0` | Controls the projectile's lobbing behavior (how much it arcs).                                             |
| `speed_min`, `speed_max`  | `1000`       | Sets the projectile's initial speed.                                                                       |
| `direction_random_rad`    | `0`          | No randomness in the projectile's initial direction.                                                       |
| `on_death_explode`        | `0`          | The projectile does not explode upon death.                                                                |
| `on_lifetime_out_explode` | `0`          | The projectile does not explode when its lifetime expires.                                                 |
| `explosion_dont_damage_shooter` | `1`      | If an explosion were to occur, it wouldn't damage the shooter.                                               |
| `velocity_sets_scale`     | `1`          | The projectile's velocity influences its scale.                                                            |
| `lifetime`                | `10`         | The projectile exists for 10 seconds before disappearing.                                                  |
| `damage`                  | `0`          | The projectile deals no direct damage.                                                                     |
| `ragdoll_fx_on_collision` | `BLOOD_SPRAY`| Applies a blood spray effect upon collision with a ragdoll.                                                |
| `camera_shake_when_shot`  | `5.0`        | Triggers a camera shake of magnitude 5.0 when the projectile is fired.                                     |
| `bounces_left`            | `0`          | The projectile does not bounce.                                                                            |
| `penetrate_entities`      | `1`          | The projectile can pass through other entities.                                                            |
| `penetrate_world`         | `1`          | The projectile can pass through the game world geometry.                                                   |

### Base Component

Inherits properties from the default projectile base.

| Attribute     | Value                               | Description                                                                                              |
| :------------ | :---------------------------------- | :------------------------------------------------------------------------------------------------------- |
| `file`        | `data/entities/base_projectile.xml` | Specifies the base entity file from which this projectile inherits its fundamental properties.           |
| `gravity_y`   | `0`                                 | The projectile is not affected by gravity in the Y-axis.                                                 |
| `mass`        | `0.04`                              | The projectile has a small mass.                                                                         |

### Light Component

Adds a light source to the projectile.

| Attribute | Value | Description