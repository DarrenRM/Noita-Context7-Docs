---
title: Expanding Orb Projectile
category: entities
---

# Expanding Orb Projectile

This document details the configuration for the "Expanding Orb" projectile entity in Noita, primarily focusing on its behavior, visual effects, and damage.

## Core Projectile Properties

The `ProjectileComponent` defines the fundamental behavior of the orb.

### Key Attributes:

| Attribute              | Value      | Description                                                                 |
| :--------------------- | :--------- | :-------------------------------------------------------------------------- |
| `lob_min`, `lob_max`   | `0.8`, `1.0` | Controls the arc of the projectile. Higher values mean a flatter trajectory. |
| `speed_min`, `speed_max` | `45`, `55` | The initial speed range of the projectile.                                  |
| `direction_random_rad` | `0.15`     | Adds a slight random deviation to the projectile's initial direction.       |
| `die_on_liquid_collision` | `0`        | The projectile does not disappear upon hitting liquids.                     |
| `on_death_explode`     | `1`        | The projectile explodes when its lifetime ends or it's destroyed.           |
| `on_lifetime_out_explode` | `1`        | Explicitly states it explodes when its lifetime expires.                    |
| `friendly_fire`        | `1`        | The projectile can damage the player and allies.                            |
| `collide_with_entities`| `0`        | The projectile does not collide with other entities (except on death).      |
| `damage`               | `3.0`      | The base damage dealt by the projectile.                                    |
| `lifetime`             | `180`      | The duration in frames before the projectile explodes.                      |
| `knockback_force`      | `1.5`      | The force applied to entities when hit by the projectile.                   |

## Explosion Configuration

The `config_explosion` section within `ProjectileComponent` defines the effects when the orb explodes.

### Key Attributes:

| Attribute                 | Value      | Description                                                                 |
| :------------------------ | :--------- | :-------------------------------------------------------------------------- |
| `explosion_radius`        | `4`        | The radius of the explosion's damaging area.                                |
| `explosion_sprite`        | `...`      | The visual sprite used for the explosion effect.                            |
| `hole_destroy_liquid`     | `1`        | The explosion can destroy liquids.                                          |
| `hole_enabled`            | `1`        | The explosion creates holes in terrain.                                     |
| `ray_energy`              | `300000`   | The energy of the destructive rays emitted by the explosion.                |
| `damage_mortals`          | `1`        | The explosion deals damage to living entities.                              |
| `physics_explosion_power` | `0.1` - `0.3` | The force of the physics-based explosion effect.                            |
| `shake_vegetation`        | `1`        | The explosion causes nearby vegetation to shake.                            |
| `light_enabled`           | `1`        | The explosion emits light.                                                  |
| `light_radius_coeff`      | `64`       | The intensity/radius multiplier for the explosion light.                    |

## Visual Components

### Main Sprite:

*   `image_file`: `data/projectiles_gfx/orb_expanding.xml` - The primary visual representation of the orb.

### Glow Sprite:

*   `image_file`: `data/projectiles_gfx/orb_expanding_glow.xml`
*   `additive="1"`, `emissive="1"`: Indicates this sprite uses additive blending for a glowing effect.

### Launch Flash:

*   `image_file`: `data/particles/explosion_016.xml`
*   `z_index="-1.1"`: Ensures this flash appears behind the main orb sprite.

## Particle Emitters

The orb utilizes several `ParticleEmitterComponent`s to create visual effects.

### Circles (Modified by `orb_expanding.lua`):

*   `emitted_material_name`: `spark`
*   `count_min`/`max`: `7`/`15`
*   `lifetime_min`/`max`: `1.0`/`5.0`
*   `emission_interval_min`/`max_frames`: `14`/`14`
*   `emit_cosmetic_particles`: `1` (These are visual effects, not physical particles).

### Trajectory:

*   `emitted_material_name`: `spark`
*   `count_min`/`max`: `1`/`1`
*   `lifetime_min`/`max`: `1.0`/`5.0`
*   `emission_interval_min`/`max_frames`: `4`/`4`

### Ring: Launch:

*   `emitted_material_name`: `spark_red`
*   `area_circle_radius.min`/`max`: `4`/`4`
*   `velocity_always_away_from_center`: `30`
*   `count_min`/`max`: `10`/`10`
*   `emitter_lifetime_frames`: `2` (Short-lived emitter).

### Ring: Ready:

*   `emitted_material_name`: `spark_yellow`
*   `delay_frames`: `115` (Starts emitting after a delay).
*   `area_circle_radius.min`/`max`: `9`/`9`
*   `velocity_always_away_from_center`: `60`
*   `count_min`/`max`: `50`/`50`
*   `emission_interval_min`/`max_frames`: `100`/`100`
*   `emitter_lifetime_frames`: `2`

## Lighting

*   `LightComponent`:
    *   `radius`: `30`
    *   `r`, `g`, `b`: `255`, `255`, `2` (A bright yellow-white light).

## Audio

*   `AudioComponent`:
    *   `file`: `data/audio/Desktop/projectiles.bank`
    *   `event_root`: `projectiles/orb_cursed` (Links to specific sound events).

## Scripting

*   `LuaComponent`:
    *   `script_source_file`: `data/scripts/projectiles/orb_expanding.lua`
    *   `execute_on_added`: `data/scripts/projectiles/orb_expanding.lua` (The script is executed when the entity is added).
    *   `execute_every_n_frame`: `1`
    *   `execute_times`: `116` (The script runs for a specific duration, likely tied to the orb's behavior before explosion).

## Variable Storage

*   `VariableStorageComponent` (for `base_damage`): Stores the base damage value, allowing for easier modification.
*   `VariableStorageComponent` (for `projectile_file`): Stores the path to this entity's XML file, useful for referencing.