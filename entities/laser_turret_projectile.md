---
title: Laser Turret Projectile
category: entities
---

# Laser Turret Projectile

This document details the configuration for the laser turret projectile entity in Noita, focusing on key attributes relevant for AI-assisted modding.

## Entity Definition

The core entity is defined as a projectile, inheriting base properties from `base_projectile.xml`.

```xml
<Entity name="$projectile_default">
	<Base file="data/entities/base_projectile.xml" />
	<!-- ... other components ... -->
</Entity>
```

## ProjectileComponent

This component governs the projectile's behavior, including its trajectory, damage, and effects upon death or collision.

### Key Attributes:

| Attribute               | Description                                                                 | Example Value |
| :---------------------- | :-------------------------------------------------------------------------- | :------------ |
| `speed_min`             | Minimum projectile speed.                                                   | `1450`        |
| `speed_max`             | Maximum projectile speed.                                                   | `1850`        |
| `lifetime`              | Duration the projectile exists before expiring.                             | `20`          |
| `damage`                | Base damage dealt by the projectile.                                        | `1`           |
| `on_death_explode`      | Whether the projectile explodes upon death (e.g., lifetime out).            | `1`           |
| `on_collision_die`      | Whether the projectile dies upon colliding with something.                  | `1`           |
| `die_on_liquid_collision` | Whether the projectile dies upon colliding with liquids.                    | `1`           |
| `friendly_fire`         | Whether the projectile can damage the shooter.                              | `1`           |
| `knockback_force`       | The force applied to entities upon impact.                                  | `3.0`         |
| `camera_shake_when_shot`| The intensity of camera shake when this projectile is fired.                | `2.0`         |
| `muzzle_flash_file`     | Path to the particle effect file for the muzzle flash.                      | `data/entities/particles/muzzle_flashes/muzzle_flash_laser.xml` |

### `config_explosion` Sub-element:

This nested element defines the properties of the explosion that occurs when the projectile dies and `on_death_explode` is enabled.

| Attribute                 | Description                                                                 | Example Value |
| :------------------------ | :-------------------------------------------------------------------------- | :------------ |
| `camera_shake`            | Intensity of camera shake during the explosion.                             | `4.5`         |
| `explosion_radius`        | The radius of the explosion effect.                                         | `3`           |
| `explosion_sprite`        | Path to the sprite file used for the explosion visual.                      | `data/particles/explosion_016_plasma.xml` |
| `create_cell_material`    | The material created by the explosion (e.g., for terrain destruction).      | `plasma_fading` |
| `create_cell_probability` | Probability of creating a cell material.                                    | `15`          |
| `ray_energy`              | Energy value for raycasting effects of the explosion.                       | `10000`       |
| `damage`                  | Damage dealt by the explosion itself.                                       | `0.25`        |
| `hole_enabled`            | Whether the explosion creates holes in terrain.                             | `1`           |
| `hole_image`              | Path to the image used for explosion holes.                                 | `data/temp/explosion_hole.png` |
| `damage_mortals`          | Whether the explosion damages living entities.                              | `1`           |
| `physics_throw_enabled`   | Whether the explosion applies physics forces to nearby objects.             | `1`           |
| `stains_enabled`          | Whether the explosion leaves stains on surfaces.                            | `1`           |
| `stains_radius`           | The radius of the stains left by the explosion.                             | `4`           |

## SpriteComponent

Defines the visual representation of the projectile.

### Key Attributes:

| Attribute     | Description                               | Example Value |
| :------------ | :---------------------------------------- | :------------ |
| `image_file`  | Path to the sprite's image file.          | `data/projectiles_gfx/laser.xml` |
| `emissive`    | Whether the sprite emits light.           | `1`           |
| `additive`    | Whether the sprite uses additive blending.| `1`           |
| `offset_x`    | Horizontal offset of the sprite.          | `2`           |
| `offset_y`    | Vertical offset of the sprite.            | `2`           |

## LightComponent

Adds a light source to the projectile.

### Key Attributes:

| Attribute | Description             | Example Value |
| :-------- | :---------------------- | :------------ |
| `radius`  | The radius of the light.| `150`         |
| `r`       | Red component of light. | `30`          |
| `g`       | Green component of light.| `30`          |
| `b`       | Blue component of light. | `60`          |

## ParticleEmitterComponent

Responsible for emitting particles, likely for visual effects like trails or sparks.

### Key Attributes:

| Attribute                 | Description                                     | Example Value |
| :------------------------ | :---------------------------------------------- | :------------ |
| `emitted_material_name`   | The material of the particles being emitted.    | `plasma_fading` |
| `count_min`               | Minimum number of particles emitted per burst.  | `5`           |
| `count_max`               | Maximum number of particles emitted per burst.  | `5`           |
| `lifetime_min`            | Minimum lifetime of emitted particles.          | `0.1`         |
| `lifetime_max`            | Maximum lifetime of emitted particles.          | `0.3`         |
| `emit_cosmetic_particles` | Whether to emit cosmetic particles.             | `1`           |
| `emission_interval_min_frames` | Minimum frames between particle emissions.    | `1`           |
| `emission_interval_max_frames` | Maximum frames between particle emissions.    | `2`           |
| `is_emitting`             | Whether the emitter is currently active.        | `1`           |

## AudioComponent

Defines the sound effects associated with the projectile.

### Key Attributes:

| Attribute   | Description                               | Example Value                               |
| :---------- | :---------------------------------------- | :------------------------------------------ |
| `file`      | Path to the audio bank file.              | `data/audio/Desktop/projectiles.bank`       |
| `event_root`| The root event name for projectile sounds.| `projectiles/laser_turret`                  |

## VariableStorageComponent

Stores custom variables for the entity.

### Key Attributes:

| Attribute    | Description                                 | Example Value                           |
| :----------- | :------------------------------------------ | :-------------------------------------- |
| `name`       | The name of the variable.                   | `projectile_file`                       |
| `value_string` | The string value of the variable.           | `data/entities/projectiles/laser_turret.xml` |