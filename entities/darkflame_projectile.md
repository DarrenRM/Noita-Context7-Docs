---
title: Darkflame Projectile
category: entities
---

# Darkflame Projectile

This document details the configuration of the Darkflame projectile entity in Noita, focusing on attributes relevant for AI-assisted modding.

## Entity Definition

The core of the Darkflame projectile is defined by its `Entity` tag.

```xml
<Entity 
  name="$projectile_default" 
   >
  <!-- ... other components ... -->
</Entity>
```

## Base Projectile Configuration

The projectile inherits fundamental properties from `base_projectile.xml`.

### VelocityComponent

Key attributes controlling the projectile's movement:

| Attribute      | Value | Description                                    |
| -------------- | ----- | ---------------------------------------------- |
| `gravity_y`    | `0`   | No vertical gravity applied.                   |
| `air_friction` | `0`   | No air resistance.                             |
| `mass`         | `0.03`| Small mass, influencing interactions.          |

## ProjectileComponent

This component defines the specific behaviors and effects of the Darkflame projectile.

### Key Attributes:

| Attribute                   | Value | Description                                                                 |
| --------------------------- | ----- | --------------------------------------------------------------------------- |
| `speed_min`                 | `250` | Minimum projectile speed.                                                   |
| `speed_max`                 | `250` | Maximum projectile speed.                                                   |
| `die_on_low_velocity`       | `0`   | Projectile does not die if its velocity drops too low.                      |
| `on_death_explode`          | `1`   | The projectile explodes upon death.                                         |
| `on_lifetime_out_explode`   | `1`   | The projectile explodes when its lifetime expires.                          |
| `explosion_dont_damage_shooter` | `1` | The explosion does not harm the entity that shot the projectile.            |
| `damage`                    | `0.8` | Base damage dealt by the projectile.                                        |
| `on_collision_die`          | `1`   | The projectile dies upon colliding with something.                          |
| `collide_with_entities`     | `0`   | The projectile does not collide with other entities.                        |
| `lifetime`                  | `100` | Duration in frames before the projectile expires (and potentially explodes). |
| `shoot_light_flash_r`       | `190` | Red component of the light flash when shot.                                 |
| `shoot_light_flash_g`       | `40`  | Green component of the light flash when shot.                               |
| `shoot_light_flash_b`       | `245` | Blue component of the light flash when shot.                                |
| `shoot_light_flash_radius`  | `140` | Radius of the light flash when shot.                                        |

### `config_explosion` Sub-element:

Defines the parameters of the explosion effect.

| Attribute                 | Value | Description                                                                 |
| ------------------------- | ----- | --------------------------------------------------------------------------- |
| `never_cache`             | `1`   | Ensures the explosion effect is not cached, allowing for dynamic creation.  |
| `damage`                  | `0`   | The explosion itself deals no direct damage.                                |
| `explosion_radius`        | `1`   | Small radius for the explosion effect.                                      |
| `explosion_sprite`        | `data/particles/darkflame.xml` | Specifies the particle effect used for the explosion.                 |
| `ray_energy`              | `0`   | No energy is transferred via rays from the explosion.                       |
| `hole_enabled`            | `0`   | No holes are created by the explosion.                                      |
| `physics_explosion_power` | `0`   | No physics-based force is applied by the explosion.                         |
| `shake_vegetation`        | `1`   | The explosion causes vegetation to shake.                                   |
| `light_enabled`           | `1`   | A light source is created by the explosion.                                 |
| `light_r`, `light_g`, `light_b` | `80`, `5`, `120` | RGB values for the explosion's light.                                     |
| `light_radius_coeff`      | `64`  | Coefficient determining the light radius.                                   |

## SpriteComponent

Defines the visual representation of the projectile.

| Attribute      | Value                         | Description                                     |
| -------------- | ----------------------------- | ----------------------------------------------- |
| `image_file`   | `data/projectiles_gfx/darkflame.xml` | Path to the sprite's graphical definition.      |
| `offset_x`     | `6`                           | Horizontal offset of the sprite.                |
| `offset_y`     | `6`                           | Vertical offset of the sprite.                  |
| `rect_animation` | `spawn`                       | Specifies the animation state to use initially. |

## LuaComponent

Links the projectile to a Lua script for custom behavior.

| Attribute           | Value                               | Description                                     |
| ------------------- | ----------------------------------- | ----------------------------------------------- |
| `script_source_file`| `data/scripts/projectiles/darkflame.lua` | Path to the associated Lua script file.         |
| `execute_every_n_frame` | `1`                                 | The script logic runs every frame.              |

## LightComponent

Defines a persistent light source emitted by the projectile.

| Attribute      | Value | Description                               |
| -------------- | ----- | ----------------------------------------- |
| `radius`       | `64`  | The radius of the light.                  |
| `r`, `g`, `b`  | `80`, `5`, `120` | RGB values for the light color.           |
| `fade_out_time`| `0.5` | Time in seconds for the light to fade out.|

## AudioComponent

Specifies the audio bank and event root for projectile sounds.

| Attribute   | Value                        | Description                               |
| ----------- | ---------------------------- | ----------------------------------------- |
| `file`      | `data/audio/Desktop/projectiles.bank` | Path to the audio bank file.              |
| `event_root`| `projectiles/rocket`         | The root event name for projectile sounds.|

## VariableStorageComponent

Stores custom variables associated with the entity.

| Attribute    | Value                               | Description                                     |
| ------------ | ----------------------------------- | ----------------------------------------------- |
| `name`       | `projectile_file`                   | The name of the variable.                       |
| `value_string`| `data/entities/projectiles/darkflame.xml` | The string value, likely referencing its own file.|