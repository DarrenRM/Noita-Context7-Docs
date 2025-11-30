---
title: Spiral Shot Projectile
category: entities
---

# Spiral Shot Projectile

This document details the configuration of the "spiral_shot" projectile entity in Noita, designed for AI-assisted modding.

## Core Entity Configuration

The projectile is defined as an entity with the tag `projectile_player`.

```xml
<Entity
  name="$projectile_default" tags="projectile_player"
>
  <!-- ... other components ... -->
</Entity>
```

## Base Projectile Properties

Inherits fundamental projectile behavior from `base_projectile.xml`.

### Velocity Component

Key attributes influencing the projectile's movement:

| Attribute      | Value | Description                                    |
|----------------|-------|------------------------------------------------|
| `gravity_y`    | `0`   | No vertical gravity applied.                   |
| `air_friction` | `0`   | No air resistance.                             |
| `mass`         | `0.01`| Very low mass, contributing to its speed.      |

```xml
<Base file="data/entities/base_projectile.xml">
  <VelocityComponent
    gravity_y="0"
    air_friction="0"
    mass="0.01"
  >
  </VelocityComponent>
</Base>
```

## Projectile Component

Defines the specific behavior and characteristics of the spiral shot.

### Key Attributes:

| Attribute                 | Value   | Description                                                              |
|---------------------------|---------|--------------------------------------------------------------------------|
| `lob_min`, `lob_max`      | `0.8`, `1.0` | Controls the minimum and maximum "lob" or arc of the projectile.         |
| `speed_min`, `speed_max`  | `100`, `120` | Sets the range for the projectile's initial speed.                       |
| `collide_with_entities`   | `0`     | Projectile does not collide with other entities.                         |
| `die_on_low_velocity`     | `0`     | Projectile does not die when its velocity becomes too low.               |
| `on_death_explode`        | `0`     | Projectile does not explode upon death.                                  |
| `on_death_gfx_leave_sprite`| `0`     | No sprite is left behind when the projectile dies.                       |
| `on_lifetime_out_explode` | `0`     | Projectile does not explode when its lifetime expires.                   |
| `damage`                  | `0.2`   | The base damage dealt by the projectile.                                 |
| `on_collision_die`        | `0`     | Projectile does not die upon collision.                                  |
| `direction_random_rad`    | `0.0`   | No random deviation in projectile direction.                             |
| `lifetime`                | `100`   | The duration (in frames) the projectile exists before expiring.          |
| `damage_every_x_frames`   | `5`     | Damage is applied every 5 frames.                                        |
| `physics_impulse_coeff`   | `5000`  | Coefficient for physics impulse, affecting knockback or interaction.     |

### Visual Effects:

| Attribute                 | Value                                                | Description                                      |
|---------------------------|------------------------------------------------------|--------------------------------------------------|
| `muzzle_flash_file`       | `data/entities/particles/muzzle_flashes/muzzle_flash_magic_large.xml` | Specifies the particle effect for the muzzle flash. |
| `shoot_light_flash_r`, `g`, `b`, `radius` | `160`, `245`, `255`, `180` | Defines the color and radius of the shooting light flash. |

```xml
<ProjectileComponent
  _enabled="1"
  lob_min="0.8"
  lob_max="1.0"
  speed_min="100"
  speed_max="120"
  collide_with_entities="0"
  die_on_low_velocity="0"
  on_death_explode="0"
  on_death_gfx_leave_sprite="0"
  on_lifetime_out_explode="0"
  explosion_dont_damage_shooter="1"
  damage="0.2"
  on_collision_die="0"
  direction_random_rad="0.0"
  lifetime="100"
  muzzle_flash_file="data/entities/particles/muzzle_flashes/muzzle_flash_magic_large.xml"
  shoot_light_flash_r="160"
  shoot_light_flash_g="245"
  shoot_light_flash_b="255"
  shoot_light_flash_radius="180"
  damage_every_x_frames="5"
  physics_impulse_coeff="5000"
>
</ProjectileComponent>
```

## Light Component

Adds a light source to the projectile.

| Attribute | Value | Description                               |
|-----------|-------|-------------------------------------------|
| `radius`  | `150` | The radius of the light emitted.          |
| `r`, `g`, `b` | `150`, `35`, `120` | The RGB color of the light. |

```xml
<LightComponent
  _enabled="1"
  radius="150"
  r="150"
  g="35"
  b="120"
>
</LightComponent>
```

## Lua Components

These components enable custom scripting for the projectile's behavior.

### `spiral_shot_start.lua`

This script is executed once when the projectile is added.

| Attribute           | Value                                         | Description                                     |
|---------------------|-----------------------------------------------|-------------------------------------------------|
| `script_source_file`| `data/scripts/projectiles/spiral_shot_start.lua`| Path to the Lua script file.                    |
| `execute_on_added`  | `1`                                           | Ensures the script runs immediately upon creation. |
| `remove_after_executed` | `1`                                       | The script component is removed after execution. |

```xml
<LuaComponent
  remove_after_executed="1"
  script_source_file="data/scripts/projectiles/spiral_shot_start.lua"
  execute_on_added="1"
>
</LuaComponent>
```

### `spiral_shot.lua`

This script is executed repeatedly throughout the projectile's lifetime.

| Attribute           | Value                                    | Description                                     |
|---------------------|------------------------------------------|-------------------------------------------------|
| `script_source_file`| `data/scripts/projectiles/spiral_shot.lua` | Path to the Lua script file.                    |
| `execute_every_n_frame` | `1`                                    | The script runs every frame.                    |
| `remove_after_executed` | `0`                                    | The script component persists.                  |

```xml
<LuaComponent
  _enabled="1"
  remove_after_executed="0"
  script_source_file="data/scripts/projectiles/spiral_shot.lua"
  execute_every_n_frame="1"
>
</LuaComponent>
```

## Audio Components

Defines the sound effects associated with the projectile.

### `AudioComponent`

Plays a specific sound event when the projectile is active.

| Attribute   | Value                                | Description                               |
|-------------|--------------------------------------|-------------------------------------------|
| `file`      | `data/audio/Desktop/projectiles.bank`| The audio bank file.                      |
| `event_root`| `player_projectiles/spiral_shot`     | The root event name for the projectile.   |

```xml
<AudioComponent
  file="data/audio/Desktop/projectiles.bank"
  event_root="player_projectiles/spiral_shot"
>
</AudioComponent>
```

### `AudioLoopComponent`

Provides a looping sound effect for the projectile.

| Attribute   | Value                                | Description                               |
|-------------|--------------------------------------|-------------------------------------------|
| `file`      | `data/audio/Desktop/projectiles.bank`| The audio bank file.                      |
| `event_name`| `player_projectiles/spiral_shot/loop`| The name of the looping audio event.      |
| `auto_play` | `1`                                  | The loop starts automatically.            |

```xml
<AudioLoopComponent
  file="data/audio/Desktop/projectiles.bank"
  event_name="player_projectiles/spiral_shot/loop"
  auto_play="1"
>
</AudioLoopComponent>
```

## Variable Storage Component

Stores a variable related to the projectile's own file path.

| Attribute    | Value                                    | Description                               |
|--------------|------------------------------------------|-------------------------------------------|
| `name`       | `projectile_file`                        | The name of the variable.                 |
| `value_string`| `data/entities/projectiles/deck/spiral_shot.xml` | The string value, pointing to its own XML. |

```xml
<VariableStorageComponent
  name="projectile_file"
  value_string="data/entities/projectiles/deck/spiral_shot.xml"
>
</VariableStorageComponent>
```