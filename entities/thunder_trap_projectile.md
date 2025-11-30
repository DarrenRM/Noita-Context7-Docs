---
title: Thunder Trap Projectile
category: entities
---

# Thunder Trap Projectile

This document details the configuration of the "Thunder Trap" projectile entity in Noita, primarily focusing on its behavior, visual effects, and associated scripts for AI-assisted modding.

## Entity Definition

The core of the Thunder Trap projectile is defined by its `Entity` tag.

```xml
<Entity
	name="$projectile_default"
	>
	<!-- ... other components ... -->
</Entity>
```

## Base Projectile Configuration

The projectile inherits fundamental properties from `base_projectile.xml`.

### Velocity Component

Controls the projectile's movement characteristics.

| Attribute       | Value | Description                                     |
| :-------------- | :---- | :---------------------------------------------- |
| `gravity_y`     | `0`   | No vertical gravity applied.                    |
| `air_friction`  | `1`   | No air friction, maintains velocity.            |
| `mass`          | `0.05`| Low mass, influencing interactions.             |

## Projectile Component

Defines specific behaviors and properties of the Thunder Trap projectile.

| Attribute               | Value | Description                                                                 |
| :---------------------- | :---- | :-------------------------------------------------------------------------- |
| `_enabled`              | `1`   | Component is active.                                                        |
| `lob_min`, `lob_max`    | `0.8`, `1.0` | Controls the lobbing behavior (arc of projectile).                          |
| `speed_min`, `speed_max`| `50`  | Projectile travels at a constant speed of 50 units.                         |
| `die_on_low_velocity`   | `0`   | Projectile does not die if its velocity drops too low.                      |
| `on_death_explode`      | `0`   | Projectile does not explode upon death.                                     |
| `on_death_gfx_leave_sprite` | `0` | No sprite is left behind when the projectile dies.                          |
| `on_lifetime_out_explode` | `0` | Projectile does not explode when its lifetime expires.                      |
| `damage`                | `0.0` | Deals no direct damage.                                                     |
| `on_collision_die`      | `0`   | Projectile does not die upon collision.                                     |
| `penetrate_entities`    | `1`   | Projectile can pass through multiple entities.                              |
| `lifetime`              | `80`  | The projectile exists for 80 frames before expiring.                        |
| `knockback_force`       | `0.0` | Applies no knockback force.                                                 |

## Light Component

Adds a light source to the projectile, contributing to its visual effect.

| Attribute | Value | Description                                     |
| :-------- | :---- | :---------------------------------------------- |
| `_enabled`| `1`   | Component is active.                            |
| `radius`  | `150` | The radius of the light emitted.                |
| `r`, `g`, `b` | `45`, `45`, `90` | Defines the blue-ish color of the light. |

## Audio Loop Component

Plays a looping sound effect associated with the projectile.

| Attribute   | Value                               | Description                                     |
| :---------- | :---------------------------------- | :---------------------------------------------- |
| `file`      | `data/audio/Desktop/projectiles.bank` | The audio bank containing the sound event.      |
| `event_name`| `projectiles/electric/loop`         | The specific sound event to play.               |
| `auto_play` | `1`                                 | The sound starts automatically when spawned.    |

## Variable Storage Component

Stores custom variables for the projectile.

| Attribute    | Value                                | Description                                     |
| :----------- | :----------------------------------- | :---------------------------------------------- |
| `name`       | `projectile_file`                    | The name of the variable.                       |
| `value_string`| `data/entities/projectiles/thunder_trap.xml` | Stores the path to this projectile's XML file. |

## Sprite Particle Emitter Component

Generates visual particle effects for the projectile.

| Attribute              | Value     | Description                                                                 |
| :--------------------- | :-------- | :-------------------------------------------------------------------------- |
| `sprite_file`          | `data/particles/spark_electric.xml` | The particle effect to emit.                                |
| `delay`                | `0`       | No delay before emission starts.                                            |
| `lifetime`             | `0`       | Particles have no inherent lifetime set by the emitter.                     |
| `color.r`, `g`, `b`, `a` | `1`, `1`, `1`, `1` | Initial color of the particles (white).                                     |
| `color_change.r`, `g`, `b`, `a` | `0`, `0`, `0`, `0` | No color change over particle lifetime.                                     |
| `velocity.x`, `y`      | `0`, `0`  | Initial velocity of particles.                                              |
| `gravity.x`, `y`       | `0`, `10` | Particles are affected by gravity.                                          |
| `velocity_slowdown`    | `0`       | Particles do not slow down.                                                 |
| `rotation`             | `0`       | Initial rotation of particles.                                              |
| `angular_velocity`     | `0`       | No angular velocity for particles.                                          |
| `use_velocity_as_rotation` | `0` | Particle rotation is not determined by velocity.                            |
| `scale.x`, `y`         | `1`, `1`  | Initial scale of particles.                                                 |
| `scale_velocity.x`, `y`| `0`, `0`  | No change in particle scale over time.                                      |
| `emission_interval_min_frames`, `max_frames` | `1`, `2` | Particles are emitted every 1-2 frames.                                     |
| `count_min`, `max`     | `1`, `3`  | Emits 1 to 3 particles per emission.                                        |
| `randomize_rotation.min`, `max` | `-3.1415`, `3.1415` | Randomizes particle rotation within a full circle.                          |
| `randomize_position.min_x`, `max_x` | `-14`, `14` | Randomizes particle emission position horizontally.                         |
| `randomize_position.min_y`, `max_y` | `-14`, `14` | Randomizes particle emission position vertically.                           |

## Lua Component

Attaches a Lua script to the projectile for custom logic.

| Attribute           | Value                                | Description                                                                 |
| :------------------ | :----------------------------------- | :-------------------------------------------------------------------------- |
| `script_source_file`| `data/scripts/projectiles/thunder_trap.lua` | The path to the Lua script file that controls the projectile's behavior. |
| `execute_every_n_frame` | `-1` | Script logic is not executed on a fixed frame interval.                     |
| `execute_on_removed`| `1`  | The script will execute its logic when the projectile is removed.           |