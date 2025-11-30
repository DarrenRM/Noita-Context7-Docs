---
title: Bounce Laser Projectile
category: entities
---

# Bounce Laser Projectile

This document details the configuration for the "bounce_laser" projectile entity in Noita, designed for AI-assisted modding.

## Core Entity Configuration

The projectile is based on the default player projectile and inherits its fundamental properties.

```xml
<Entity 
  name="$projectile_default" tags="projectile_player"
>
  <Base file="data/entities/base_projectile.xml" />
  <!-- ... other components ... -->
</Entity>
```

## Projectile Component - Key Attributes

This component defines the projectile's behavior, including its movement, interaction with the environment, and damage.

| Attribute                 | Description                                                                 |
| :------------------------ | :-------------------------------------------------------------------------- |
| `lob_min`, `lob_max`      | Controls the minimum and maximum arc of the projectile.                     |
| `speed_min`, `speed_max`  | Defines the range of initial projectile speeds.                             |
| `friction`                | How much the projectile slows down over time.                               |
| `on_death_explode`        | If `1`, the projectile explodes upon death (e.g., hitting a wall).          |
| `on_collision_die`        | If `1`, the projectile is destroyed upon collision with any surface.        |
| `die_on_liquid_collision` | If `1`, the projectile is destroyed upon colliding with liquids.            |
| `lifetime`                | The base duration of the projectile in seconds.                             |
| `lifetime_randomness`     | Adds randomness to the projectile's lifetime.                               |
| `damage`                  | The base damage dealt by the projectile.                                    |
| `bounces_left`            | The number of times the projectile can bounce before being destroyed.       |
| `knockback_force`         | The force applied to entities when the projectile hits them.                |
| `physics_impulse_coeff`   | Coefficient for physics impulse applied on collision.                       |
| `muzzle_flash_file`       | Specifies the particle effect for the muzzle flash when shot.               |
| `shoot_light_flash_radius`| Radius of the light flash emitted when the projectile is shot.              |
| `shoot_light_flash_r/g/b` | RGB values for the shooting light flash color.                              |

### Explosion Configuration (`config_explosion`)

Defines the properties of the explosion that occurs when the projectile dies or is set to explode.

| Attribute                 | Description                                                                 |
| :------------------------ | :-------------------------------------------------------------------------- |
| `camera_shake`            | Intensity of camera shake upon explosion.                                   |
| `explosion_radius`        | The radius of the explosion's effect.                                       |
| `explosion_sprite`        | The particle effect used for the explosion visual.                          |
| `create_cell_material`    | Material created in the environment by the explosion.                       |
| `create_cell_probability` | Probability of creating the specified cell material.                        |
| `hole_enabled`            | If `1`, the explosion creates holes in the environment.                     |
| `ray_energy`              | Energy of the explosion's damaging rays.                                    |
| `damage`                  | Damage dealt by the explosion itself.                                       |
| `physics_explosion_power` | Minimum and maximum power of the physics-based explosion force.             |
| `stains_enabled`          | If `1`, the explosion leaves stains on surfaces.                            |
| `stains_radius`           | The radius of the stains left by the explosion.                             |

## Sprite Component

Defines the visual appearance of the projectile.

```xml
<SpriteComponent 
  _enabled="1" 
  alpha="1" 
  image_file="data/projectiles_gfx/laser_green.xml" 
  offset_x="2" 
  offset_y="2"
>
</SpriteComponent>
```

*   `image_file`: Specifies the graphical asset for the projectile.

## Light Component

Adds a light source to the projectile.

```xml
<LightComponent 
  _enabled="1" 
  radius="150" 
  r="30"
  g="90"
  b="30">
</LightComponent>
```

*   `radius`: The range of the light.
*   `r`, `g`, `b`: RGB color values for the light.

## Particle Emitter Component

Manages the emission of cosmetic particles, often used for trails.

```xml
<ParticleEmitterComponent 
  emitted_material_name="plasma_fading_green"
  is_trail="1"
  trail_gap="0.8"
  lifetime_min="0.1"
  lifetime_max="0.8"
  emission_interval_min_frames="1"
  emission_interval_max_frames="2"
  is_emitting="1" >
</ParticleEmitterComponent>
```

*   `emitted_material_name`: The material of the particles being emitted.
*   `is_trail`: If `1`, particles are emitted as a trail.
*   `trail_gap`: Spacing between trail particles.

## Variable Storage Component

Stores custom variables associated with the entity.

```xml
<VariableStorageComponent
  name="projectile_file"
  value_string="data/entities/projectiles/deck/bounce_laser.xml"
>
</VariableStorageComponent>
```

*   `name`: The name of the variable.
*   `value_string`: The string value of the variable, often used to reference the entity's own file.