---
title: Pink Fast Orb Projectile
category: entities
---

# Pink Fast Orb Projectile

This document details the configuration of the "Pink Fast Orb" projectile entity in Noita, designed for AI-assisted modding.

## Entity Definition

The core entity definition for the pink fast orb.

```xml
<Entity 
  name="$projectile_default" 
   >
  </Entity>
```

## Base Projectile Configuration

Inherits fundamental projectile properties from `base_projectile.xml`.

### Velocity Component

Controls the movement and physics of the projectile.

| Attribute      | Value   | Description                                     |
|----------------|---------|-------------------------------------------------|
| `gravity_y`    | `0`     | No vertical gravity applied.                    |
| `air_friction` | `-1.5`  | High air friction, causing rapid deceleration.  |
| `mass`         | `0.06`  | Low mass, contributing to its speed.            |

## Projectile Component

Defines the specific behaviors and effects of this projectile.

| Attribute                   | Value   | Description                                                              |
|-----------------------------|---------|--------------------------------------------------------------------------|
| `_enabled`                  | `1`     | Enables this component.                                                  |
| `lob_min`, `lob_max`        | `0.8`, `1.0` | Controls the lobbing behavior (minimal to no lobbing).                   |
| `speed_min`, `speed_max`    | `100`, `190` | Sets the range of projectile speed.                                      |
| `die_on_low_velocity`       | `0`     | Projectile does not die solely due to low velocity.                      |
| `on_death_explode`          | `1`     | Explodes upon death.                                                     |
| `on_lifetime_out_explode`   | `1`     | Explodes when its lifetime expires.                                      |
| `explosion_dont_damage_shooter` | `1`     | The explosion does not harm the entity that fired it.                    |
| `damage`                    | `0.5`   | Base damage dealt by the projectile.                                     |
| `go_through_this_material`  | `crystal` | Can pass through "crystal" material without collision.                   |
| `on_collision_die`          | `1`     | Dies upon colliding with most surfaces.                                  |
| `velocity_sets_scale`       | `1`     | Projectile's velocity influences its scale.                              |
| `velocity_sets_scale_coeff` | `4.5`   | Coefficient for how velocity affects scale.                              |
| `lifetime`                  | `55`    | Duration in frames before the projectile expires.                        |
| `muzzle_flash_file`         | `...`   | Specifies the particle effect for the muzzle flash.                      |
| `shoot_light_flash_r/g/b`   | `255/90/245` | RGB values for the light flash when shot.                                |
| `shoot_light_flash_radius`  | `75`    | Radius of the light flash when shot.                                     |
| `knockback_force`           | `2.0`   | The force applied to knock back entities upon impact.                    |

### Config Explosion

Details the explosion effect when the projectile dies.

| Attribute                   | Value   | Description                                                              |
|-----------------------------|---------|--------------------------------------------------------------------------|
| `never_cache`               | `1`     | Prevents caching of this explosion for performance.                      |
| `camera_shake`              | `0`     | No camera shake is triggered by the explosion.                           |
| `explosion_radius`          | `10`    | The radius of the explosion's effect.                                    |
| `explosion_sprite`          | `...`   | Specifies the particle effect sprite for the explosion.                  |
| `explosion_sprite_lifetime` | `0.0`   | The explosion sprite has no independent lifetime.                        |
| `create_cell_probability`   | `0`     | No material cells are created by the explosion.                          |
| `ray_energy`                | `5000`  | Energy value for any potential ray interactions from the explosion.      |
| `hole_destroy_liquid`       | `1`     | The explosion can destroy liquids.                                       |
| `hole_enabled`              | `1`     | Creates a hole in surfaces upon explosion.                               |
| `hole_image`                | `...`   | Specifies the image used for the explosion hole.                         |
| `explosion_sprite_emissive` | `1`     | The explosion sprite is emissive.                                        |
| `explosion_sprite_additive` | `1`     | The explosion sprite uses additive blending.                             |
| `particle_effect`           | `0`     | No specific particle effect is directly spawned by the explosion component. |
| `damage_mortals`            | `0`     | The explosion does not directly damage living entities.                  |
| `physics_explosion_power.min/max` | `0.2/0.3` | Minimum and maximum power for physics-based explosions.                  |
| `physics_throw_enabled`     | `1`     | Physics objects can be thrown by the explosion.                          |
| `shake_vegetation`          | `1`     | The explosion can shake vegetation.                                      |
| `sparks_enabled`            | `0`     | No sparks are generated by the explosion.                                |
| `light_fade_time`           | `0.8`   | Time in seconds for the explosion's light to fade.                       |
| `light_r/g/b`               | `15/15/40` | RGB values for the light emitted by the explosion.                       |
| `stains_enabled`            | `0`     | No stains are left by the explosion.                                     |

## Sprite Components

Defines the visual appearance of the projectile.

### Primary Sprite

The main visual representation of the orb.

| Attribute      | Value   | Description                                     |
|----------------|---------|-------------------------------------------------|
| `_enabled`     | `1`     | Enables this sprite component.                  |
| `alpha`        | `1`     | Full opacity.                                   |
| `image_file`   | `...`   | Path to the sprite image file.                  |
| `rect_animation` | `spawn` | Uses the "spawn" animation from the image file. |

### Emissive Sprite

A secondary sprite, likely for glowing effects.

| Attribute      | Value   | Description                                     |
|----------------|---------|-------------------------------------------------|
| `_enabled`     | `1`     | Enables this sprite component.                  |
| `alpha`        | `1`     | Full opacity.                                   |
| `image_file`   | `...`   | Path to the sprite image file.                  |
| `rect_animation` | `spawn` | Uses the "spawn" animation from the image file. |
| `emissive`     | `1`     | The sprite is emissive (glows).                 |
| `additive`     | `1`     | Uses additive blending for a brighter glow.     |

## Light Component

Adds a light source to the projectile.

| Attribute | Value | Description                               |
|-----------|-------|-------------------------------------------|
| `_enabled`| `1`   | Enables the light component.              |
| `radius`  | `150` | The radius of the light emitted.          |
| `r/g/b`   | `130/35/90` | RGB values for the light color. |

## Audio Component

Manages the sound effects associated with the projectile.

| Attribute   | Value                               | Description                               |
|-------------|-------------------------------------|-------------------------------------------|
| `file`      | `data/audio/Desktop/projectiles.bank` | Path to the audio bank file.              |
| `event_root`| `projectiles/orb_pink_fast`         | The root event name for projectile sounds. |

## Variable Storage Component

Stores custom variables for the entity.

| Attribute   | Value                               | Description                               |
|-------------|-------------------------------------|-------------------------------------------|
| `name`      | `projectile_file`                   | The name of the variable.                 |
| `value_string`| `data/entities/projectiles/orb_pink_fast.xml` | The string value, referencing its own file. |