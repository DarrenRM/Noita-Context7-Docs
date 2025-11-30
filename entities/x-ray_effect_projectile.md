---
title: X-Ray Effect Projectile
category: entities
---

# X-Ray Effect Projectile

This entity defines a projectile that applies an X-ray effect. It's designed to pass through the world and entities without causing damage or explosions, primarily serving as a visual or utility effect.

## Key Components and Attributes

### ProjectileComponent

This is the core component defining the projectile's behavior.

| Attribute                 | Value      | Description                                                                 |
| :------------------------ | :--------- | :-------------------------------------------------------------------------- |
| `_enabled`                | `1`        | Enables the projectile component.                                           |
| `speed_min`               | `600`      | Minimum projectile speed.                                                   |
| `speed_max`               | `600`      | Maximum projectile speed.                                                   |
| `die_on_low_velocity`     | `0`        | Projectile does not die if its velocity becomes too low.                    |
| `on_death_explode`        | `0`        | Projectile does not explode upon death.                                     |
| `on_lifetime_out_explode` | `1`        | Projectile explodes when its lifetime expires.                              |
| `on_collision_die`        | `0`        | Projectile does not die upon collision with entities or world.              |
| `penetrate_entities`      | `1`        | Projectile can pass through entities.                                       |
| `collide_with_entities`   | `0`        | Projectile does not trigger collision events with entities.                 |
| `penetrate_world`         | `1`        | Projectile can pass through the game world geometry.                        |
| `damage`                  | `0`        | Projectile deals no damage.                                                 |
| `lifetime`                | `50`       | Duration in frames before the projectile expires and potentially explodes. |

#### `config_explosion` (within `ProjectileComponent`)

This sub-configuration defines the explosion properties when `on_lifetime_out_explode` is true.

| Attribute               | Value | Description                                                              |
| :---------------------- | :---- | :----------------------------------------------------------------------- |
| `never_cache`           | `1`   | Prevents caching of this explosion configuration.                        |
| `damage`                | `0`   | Explosion deals no damage.                                               |
| `camera_shake`          | `0`   | No camera shake is applied.                                              |
| `explosion_radius`      | `0`   | Explosion has no radius.                                                 |
| `particle_effect`       | `0`   | No particle effects are spawned by the explosion.                        |
| `damage_mortals`        | `0`   | Explosion does not damage mortals.                                       |
| `physics_explosion_power` | `0`   | Explosion has no physics force.                                          |
| `hole_enabled`          | `0`   | No holes are created in the world by the explosion.                      |

### VelocityComponent

This component controls the projectile's movement physics.

| Attribute   | Value | Description                               |
| :---------- | :---- | :---------------------------------------- |
| `air_friction` | `0`   | No air friction is applied.               |
| `gravity_y` | `0`   | No gravity affects the projectile vertically. |

### SpriteParticleEmitterComponent

This component emits particles to create a visual effect for the projectile.

| Attribute              | Value     | Description