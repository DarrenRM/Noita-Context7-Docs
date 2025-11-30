---
title: Death Cross Big Laser Projectile
category: entities
---

# Death Cross Big Laser Projectile

This document details the configuration for the "Death Cross Big Laser" projectile in Noita, designed for AI-assisted modding.

## Core Entity

The projectile is defined as an `Entity` with the tag `projectile_player`.

```xml
<Entity
  name="$projectile_default" tags="projectile_player"
>
  </Entity>
```

## Base Projectile Properties

Inherits fundamental projectile behavior from `base_projectile.xml`.

### Velocity Component

Controls the projectile's movement characteristics.

| Attribute      | Value   | Description                                    |
|----------------|---------|------------------------------------------------|
| `air_friction` | `1`     | Resistance to movement in the air.             |
| `gravity_y`    | `0`     | Vertical acceleration due to gravity.          |
| `mass`         | `0.09`  | The projectile's mass, affecting its inertia. |

## Projectile Component

Defines the specific behaviors and effects of this projectile.

### Key Attributes

| Attribute                   | Value    | Description                                                                 |
|-----------------------------|----------|-----------------------------------------------------------------------------|
| `lob_min`, `lob_max`        | `0.8`, `1.0` | Minimum and maximum lob angle (deviation from straight trajectory).         |
| `speed_min`, `speed_max`    | `180`, `240` | Minimum and maximum projectile speed.                                       |
| `friction`                  | `1`      | Friction applied to the projectile.                                         |
| `direction_random_rad`      | `0.03`   | Random deviation in projectile direction upon firing.                       |
| `on_death_explode`          | `1`      | Triggers an explosion when the projectile dies.                             |
| `on_lifetime_out_explode`   | `1`      | Triggers an explosion when the projectile's lifetime expires.               |
| `explosion_dont_damage_shooter` | `1`      | Prevents the explosion from damaging the entity that fired it.              |
| `on_collision_die`          | `1`      | The projectile dies upon colliding with something.                          |
| `lifetime`                  | `50`     | Base duration of the projectile before expiring.                            |
| `lifetime_randomness`       | `7`      | Random variation added to the projectile's lifetime.                        |
| `damage`                    | `1.15`   | Base damage dealt by the projectile.                                        |
| `knockback_force`           | `2.8`    | Force applied to push entities away upon impact.                            |
| `camera_shake_when_shot`    | `0.4`    | Intensity of camera shake when the projectile is fired.                     |
| `muzzle_flash_file`         | `...`    | Path to the particle effect used for the muzzle flash.                      |
| `shoot_light_flash_radius`  | `100`    | Radius of the light flash emitted when the projectile is shot.              |
| `physics_impulse_coeff`     | `4000`   | Coefficient for physics impulse, affecting how it interacts with physics. |

### Explosion Configuration (`config_explosion`)

Details of the explosion triggered by the projectile.

| Attribute                 | Value      | Description                                                              |
|---------------------------|------------|---------------------------------------------------------------------------|
| `damage`                  | `0.38`     | Damage dealt by the explosion.                                            |
| `camera_shake`            | `20.0`     | Intensity of camera shake caused by the explosion.                        |
| `explosion_radius`        | `20`       | The radius of the explosion's effect.                                     |
| `explosion_sprite`        | `...`      | Path to the sprite used for the explosion visual.                         |
| `create_cell_probability` | `10`       | Chance (out of 100) to create material cells upon explosion.              |
| `create_cell_material`    | `spark_green` | The material of the cells created by the explosion.                       |
| `hole_enabled`            | `1`        | Enables the creation of holes in terrain by the explosion.                |
| `ray_energy`              | `2050000`  | Energy value for raycasting effects of the explosion.                     |
| `max_durability_to_destroy` | `11`       | Maximum durability of objects that can be destroyed by the explosion.     |
| `physics_explosion_power` | `0.15-0.35`| Range for the power of the physics-based explosion impulse.               |
| `sparks_enabled`          | `1`        | Enables the emission of sparks from the explosion.                        |
| `material_sparks_count`   | `20-40`    | Range for the number of material sparks emitted.                          |
| `stains_enabled`          | `1`        | Enables the creation of impact stains.                                    |
| `stains_radius`           | `1`        | Radius of the impact stains.                                              |

## Sprite Component

Defines the visual appearance of the projectile.

| Attribute    | Value   | Description                               |
|--------------|---------|-------------------------------------------|
| `image_file` | `...`   | Path to the sprite image file.            |
| `offset_x`   | `2`     | Horizontal offset of the sprite.          |
| `offset_y`   | `2`     | Vertical offset of the sprite.            |

## Light Component

Adds a light source to the projectile.

| Attribute | Value | Description                               |
|-----------|-------|-------------------------------------------|
| `radius`  | `150` | The radius of the light emitted.          |
| `r`, `g`, `b` | `3`, `9`, `3` | RGB color values of the light. |

## Particle Emitter Component

Responsible for emitting cosmetic particles, creating a trail effect.

| Attribute                 | Value         | Description                                                               |
|---------------------------|---------------|---------------------------------------------------------------------------|
| `emitted_material_name`   | `plasma_fading_green` | The material of the particles being emitted.                              |
| `count_min`, `count_max`  | `1`, `1`      | Minimum and maximum number of particles emitted per emission.             |
| `lifetime_min`, `lifetime_max` | `0.1`, `0.3`  | Minimum and maximum lifetime of emitted particles.                        |
| `is_trail`                | `1`           | Indicates that this emitter is for a trail effect.                        |
| `trail_gap`               | `0.5`         | The gap between particles in the trail.                                   |
| `emit_cosmetic_particles` | `1`           | Enables the emission of cosmetic particles.                               |
| `emission_interval_frames`| `1-2`         | The interval in frames between particle emissions.                        |

## Variable Storage Component

Stores a variable related to the projectile's own file path.

| Attribute    | Value                                      | Description                                     |
|--------------|--------------------------------------------|-------------------------------------------------|
| `name`       | `projectile_file`                          | The name of the variable.                       |
| `value_string` | `data/entities/projectiles/deck/death_cross_big_laser.xml` | The string value of the variable (its own path). |