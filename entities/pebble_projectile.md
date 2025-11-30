---
title: Pebble Projectile
category: entities
---

# Pebble Projectile

This document details the configuration of the "Pebble" projectile entity in Noita, focusing on attributes relevant for AI-assisted modding.

## Entity Definition

The core of the pebble projectile is defined by its `Entity` tag, inheriting from a base projectile.

```xml
<Entity name="$projectile_default">
	<Base file="data/entities/base_projectile.xml" />
</Entity>
```

## ProjectileComponent

This component governs the physical and behavioral aspects of the projectile.

### Key Attributes:

| Attribute             | Description                                                                 | Value Examples      |
| :-------------------- | :-------------------------------------------------------------------------- | :------------------ |
| `lob_min`, `lob_max`  | Minimum and maximum lobbing angle (in radians) for projectile trajectory.   | `1.0`, `3.0`        |
| `speed_min`, `speed_max` | Minimum and maximum initial speed of the projectile.                        | `240`, `280`        |
| `angular_velocity`    | The projectile's rotation speed.                                            | `0`                 |
| `friction`            | How much the projectile's speed is reduced over time due to air resistance. | `1`                 |
| `direction_random_rad`| Random deviation in projectile direction (in radians).                      | `0.02`              |
| `lifetime`            | Duration in frames before the projectile is destroyed.                      | `90`                |
| `damage`              | The amount of damage the projectile deals upon collision.                   | `0.0`               |
| `on_collision_die`    | If `1`, the projectile is destroyed upon collision.                         | `1`                 |

## SpriteComponent

Defines the visual representation of the pebble.

### Key Attributes:

| Attribute    | Description                                     | Value Example                           |
| :----------- | :---------------------------------------------- | :-------------------------------------- |
| `image_file` | Path to the sprite image file.                  | `data/enemies_gfx/pebble_physics.png`   |
| `offset_x`   | Horizontal offset for the sprite.               | `6`                                     |
| `offset_y`   | Vertical offset for the sprite.                 | `13`                                    |

## AudioComponent

Handles the sound effects associated with the projectile.

### Key Attributes:

| Attribute    | Description                                     | Value Example                     |
| :----------- | :---------------------------------------------- | :-------------------------------- |
| `file`       | Path to the audio bank file.                    | `data/audio/Desktop/projectiles.bank` |
| `event_root` | The root event name for projectile sounds.      | `projectiles/bullet_laucher`      |

## LuaComponent

Allows for custom scripting to modify projectile behavior.

### Key Attributes:

| Attribute           | Description                                                               | Value Example                               |
| :------------------ | :------------------------------------------------------------------------ | :------------------------------------------ |
| `script_source_file`| Path to the Lua script file to be executed.                               | `data/scripts/animals/pebble_spawn.lua`     |
| `execute_on_removed`| If `1`, the script executes when the entity is removed.                 | `1`                                         |
| `execute_every_n_frame` | How often the script should execute (in frames). `-1` means once. | `-1`                                        |