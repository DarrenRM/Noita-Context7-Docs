---
title: Acid Cloud Projectile
category: entities
---

# Acid Cloud Projectile

This document details the configuration of the Acid Cloud projectile in Noita, focusing on its behavior and visual effects.

## Core Projectile Properties

The projectile is defined by its `ProjectileComponent` and `Base` properties.

### `ProjectileComponent`

| Attribute | Value | Description |
|---|---|---|
| `_enabled` | `1` | Enables the projectile component. |
| `lob_min`, `lob_max` | `0.8`, `1.0` | Controls the lobbing behavior (vertical arc) of the projectile. |
| `speed_min`, `speed_max` | `0`, `0` | The projectile has no initial speed, suggesting it's spawned in place. |
| `direction_random_rad` | `0.00` | No randomness in projectile direction. |
| `on_death_explode` | `0` | The projectile does not explode upon death. |
| `on_death_gfx_leave_sprite` | `0` | No graphical effects are left behind when the projectile dies. |
| `on_lifetime_out_explode` | `0` | The projectile does not explode when its lifetime ends. |
| `explosion_dont_damage_shooter` | `1` | If an explosion were to occur, it wouldn't damage the player who fired it. |
| `on_collision_die` | `0` | The projectile does not die upon collision. |
| `lifetime` | `999` | A very long lifetime, indicating it persists for a significant duration. |
| `damage` | `0` | The projectile itself deals no direct damage. |
| `damage_every_x_frames` | `25` | Damage is applied periodically, but since `damage` is 0, this has no effect. |

### `Base` Properties

| Attribute | Value | Description |
|---|---|---|
| `file` | `data/entities/base_projectile.xml` | Inherits standard projectile behaviors. |
| `gravity_y` | `0` | The projectile is not affected by gravity. |
| `air_friction` | `-0.2` | A slight negative air friction, which might counteract other forces or have a minor effect. |

## Visual Effects and Particle Emitters

The projectile's appearance and cloud-like nature are achieved through multiple `ParticleEmitterComponent` instances.

### `ParticleEmitterComponent` (Acid Material)

This emitter is responsible for the core visual of the acid cloud.

| Attribute | Value | Description |
|---|---|---|
| `emitted_material_name` | `acid` | The material that forms the cloud. |
| `offset.y` | `3` | Slightly offsets the emitter position vertically. |
| `count_min`, `count_max` | `1`, `10` | Emits between 1 and 10 particles per emission interval. |
| `emission_interval_min_frames`, `emission_interval_max_frames` | `1`, `2` | Particles are emitted frequently. |
| `image_animation_file` | `data/particles/image_emitters/cloud_bottom.png` | Uses a specific sprite for the cloud's base. |
| `create_real_particles` | `1` | Creates actual particles that interact with the game world. |

### `ParticleEmitterComponent` (Acid Gas - Cosmetic)

This emitter likely contributes to the gaseous appearance of the cloud, but as cosmetic particles.

| Attribute | Value | Description |
|---|---|---|
| `emitted_material_name` | `acid_gas` | Emits particles representing acid gas. |
| `x_pos_offset_min`, `x_pos_offset_max` | `-1`, `1` | Small horizontal spread for the gas particles. |
| `y_pos_offset_min`, `y_pos_offset_max` | `-1`, `1` | Small vertical spread for the gas particles. |
| `lifetime_min`, `lifetime_max` | `0.2`, `0.5` | Gas particles have a short lifespan. |
| `airflow_force` | `1.0` | Gas particles are influenced by airflow. |
| `render_on_grid` | `1` | Renders particles on the game grid. |
| `emission_interval_min_frames`, `emission_interval_max_frames` | `10`, `10` | Emits gas particles at a moderate rate. |
| `image_animation_file` | `data/particles/image_emitters/cloud.png` | Uses a generic cloud sprite. |
| `emit_cosmetic_particles` | `1` | These are cosmetic particles, not affecting gameplay directly. |
| `create_real_particles` | `0` | Does not create real, interactive particles. |
| `is_emitting` | `0` | This emitter is initially off. |

### `ParticleEmitterComponent` (Acid Gas - Real)

This emitter creates actual, interactive acid gas particles.

| Attribute | Value | Description |
|---|---|---|
| `emitted_material_name` | `acid_gas` | Emits interactive acid gas particles. |
| `lifetime_min`, `lifetime_max` | `0.2`, `0.5` | Short lifespan for these gas particles. |
| `airflow_force` | `1.0` | Gas particles are influenced by airflow. |
| `render_on_grid` | `1` | Renders particles on the game grid. |
| `emission_interval_min_frames`, `emission_interval_max_frames` | `1`, `10` | Emits gas particles frequently. |
| `image_animation_file` | `data/particles/image_emitters/cloud.png` | Uses a generic cloud sprite. |
| `emit_cosmetic_particles` | `0` | These are real, gameplay-affecting particles. |
| `create_real_particles` | `1` | Creates actual particles. |
| `is_emitting` | `0` | This emitter is initially off. |

### `ParticleEmitterComponent` (Green Sparks - Short Life)

This emitter creates short-lived green sparks, likely for visual flair.

| Attribute | Value | Description |
|---|---|---|
| `emitted_material_name` | `spark_green` | Emits green sparks. |
| `y_pos_offset_min`, `y_pos_offset_max` | `7`, `7` | Sparks originate from a specific vertical offset. |
| `lifetime_min`, `lifetime_max` | `0.5`, `0.8` | Sparks have a short duration. |
| `airflow_force` | `0.015` | Minor influence from airflow. |
| `emission_interval_min_frames`, `emission_interval_max_frames` | `5`, `5` | Sparks are emitted at a steady rate. |
| `image_animation_file` | `data/particles/image_emitters/cloud_outline.png` | Uses a specific sprite for the sparks. |
| `emit_cosmetic_particles` | `1` | These are cosmetic particles. |
| `create_real_particles` | `0` | Does not create real particles. |

### `ParticleEmitterComponent` (Green Sparks - Long Life)

This emitter creates longer-lasting green sparks.

| Attribute | Value | Description |
|---|---|---|
| `emitted_material_name` | `spark_green` | Emits green sparks. |
| `y_pos_offset_min`, `y_pos_offset_max` | `7`, `7` | Sparks originate from a specific vertical offset. |
| `lifetime_min`, `lifetime_max` | `2.5`, `3.8` | Sparks have a longer duration. |
| `airflow_force` | `0.15` | More significant influence from airflow. |
| `emission_interval_min_frames`, `emission_interval_max_frames` | `55`, `60` | Sparks are emitted at a much slower rate. |
| `image_animation_file` | `data/particles/image_emitters/cloud_outline.png` | Uses a specific sprite for the sparks. |
| `emit_cosmetic_particles` | `1` | These are cosmetic particles. |
| `create_real_particles` | `0` | Does not create real particles. |

## Other Components

### `LifetimeComponent`

| Attribute | Value | Description |
|---|---|---|
| `lifetime` | `400` | The projectile persists for a long duration (400 frames). |

### `AudioComponent`

| Attribute | Value | Description |
|---|---|---|
| `file` | `data/audio/Desktop/projectiles.bank` | Specifies the audio bank for projectile sounds. |
| `event_root` | `player_projectiles/cloud` | Defines the root event for cloud projectile audio. |

### `LuaComponent`

| Attribute | Value | Description |
|---|---|---|
| `script_source_file` | `data/scripts/projectiles/cloud_position.lua` | Executes a Lua script to manage the projectile's position or behavior. |
| `execute_times` | `1` | The script is executed only once. |