---
title: Ocarina Projectile (D Note)
category: entities
---

# Ocarina Projectile (D Note)

This document describes the "Ocarina D" projectile entity in Noita, focusing on its key attributes for AI-assisted modding.

## Core Entity

The projectile is defined as an `Entity` with the tag `projectile_player`, indicating it's a player-fired projectile.

```xml
<Entity name="$projectile_default" tags="projectile_player" >
    <!-- ... other components ... -->
</Entity>
```

## Base Projectile Properties

Inherits from `data/entities/base_projectile.xml`.

### Velocity Component

Controls the projectile's movement physics.

| Attribute        | Value   | Description                                     |
| :--------------- | :------ | :---------------------------------------------- |
| `gravity_y`      | `0`     | No vertical gravity applied.                    |
| `air_friction`   | `8`     | Moderate air resistance.                        |
| `mass`           | `0.01`  | Very light mass.                                |

## Projectile Component

Defines the specific behavior and characteristics of this projectile.

| Attribute                 | Value   | Description                                                                 |
| :------------------------ | :------ | :-------------------------------------------------------------------------- |
| `_enabled`                | `1`     | Component is active.                                                        |
| `lob_min`, `lob_max`      | `0.5`, `0.7` | Controls the arc of the projectile.                                         |
| `speed_min`, `speed_max`  | `250`, `450` | Sets the range for projectile speed.                                        |
| `direction_random_rad`    | `0.00`  | No initial random deviation in direction.                                   |
| `on_death_explode`        | `0`     | Does not explode upon death.                                                |
| `on_death_gfx_leave_sprite` | `0`     | Does not leave a sprite upon death.                                         |
| `on_lifetime_out_explode` | `0`     | Does not explode when lifetime expires.                                     |
| `on_collision_die`        | `0`     | Does not die upon collision.                                                |
| `lifetime`                | `2`     | Projectile exists for 2 seconds.                                            |
| `damage`                  | `0`     | Deals no direct damage.                                                     |
| `lifetime_randomness`     | `0`     | Lifetime is fixed.                                                          |
| `knockback_force`         | `0`     | Does not apply knockback.                                                   |
| `physics_impulse_coeff`   | `0`     | Does not impart physics impulse.                                            |

## Particle Emitters

### `ParticleEmitterComponent` (Spark Trail)

Generates white sparks as a visual trail.

| Attribute               | Value      | Description                                                                 |
| :---------------------- | :--------- | :-------------------------------------------------------------------------- |
| `emitted_material_name` | `spark_white` | The material used for the emitted particles.                                |
| `x_vel_max`, `y_vel_max`| `80`, `10` | Controls the outward velocity of the sparks.                                |
| `count_min`, `count_max`| `8`, `10`  | Number of sparks emitted per interval.                                      |
| `lifetime_min`, `lifetime_max` | `0.2`, `1.2` | Duration each spark particle exists.                                        |
| `airflow_force`, `airflow_time`, `airflow_scale` | `1.5`, `1.101`, `0.05` | Influences how air currents affect the sparks.                              |
| `create_real_particles` | `0`        | These are cosmetic particles, not physical entities.                        |

### `SpriteParticleEmitterComponent` (Note Sprites)

Emits sprite-based particles resembling musical notes.

| Attribute                 | Value        | Description                                                                 |
| :------------------------ | :----------- | :-------------------------------------------------------------------------- |
| `sprite_file`             | `data/particles/note_$[1-4].xml` | Uses one of four note sprite variations.                                    |
| `lifetime`                | `1.5`        | Duration each note sprite exists.                                           |
| `color.r`, `color.g`, `color.b`, `color.a` | `1`, `1`, `0.8`, `1` | Initial color of the note sprites (yellowish-white).                        |
| `color_change.a`          | `-1`         | Alpha value decreases over lifetime, causing fading.                        |
| `emission_interval_min_frames`, `emission_interval_max_frames` | `4`, `6` | Controls the timing of note sprite emissions.                               |
| `count_min`, `count_max`  | `1`, `1`     | One note sprite emitted per interval.                                       |
| `randomize_rotation`      | `-0.3415` to `0.3415` | Randomizes the initial rotation of the note sprites.                        |
| `randomize_angular_velocity` | `-0.1415` to `0.1415` | Randomizes the rotation speed of the note sprites.                          |
| `randomize_velocity`      | `-5` to `5` (x/y) | Small random velocity applied to note sprites.                              |
| `entity_velocity_multiplier` | `0.1`        | Note sprites inherit a small portion of the projectile's velocity.          |

## Variable Storage

### `VariableStorageComponent`

Stores a variable to identify the specific ocarina note.

| Attribute      | Value | Description                                     |
| :------------- | :---- | :---------------------------------------------- |
| `name`         | `ocarina_note` | The name of the variable.                   |
| `value_string` | `d`   | The value, indicating this is the 'D' note.     |

## Lua Component

### `LuaComponent`

Links to a Lua script for custom behavior.

| Attribute           | Value                           | Description                                                                 |
| :------------------ | :------------------------------ | :-------------------------------------------------------------------------- |
| `script_source_file`| `data/scripts/magic/ocarina.lua`| The Lua script responsible for the ocarina's magical effects.               |
| `execute_on_added`  | `1`                             | The script executes immediately when the projectile is added.               |
| `remove_after_executed` | `1`                             | The Lua component is removed after its script has run once.                 |

## Audio Component

### `AudioComponent`

Manages the sound effects for the projectile.

| Attribute        | Value                               | Description                                     |
| :--------------- | :---------------------------------- | :---------------------------------------------- |
| `file`           | `data/audio/Desktop/projectiles.bank` | The audio bank containing projectile sounds.    |
| `event_root`     | `player_projectiles/ocarina/d`      | The specific sound event for the 'D' ocarina note. |
| `set_latest_event_position` | `1`                             | The sound will be positioned at the projectile's location. |