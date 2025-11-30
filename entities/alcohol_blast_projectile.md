---
title: Alcohol Blast Projectile
category: entities
---

# Alcohol Blast Projectile

This document details the configuration for the "Alcohol Blast" projectile in Noita, designed for AI-assisted modding.

## Core Entity Configuration

The projectile is based on the default player projectile entity.

```xml
<Entity 
  name="$projectile_default" tags="projectile_player"
   >
```

## Base Projectile Settings

Inherits fundamental projectile behavior from `base_projectile.xml`.

```xml
	<Base file="data/entities/base_projectile.xml" >
		<VelocityComponent>
    	</VelocityComponent> 
	</Base>
```

## Projectile Component - Key Attributes

This component defines the specific behavior and effects of the Alcohol Blast projectile.

| Attribute                 | Value                               | Description                                                                 |
| :------------------------ | :---------------------------------- | :-------------------------------------------------------------------------- |
| `_enabled`                | `1`                                 | Enables the projectile component.                                           |
| `lob_min`, `lob_max`      | `0.8`, `1.0`                        | Controls the lobbing behavior (arc) of the projectile.                      |
| `speed_min`, `speed_max`  | `0`, `0`                            | Projectile starts with no initial speed.                                    |
| `die_on_low_velocity`     | `1`                                 | The projectile will be destroyed if its velocity drops too low.             |
| `on_death_explode`        | `1`                                 | The projectile explodes upon death.                                         |
| `on_lifetime_out_explode` | `1`                                 | The projectile explodes when its lifetime expires.                          |
| `damage`                  | `0`                                 | Base damage of the projectile itself (before explosion).                    |
| `on_collision_die`        | `1`                                 | The projectile is destroyed upon collision.                                 |
| `lifetime`                | `0`                                 | Projectile has no inherent lifetime; death is triggered by other conditions. |
| `shoot_light_flash_r`     | `255`                               | Red component of the light flash when shot.                                 |
| `shoot_light_flash_g`     | `140`                               | Green component of the light flash when shot.                               |
| `shoot_light_flash_b`     | `255`                               | Blue component of the light flash when shot.                                |
| `shoot_light_flash_radius`| `140`                               | Radius of the light flash when shot.                                        |

### Explosion Configuration (`config_explosion`)

Defines the parameters of the explosion that occurs upon the projectile's death.

| Attribute                   | Value     | Description                                                                                             |
| :-------------------------- | :-------- | :------------------------------------------------------------------------------------------------------ |
| `never_cache`               | `1`       | Prevents caching of this explosion for performance.                                                     |
| `camera_shake`              | `4.0`     | Intensity of camera shake caused by the explosion.                                                      |
| `explosion_radius`          | `12`      | The radius of the explosion effect.                                                                     |
| `explosion_sprite`          | `...xml`  | Path to the sprite used for the explosion visual.                                                       |
| `ray_energy`                | `400000`  | Energy value for raycasting effects related to the explosion.                                           |
| `create_cell_probability`   | `70`      | Percentage chance to create new cells (liquid/material) upon explosion.                                 |
| `create_cell_material`      | `alcohol` | The material of the cells to be created.                                                                |
| `damage`                    | `0.3`     | Damage dealt by the explosion.                                                                          |
| `hole_enabled`              | `1`       | Enables the creation of holes in terrain by the explosion.                                              |
| `hole_image`                | `...png`  | Path to the image used for the explosion hole.                                                          |
| `particle_effect`           | `1`       | Enables particle effects associated with the explosion.                                                 |
| `damage_mortals`            | `1`       | The explosion deals damage to living entities.                                                          |
| `physics_explosion_power`   | `0.4-0.6` | Minimum and maximum power of the physics-based force applied by the explosion.                          |
| `physics_throw_enabled`     | `1`       | Enables physics-based throwing of objects by the explosion.                                             |
| `spark_material`            | `alcohol` | The material of the sparks generated by the explosion.                                                  |
| `material_sparks_enabled`   | `1`       | Enables the generation of material-specific sparks.                                                     |
| `material_sparks_count_max` | `50`      | Maximum number of material sparks to generate.                                                          |
| `material_sparks_count_min` | `40`      | Minimum number of material sparks to generate.                                                          |
| `light_fade_time`           | `0.8`     | Time in seconds for the explosion's light effect to fade out.                                           |
| `stains_enabled`            | `1`       | Enables the creation of stains on surfaces from the explosion.                                          |
| `stains_image`              | `...png`  | Path to the image used for the explosion stains.                                                        |
| `audio_event_name`          | `explosions/liquid` | The name of the audio event to play upon explosion.                                                     |

## Variable Storage Component

Stores a reference to the projectile's own XML file.

```xml
	<VariableStorageComponent
		name="projectile_file"
		value_string="data/entities/projectiles/deck/alcohol_blast.xml"
		>
	</VariableStorageComponent>
```