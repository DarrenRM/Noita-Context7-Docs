---
title: Vacuum Liquid Projectile
category: entities
---

# Vacuum Liquid Projectile

This document details the configuration for the "Vacuum Liquid" projectile entity in Noita, focusing on its core mechanics and visual effects for AI-assisted modding.

## Core Components

The Vacuum Liquid projectile is designed to suck in nearby materials and has a short lifespan, dissipating after a set duration.

### GameAreaEffectComponent

This component defines the area of effect for the projectile.

| Attribute | Value | Description |
|---|---|---|
| `radius` | `64` | The radius in pixels around the projectile where its effects are applied. |

### ParticleEmitterComponent (x2)

These components are responsible for emitting cosmetic "spark" particles. They differ in their emission parameters and attractor forces, contributing to the visual dynamism of the projectile.

**Emitter 1:**

| Attribute | Value | Description |
|---|---|---|
| `emitted_material_name` | `spark` | The material of the particles to be emitted. |
| `gravity.y` | `0.0` | No vertical gravity applied to the emitted particles. |
| `lifetime_min` | `0.5` | Minimum lifetime of emitted particles in seconds. |
| `lifetime_max` | `1.5` | Maximum lifetime of emitted particles in seconds. |
| `count_min` | `2` | Minimum number of particles emitted per burst. |
| `count_max` | `4` | Maximum number of particles emitted per burst. |
| `airflow_force` | `1.7` | Force applied by airflow to the particles. |
| `attractor_force` | `4` | Force attracting particles towards a central point. |

**Emitter 2:**

| Attribute | Value | Description |
|---|---|---|
| `emitted_material_name` | `spark` | The material of the particles to be emitted. |
| `gravity.y` | `0.0` | No vertical gravity applied to the emitted particles. |
| `lifetime_min` | `0.5` | Minimum lifetime of emitted particles in seconds. |
| `lifetime_max` | `2.5` | Maximum lifetime of emitted particles in seconds. |
| `count_min` | `4` | Minimum number of particles emitted per burst. |
| `count_max` | `4` | Maximum number of particles emitted per burst. |
| `area_circle_radius.min` | `64` | Minimum radius of the emission area. |
| `area_circle_radius.max` | `64` | Maximum radius of the emission area. |
| `airflow_force` | `0.8` | Force applied by airflow to the particles. |
| `attractor_force` | `8` | Force attracting particles towards a central point. |

### Base File Inclusion

The projectile inherits base properties from `data/entities/projectiles/deck/base_field.xml`.

#### ProjectileComponent

Key properties related to the projectile's behavior.

| Attribute | Value | Description |
|---|---|---|
| `lifetime` | `300` | The duration in frames the projectile exists before expiring. |
| `config_explosion.explosion_sprite` | `data/particles/blast_out_polymorph.xml` | The visual effect used when the projectile explodes. |

#### AudioLoopComponent

Plays a looping sound effect associated with the projectile.

| Attribute | Value | Description |
|---|---|---|
| `file` | `data/audio/Desktop/projectiles.bank` | The audio bank containing the sound event. |
| `event_name` | `player_projectiles/field_transmutation/loop` | The specific sound event to play. |
| `auto_play` | `1` | Starts playing the sound automatically when the entity is created. |

### MaterialSuckerComponent

This component enables the projectile to absorb nearby materials.

| Attribute | Value | Description |
|---|---|---|
| `num_cells_sucked_per_frame` | `200` | The number of material cells the projectile attempts to suck in each frame. |
| `randomized_position.min_x` | `-64` | Minimum X offset for sucking materials. |
| `randomized_position.max_x` | `64` | Maximum X offset for sucking materials. |
| `randomized_position.min_y` | `-64` | Minimum Y offset for sucking materials. |
| `randomized_position.max_y` | `64` | Maximum Y offset for sucking materials. |
| `material_type` | `0` | Specifies which material types can be sucked (0 typically means all). |
| `barrel_size` | `10000` | A large value indicating a wide range for material suction. |

### MaterialInventoryComponent

Manages how materials are handled when the projectile is destroyed.

| Attribute | Value | Description |
|---|---|---|
| `drop_as_item` | `0` | The projectile does not drop its contents as an item upon death. |
| `on_death_spill` | `1` | The sucked materials are spilled onto the ground when the projectile dies. |

### DamageModelComponent

Defines the projectile's health and how it interacts with damage.

| Attribute | Value | Description |
|---|---|---|
| `hp` | `0.5` | The health points of the projectile. |
| `air_needed` | `0` | The projectile does not require air to function. |
| `wait_for_kill_flag_on_death` | `1` | The projectile waits for a specific kill flag to be set before dying. |

### HitboxComponent

Determines the collision area of the projectile.

| Attribute | Value | Description |
|---|---|---|
| `aabb_min_x` | `-2` | Minimum X coordinate of the Axis-Aligned Bounding Box. |
| `aabb_max_x` | `2` | Maximum X coordinate of the Axis-Aligned Bounding Box. |
| `aabb_min_y` | `-2` | Minimum Y coordinate of the Axis-Aligned Bounding Box. |
| `aabb_max_y` | `2` | Maximum Y coordinate of the Axis-Aligned Bounding Box. |

### LuaComponent (x2)

These components execute Lua scripts to control specific behaviors.

**Lua Component 1:**

| Attribute | Value | Description |
|---|---|---|
| `_tags` | `vacuum_powder_helper` | A tag associated with this script. |
| `script_source_file` | `data/scripts/projectiles/vacuum_powder.lua` | The path to the Lua script file. |
| `execute_every_n_frame` | `280` | The script executes every 280 frames. |

**Lua Component 2:**

| Attribute | Value | Description |
|---|---|---|
| `script_source_file` | `data/scripts/projectiles/vacuum_powder_init.lua` | The path to the Lua script file. |
| `execute_every_n_frame` | `2` | The script executes every 2 frames. |
| `remove_after_executed` | `1` | The script is removed after its first execution. |