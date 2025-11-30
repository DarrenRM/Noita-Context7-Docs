---
title: Acid Shot Projectile
category: entities
---

# Acid Shot Projectile

This document details the configuration for the "Acid Shot" projectile in Noita, designed for AI-assisted modding.

## Core Entity Configuration

The projectile is defined as an `Entity` with tags indicating it's both `hittable` and a `projectile_player`. It inherits base properties from `base_projectile.xml`.

```xml
<Entity tags="hittable,projectile_player" name="$projectile_default">
    <Base file="data/entities/base_projectile.xml" />
    <!-- ... other components ... -->
</Entity>
```

## Projectile Component - Key Attributes

This component governs the projectile's behavior in flight and upon impact.

| Attribute                 | Value     | Description                                                                 |
| :------------------------ | :-------- | :-------------------------------------------------------------------------- |
| `speed_min`               | `90`      | Minimum projectile speed.                                                   |
| `speed_max`               | `108`     | Maximum projectile speed.                                                   |
| `on_death_explode`        | `1`       | Causes an explosion when the projectile dies.                               |
| `on_lifetime_out_explode` | `1`       | Causes an explosion when the projectile's lifetime expires.                 |
| `on_collision_die`        | `1`       | The projectile dies upon collision.                                         |
| `die_on_low_velocity`     | `1`       | The projectile dies if its velocity drops too low.                          |
| `damage`                  | `0.24`    | Base damage dealt by the projectile.                                        |
| `lifetime`                | `330`     | Duration in frames before the projectile expires.                           |
| `knockback_force`         | `1.0`     | Force applied to entities upon impact.                                      |
| `physics_impulse_coeff`   | `2000`    | Coefficient for physics impulse, affecting knockback and object interaction. |

### Explosion Configuration (`config_explosion`)

This nested configuration defines the properties of the explosion that occurs when the projectile dies.

| Attribute                 | Value     | Description                                                                 |
| :------------------------ | :-------- | :-------------------------------------------------------------------------- |
| `damage`                  | `0`       | Damage dealt by the explosion itself (distinct from projectile damage).     |
| `camera_shake`            | `3.5`     | Intensity of camera shake upon explosion.                                   |
| `explosion_radius`        | `9`       | The radius of the explosion effect.                                         |
| `explosion_sprite`        | `data/particles/explosion_032_slimeburst.xml` | GFX file for the explosion.                                                 |
| `create_cell_material`    | `acid`    | Material created at the explosion site.                                     |
| `create_cell_probability` | `40`      | Percentage chance to create the specified cell material.                    |
| `hole_enabled`            | `1`       | Enables the creation of holes in surfaces.                                  |
| `damage_mortals`          | `1`       | Whether the explosion damages living entities.                              |
| `physics_throw_enabled`   | `1`       | Enables physics-based throwing of objects by the explosion.                 |
| `stains_enabled`          | `1`       | Enables the creation of impact stains.                                      |
| `stains_radius`           | `9`       | Radius of the created stains.                                               |

## Sprite Component

Defines the visual appearance of the projectile.

| Attribute     | Value                           | Description                               |
| :------------ | :------------------------------ | :---------------------------------------- |
| `image_file`  | `data/projectiles_gfx/slimeball.xml` | The sprite image file for the projectile. |

## Particle Emitter Component

Responsible for generating cosmetic particles, often used for trails or impact effects.

| Attribute               | Value   | Description                                                               |
| :---------------------- | :------ | :------------------------------------------------------------------------ |
| `emitted_material_name` | `acid`  | The material of the particles being emitted.                              |
| `is_trail`              | `1`     | Indicates that this emitter is for creating a trail effect.               |
| `lifetime_min`          | `0.1`   | Minimum lifetime of emitted particles.                                    |
| `lifetime_max`          | `0.2`   | Maximum lifetime of emitted particles.                                    |
| `create_real_particles` | `1`     | Whether to create actual game particles.                                  |
| `emission_interval_min_frames` | `5` | Minimum frames between particle emissions.                                |
| `emission_interval_max_frames` | `8` | Maximum frames between particle emissions.                                |
| `is_emitting`           | `1`     | Whether the particle emitter is currently active.                         |

## Hitbox Component

Defines the collision area of the projectile.

| Attribute   | Value | Description                               |
| :---------- | :---- | :---------------------------------------- |
| `aabb_min_x`| `-5`  | Minimum X-coordinate of the bounding box. |
| `aabb_max_x`| `5`   | Maximum X-coordinate of the bounding box. |
| `aabb_min_y`| `-5`  | Minimum Y-coordinate of the bounding box. |
| `aabb_max_y`| `5`   | Maximum Y-coordinate of the bounding box. |

## Damage Model Component

Configures how the projectile interacts with damage and health.

| Attribute           | Value | Description                                                                 |
| :------------------ | :---- | :-------------------------------------------------------------------------- |
| `hp`                | `0.2` | Health points of the projectile itself.                                     |
| `blood_material`    | `acid`| The material that is created when the projectile takes damage (if applicable). |

## Audio Component

Specifies the sound effects associated with the projectile.

| Attribute   | Value                               | Description                               |
| :---------- | :---------------------------------- | :---------------------------------------- |
| `file`      | `data/audio/Desktop/projectiles.bank` | The audio bank file containing the sounds. |
| `event_root`| `player_projectiles/bullet_acid`    | The specific audio event for this projectile. |

## Variable Storage Component

Stores custom variables for the entity.

| Attribute    | Value                                | Description                                     |
| :----------- | :----------------------------------- | :---------------------------------------------- |
| `name`       | `projectile_file`                    | The name of the variable.                       |
| `value_string`| `data/entities/projectiles/deck/acidshot.xml` | The string value, referencing its own file. |