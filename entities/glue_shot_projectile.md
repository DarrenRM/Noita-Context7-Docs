---
title: Glue Shot Projectile
category: entities
---

# Glue Shot Projectile

This document details the `glue_shot.xml` entity, which defines the behavior and appearance of the Glue Shot projectile in Noita.

## Core Entity

The `Entity` tag defines the projectile itself, with the name `$projectile_default` and tagged as `projectile_player`.

```xml
<Entity
	name="$projectile_default" tags="projectile_player"
	>
	<!-- ... other components ... -->
</Entity>
```

## Base Projectile Configuration

The `Base` component inherits properties from the default projectile.

### VelocityComponent

Controls the projectile's movement characteristics.

| Attribute      | Value   | Description                               |
| -------------- | ------- | ----------------------------------------- |
| `air_friction` | `1.0`   | How much air resistance affects velocity. |
| `mass`         | `0.06`  | The mass of the projectile.               |

## Projectile Component

This is the primary component defining the Glue Shot's unique properties.

### Key Attributes

| Attribute                   | Value      | Description                                                                 |
| --------------------------- | ---------- | --------------------------------------------------------------------------- |
| `lob_min`, `lob_max`        | `0.8`, `1.3` | Controls the arc of the projectile.                                         |
| `speed_min`, `speed_max`    | `300`, `350` | The initial speed range of the projectile.                                  |
| `direction_random_rad`      | `0.15`     | Adds a small random deviation to the projectile's direction.                |
| `on_death_explode`          | `1`        | The projectile explodes when it dies (e.g., hits a surface).                |
| `on_lifetime_out_explode`   | `1`        | The projectile explodes when its lifetime expires.                          |
| `on_collision_die`          | `1`        | The projectile is destroyed upon collision.                                 |
| `lifetime`                  | `40`       | Base duration of the projectile before expiring.                            |
| `lifetime_randomness`       | `7`, `20`  | Adds randomness to the projectile's lifetime.                               |
| `damage`                    | `0.1`      | Base damage dealt by the projectile.                                        |
| `bounces_left`              | `2`        | The number of times the projectile can bounce before being destroyed.       |
| `bounce_at_any_angle`       | `1`        | Allows bouncing off surfaces regardless of the impact angle.                |
| `camera_shake_when_shot`    | `8.0`      | The intensity of camera shake when this projectile is fired.                |
| `knockback_force`           | `1.0`      | The force applied to knock back entities upon impact.                       |
| `physics_impulse_coeff`     | `2000`     | Coefficient for physics impulse applied on collision.                       |
| `ragdoll_fx_on_collision`   | `BLOOD_EXPLOSION` | The visual effect applied to ragdolls upon collision.                       |
| `muzzle_flash_file`         | `...`      | Specifies the particle effect for the muzzle flash when shot.               |

### `config_explosion`

Defines the properties of the explosion that occurs when the projectile dies.

| Attribute               | Value                               | Description                                                              |
| ----------------------- | ----------------------------------- | ------------------------------------------------------------------------ |
| `camera_shake`          | `0.3`                               | Camera shake intensity of the explosion.                                 |
| `explosion_radius`      | `4`                                 | The radius of the explosion effect.                                      |
| `explosion_sprite`      | `data/particles/explosion_032_glue.xml` | The sprite used for the explosion visual.                                |
| `load_this_entity`      | `data/entities/projectiles/glue.xml` | The entity to load/spawn upon explosion (likely the glue puddle).        |
| `hole_enabled`          | `1`                                 | Enables the creation of holes in surfaces from the explosion.            |
| `ray_energy`            | `50000`                             | Energy value for raycasting effects of the explosion.                    |
| `damage`                | `0.0`                               | Damage dealt by the explosion itself (note: `damage` in `ProjectileComponent` is for the projectile hit). |
| `physics_explosion_power.min`, `.max` | `0.3`, `0.5` | Controls the physics force applied by the explosion.                     |
| `shake_vegetation`      | `1`                                 | Whether the explosion shakes vegetation.                                 |
| `stains_enabled`        | `1`                                 | Enables the creation of stains on surfaces from the explosion.           |
| `stains_radius`         | `1`                                 | The radius of the stains created.                                        |
| `audio_event_name`      | `explosions/slime_small`            | The sound event triggered by the explosion.                              |

## Particle Emitter Component (Trail)

This component creates a visual trail behind the projectile.

| Attribute               | Value   | Description                                     |
| ----------------------- | ------- | ----------------------------------------------- |
| `emitted_material_name` | `glue`  | The material of the particles emitted.          |
| `x_vel_min`, `x_vel_max`| `-2`, `2` | Horizontal velocity range of emitted particles. |
| `y_vel_min`, `y_vel_max`| `-20`, `-10`| Vertical velocity range of emitted particles.   |
| `gravity.y`             | `0`     | Gravity applied to emitted particles.           |
| `count_min`, `count_max`| `1`, `1`  | Number of particles emitted per emission.       |
| `lifetime_min`, `max`   | `0.2`, `0.7`| Lifetime range of emitted particles.            |
| `is_trail`              | `1`     | Marks this emitter as a trail.                  |
| `trail_gap`             | `6`     | Spacing between trail particles.                |

## Sprite Component

Defines the visual representation of the projectile.

| Attribute    | Value                               | Description                               |
| ------------ | ----------------------------------- | ----------------------------------------- |
| `image_file` | `data/projectiles_gfx/glue_shot.xml`| The sprite file for the projectile.       |

## Light Component

Adds a light source to the projectile.

| Attribute | Value | Description             |
| --------- | ----- | ----------------------- |
| `radius`  | `10`  | The radius of the light. |

## Audio Component

Handles sound effects for the projectile.

| Attribute      | Value                     | Description                               |
| -------------- | ------------------------- | ----------------------------------------- |
| `file`         | `data/audio/Desktop/projectiles.bank` | The audio bank file.                      |
| `event_root`   | `projectiles/slime`       | The root event name for projectile sounds. |

## Variable Storage Component

Stores persistent variables related to the projectile.

| Attribute   | Value                                    | Description                               |
| ----------- | ---------------------------------------- | ----------------------------------------- |
| `name`      | `projectile_file`                        | The name of the variable.                 |
| `value_string`| `data/entities/projectiles/deck/glue_shot.xml` | The string value, referencing its own file. |