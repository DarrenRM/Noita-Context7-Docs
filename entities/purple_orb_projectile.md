---
title: Purple Orb Projectile
category: entities
---

# Purple Orb Projectile

This document details the configuration of the "Purple Orb" projectile entity in Noita, useful for AI-assisted modding.

## Entity Definition

The core of the projectile is defined by the `<Entity>` tag.

```xml
<Entity 
  name="$projectile_default" 
   >
  <!-- ... other components ... -->
</Entity>
```

## Base Projectile Configuration

Inherits fundamental projectile properties from `base_projectile.xml`.

### Velocity Component

Controls the projectile's movement characteristics.

| Attribute      | Value | Description                                     |
|----------------|-------|-------------------------------------------------|
| `gravity_y`    | `0`   | No vertical gravity applied.                    |
| `air_friction` | `0`   | No air resistance.                              |
| `mass`         | `0.05`| Low mass, contributing to its speed.            |

## Projectile Component

Defines the specific behaviors and effects of the purple orb.

### Key Attributes

| Attribute                   | Value   | Description                                                                 |
|-----------------------------|---------|-----------------------------------------------------------------------------|
| `_enabled`                  | `1`     | Enables this component.                                                     |
| `lob_min`, `lob_max`        | `0.8`, `1.0` | Controls the minimum and maximum lobbing angle (arc) of the projectile.     |
| `speed_min`, `speed_max`    | `100`, `120`| Sets the range for the projectile's initial speed.                          |
| `die_on_low_velocity`       | `0`     | Projectile does not die if its velocity drops too low.                      |
| `on_death_explode`          | `1`     | The projectile explodes upon death.                                         |
| `on_lifetime_out_explode`   | `1`     | The projectile explodes when its lifetime expires.                          |
| `explosion_dont_damage_shooter` | `1` | The explosion does not harm the entity that fired it.                       |
| `damage`                    | `1.2`   | Base damage dealt by the projectile.                                        |
| `go_through_this_material`  | `meat_slime`| The projectile can pass through "meat_slime" material without dying.        |
| `on_collision_die`          | `1`     | The projectile dies upon colliding with most surfaces.                      |
| `lifetime`                  | `25`    | The duration in seconds before the projectile expires (and explodes).       |
| `knockback_force`           | `1.0`   | The force applied to entities when hit by the projectile.                   |

### Explosion Configuration (`config_explosion`)

Details the effects of the projectile's explosion.

| Attribute                 | Value   | Description                                                                 |
|---------------------------|---------|-----------------------------------------------------------------------------|
| `never_cache`             | `1`     | Prevents caching of this explosion for performance.                         |
| `camera_shake`            | `0`     | No camera shake effect from the explosion.                                  |
| `explosion_radius`        | `6`     | The radius of the explosion's effect.                                       |
| `explosion_sprite`        | `data/particles/explosion_016_plasma_pink.xml` | The visual sprite used for the explosion. |
| `ray_energy`              | `5000`  | Energy value for any associated ray effects.                                |
| `hole_destroy_liquid`     | `1`     | The explosion can destroy liquids.                                          |
| `hole_enabled`            | `1`     | The explosion creates holes in surfaces.                                    |
| `hole_image`              | `data/temp/explosion_hole.png` | The image used for the explosion hole.      |
| `explosion_sprite_emissive`| `1`    | The explosion sprite emits light.                                           |
| `explosion_sprite_additive`| `1`    | The explosion sprite uses additive blending.                                |
| `physics_explosion_power.min`, `.max` | `0.13`, `0.23` | The minimum and maximum power of the physics-based explosion force. |
| `shake_vegetation`        | `1`     | The explosion can shake vegetation.                                         |
| `light_r`, `light_g`, `light_b` | `40`, `15`, `80` | RGB values for the light emitted by the explosion.                      |

## Sprite Component

Defines the visual appearance of the projectile.

| Attribute       | Value                               | Description                                     |
|-----------------|-------------------------------------|-------------------------------------------------|
| `_enabled`      | `1`                                 | Enables this component.                         |
| `image_file`    | `data/projectiles_gfx/orb_dark.xml` | The sprite asset used for the projectile.       |
| `offset_x`, `offset_y` | `6`, `6`                            | Offset of the sprite from the entity's center.  |
| `rect_animation`| `spawn`                             | Specifies the animation to play on spawn.       |
| `emissive`      | `1`                                 | The sprite emits light.                         |
| `additive`      | `1`                                 | The sprite uses additive blending.              |

## Light Component

Adds a light source to the projectile.

| Attribute | Value | Description                               |
|-----------|-------|-------------------------------------------|
| `_enabled`| `1`   | Enables this component.                   |
| `radius`  | `150` | The radius of the light.                  |
| `r`, `g`, `b` | `90`, `15`, `150` | RGB values for the light color. |

## Audio Component

Specifies the sound effects associated with the projectile.

| Attribute   | Value                               | Description                                     |
|-------------|-------------------------------------|-------------------------------------------------|
| `file`      | `data/audio/Desktop/projectiles.bank` | The audio bank containing the sound events.     |
| `event_root`| `projectiles/magic`                 | The root event path for projectile sounds.      |

## Variable Storage Component

Stores custom variables for the entity.

| Attribute    | Value                                | Description                                     |
|--------------|--------------------------------------|-------------------------------------------------|
| `name`       | `projectile_file`                    | The name of the variable.                       |
| `value_string`| `data/entities/projectiles/orb_purple.xml` | The string value, referencing its own file. |