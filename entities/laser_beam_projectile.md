---
title: Laser Beam Projectile
category: entities
---

---

# Laser Beam Projectile

This document details the configuration of the default laser beam projectile in Noita, as defined in `data/entities/projectiles/laserbeam.xml`. This projectile is characterized by its rapid speed, moderate lifetime, and a distinct visual and auditory presence.

## Key Components and Attributes

The `laserbeam.xml` file defines a projectile with several core components that dictate its behavior, appearance, and effects.

### ProjectileComponent

This is the primary component defining the projectile's physical and behavioral properties.

| Attribute                 | Description                                                                 | Value Example       |
| :------------------------ | :-------------------------------------------------------------------------- | :------------------ |
| `_enabled`                | Enables or disables the component.                                          | `1`                 |
| `lob_min`, `lob_max`      | Minimum and maximum lob angle (in radians) for projectile trajectory.       | `0.8`, `1.0`        |
| `speed_min`, `speed_max`  | Minimum and maximum initial speed of the projectile.                        | `130`, `150`        |
| `friction`                | Friction applied to the projectile, affecting its deceleration.             | `-15.0`             |
| `direction_random_rad`    | Randomness applied to the projectile's initial direction in radians.        | `0`                 |
| `on_death_explode`        | Whether the projectile explodes upon death.                                 | `1`                 |
| `on_lifetime_out_explode` | Whether the projectile explodes when its lifetime expires.                  | `1`                 |
| `on_collision_die`        | Whether the projectile dies upon colliding with an entity.                  | `1`                 |
| `die_on_liquid_collision` | Whether the projectile dies upon colliding with a liquid.                     | `1`                 |
| `lifetime`                | The base lifetime of the projectile in frames.                              | `30`                |
| `lifetime_randomness`     | Randomness added to the projectile's lifetime.                              | `7`                 |
| `damage`                  | The base damage dealt by the projectile.                                    | `0.35`              |
| `knockback_force`         | The force applied to entities when hit by the projectile.                   | `1.5`               |
| `camera_shake_when_shot`  | The intensity of camera shake when this projectile is fired.                | `2.0`               |
| `bounces_left`            | The number of bounces the projectile can perform before dying.              | `10`                |
| `muzzle_flash_file`       | Path to the particle effect file used for the muzzle flash.                 | `data/entities/particles/muzzle_flashes/muzzle_flash_laser.xml` |

#### `config_explosion` (Nested within `ProjectileComponent`)

Defines the properties of the explosion that occurs when the projectile dies or its lifetime expires.

| Attribute                 | Description                                                                 | Value Example       |
| :------------------------ | :-------------------------------------------------------------------------- | :------------------ |
| `never_cache`             | Prevents the explosion from being cached, ensuring unique instances.         | `1`                 |
| `camera_shake`            | Intensity of camera shake during the explosion.                             | `4.5`               |
| `explosion_radius`        | The radius of the explosion effect.                                         | `3`                 |
| `explosion_sprite`        | Path to the sprite file used for the explosion visual.                      | `data/particles/explosion_016_plasma.xml` |
| `create_cell_material`    | The material created in the world by the explosion.                         | `plasma_fading`     |
| `create_cell_probability` | The probability (in percent) of creating a cell material.                   | `15`                |
| `hole_enabled`            | Whether the explosion creates a hole in the environment.                    | `1`                 |
| `ray_energy`              | The energy of the explosion's damaging rays.                                | `10000`             |
| `damage`                  | Damage dealt by the explosion itself (distinct from projectile damage).     | `0`                 |
| `physics_explosion_power` | Minimum and maximum power of the physics-based explosion force.             | `0.2` - `0.7`       |
| `stains_enabled`          | Whether the explosion leaves stains on surfaces.                            | `1`                 |
| `stains_radius`           | The radius of the stains left by the explosion.                             | `4`                 |

### SpriteComponent

Defines the visual representation of the projectile.

| Attribute     | Description                               | Value Example             |
| :------------ | :---------------------------------------- | :------------------------ |
| `_enabled`    | Enables or disables the component.        | `1`                       |
| `image_file`  | Path to the sprite image file.            | `data/projectiles_gfx/laser.xml` |
| `alpha`       | Transparency of the sprite.               | `1`                       |

### LightComponent

Adds a light source to the projectile.

| Attribute  | Description                               | Value Example |
| :--------- | :---------------------------------------- | :------------ |
| `_enabled` | Enables or disables the component.        | `1`           |
| `radius`   | The radius of the light emitted.          | `150`         |
| `r`, `g`, `b` | Red, Green, and Blue color components.    | `30`, `30`, `60` |

### ParticleEmitterComponent

Responsible for emitting trail particles.

| Attribute               | Description                                                                 | Value Example |
| :---------------------- | :-------------------------------------------------------------------------- | :------------ |
| `emitted_material_name` | The material name of the particles to be emitted.                           | `plasma_fading` |
| `is_trail`              | Indicates if these particles form a trail.                                  | `1`           |
| `trail_gap`             | The spacing between trail particles.                                        | `0.5`         |
| `lifetime_min`, `lifetime_max` | Minimum and maximum lifetime of emitted particles.                          | `0.2`, `0.4`  |
| `emit_cosmetic_particles` | Whether to emit cosmetic particles (visual effects only).                   | `1`           |

### SpriteParticleEmitterComponent

Emits specific sprite-based particles, likely for sparks or secondary effects.

| Attribute                 | Description                                                                 | Value Example |
| :------------------------ | :-------------------------------------------------------------------------- | :------------ |
| `sprite_file`             | Path to the sprite file for the emitted particles.                          | `data/particles/spark_electric.xml` |
| `emission_interval_min_frames`, `emission_interval_max_frames` | The frame interval between particle emissions. | `1`, `3`      |
| `count_min`, `count_max`  | The number of particles emitted per interval.                               | `1`, `1`      |
| `randomize_rotation`      | Random range for particle rotation.                                         | `-3.1415` to `3.1415` |
| `randomize_position`      | Random range for particle spawn position.                                   | `-2` to `2`   |

### AudioComponent

Handles the sound effects associated with the projectile.

| Attribute   | Description                               | Value Example                     |
| :---------- | :---------------------------------------- | :-------------------------------- |
| `file`      | Path to the audio bank file.              | `data/audio/Desktop/projectiles.bank` |
| `event_root`| The root event name for projectile sounds. | `projectiles/laser`               |

### VariableStorageComponent

Stores custom variables for the entity.

| Attribute   | Description                               | Value Example                     |
| :---------- | :---------------------------------------- | :-------------------------------- |
| `name`      | The name of the variable.                 | `projectile_file`                 |
| `value_string` | The string value of the variable.         | `data/entities/projectiles/laserbeam.xml` |