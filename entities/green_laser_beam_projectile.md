---
title: Green Laser Beam Projectile
category: entities
---

---

# Green Laser Beam Projectile

This document details the configuration of the `laserbeam_green.xml` entity, which defines the behavior and appearance of the green laser beam projectile in Noita.

## Core Components

### Entity
The root element defining the projectile.

### Base Projectile
Inherits fundamental projectile properties.

#### VelocityComponent
Controls the projectile's movement characteristics.

| Attribute      | Value   | Description                                    |
|----------------|---------|------------------------------------------------|
| `gravity_y`    | `0`     | No vertical gravity applied.                   |
| `air_friction` | `-4`    | Negative friction to counteract air resistance. |
| `mass`         | `0.04`  | The mass of the projectile.                    |

### ProjectileComponent
Defines the specific behaviors and effects of this projectile.

| Attribute                 | Value   | Description                                                                 |
|---------------------------|---------|-----------------------------------------------------------------------------|
| `_enabled`                | `1`     | Enables the component.                                                      |
| `speed_min`               | `130`   | Minimum initial speed.                                                      |
| `speed_max`               | `150`   | Maximum initial speed.                                                      |
| `friction`                | `-15.0` | Friction applied to slow down the projectile.                               |
| `on_death_explode`        | `1`     | The projectile explodes upon death.                                         |
| `on_lifetime_out_explode` | `1`     | The projectile explodes when its lifetime expires.                          |
| `on_collision_die`        | `1`     | The projectile dies upon collision.                                         |
| `lifetime`                | `60`    | Base lifetime in frames.                                                    |
| `lifetime_randomness`     | `7`     | Randomness added to the lifetime.                                           |
| `damage`                  | `0.15`  | Base damage dealt by the projectile.                                        |
| `knockback_force`         | `1.5`   | The force applied to knock back targets.                                    |
| `camera_shake_when_shot`  | `2.0`   | Camera shake effect when the projectile is fired.                           |
| `shoot_light_flash_radius`| `180`   | Radius of the light flash when fired.                                       |
| `muzzle_flash_file`       | `data/entities/particles/muzzle_flashes/muzzle_flash_laser_green.xml` | Specifies the muzzle flash particle effect. |

#### config_explosion
Defines the properties of the explosion when the projectile dies or its lifetime expires.

| Attribute                 | Value   | Description                                                                 |
|---------------------------|---------|-----------------------------------------------------------------------------|
| `camera_shake`            | `4.5`   | Camera shake intensity of the explosion.                                    |
| `explosion_radius`        | `3`     | The radius of the explosion.                                                |
| `explosion_sprite`        | `data/particles/explosion_016_plasma_green.xml` | The sprite used for the explosion.                                          |
| `create_cell_material`    | `plasma_fading` | Material created by the explosion.                                          |
| `create_cell_probability` | `15`    | Probability of creating a cell material.                                    |
| `hole_enabled`            | `1`     | Enables the creation of holes in terrain.                                   |
| `ray_energy`              | `10000` | Energy of the explosion's damaging rays.                                    |
| `damage`                  | `0.1`   | Damage dealt by the explosion itself.                                       |
| `physics_explosion_power.min` | `0.2` | Minimum physics force applied by the explosion.                             |
| `physics_explosion_power.max` | `0.7` | Maximum physics force applied by the explosion.                             |
| `stains_enabled`          | `1`     | Enables the creation of stains from the explosion.                          |
| `stains_radius`           | `4`     | Radius of the stains created.                                               |

### SpriteComponent
Defines the visual representation of the projectile.

| Attribute     | Value                                | Description                               |
|---------------|--------------------------------------|-------------------------------------------|
| `image_file`  | `data/projectiles_gfx/laser_green.xml` | The sprite image file for the projectile. |
| `offset_x`    | `2`                                  | Horizontal offset of the sprite.          |
| `offset_y`    | `2`                                  | Vertical offset of the sprite.            |

### LightComponent
Adds a light source to the projectile.

| Attribute | Value | Description              |
|-----------|-------|--------------------------|
| `radius`  | `150` | The radius of the light. |
| `r`       | `3`   | Red component of light.  |
| `g`       | `9`   | Green component of light.|
| `b`       | `3`   | Blue component of light. |

### ParticleEmitterComponent
Manages particle effects emitted by the projectile, likely for a trail.

| Attribute                 | Value   | Description                                                                 |
|---------------------------|---------|-----------------------------------------------------------------------------|
| `emitted_material_name`   | `plasma_fading_green` | The material of the emitted particles.                                      |
| `lifetime_min`            | `0.1`   | Minimum lifetime of emitted particles.                                      |
| `lifetime_max`            | `0.3`   | Maximum lifetime of emitted particles.                                      |
| `is_trail`                | `1`     | Indicates that these particles form a trail.                                |
| `trail_gap`               | `0.5`   | The gap between particles in the trail.                                     |
| `emit_cosmetic_particles` | `1`     | Emits cosmetic particles (visual effects only).                             |
| `emission_interval_min_frames` | `1` | Minimum frames between particle emissions.                                  |
| `emission_interval_max_frames` | `2` | Maximum frames between particle emissions.                                  |

### AudioComponent
Handles sound effects associated with the projectile.

| Attribute   | Value                                | Description                               |
|-------------|--------------------------------------|-------------------------------------------|
| `file`      | `data/audio/Desktop/projectiles.bank`| The audio bank file.                      |
| `event_root`| `projectiles/laser_small`            | The root event for projectile sounds.     |

### VariableStorageComponent
Stores custom variables for the entity.

| Attribute    | Value                                | Description                               |
|--------------|--------------------------------------|-------------------------------------------|
| `name`       | `projectile_file`                    | The name of the variable.                 |
| `value_string`| `data/entities/projectiles/laserbeam_green.xml` | The value of the variable, referencing its own file. |