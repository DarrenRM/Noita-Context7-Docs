---
title: Cloud Blood Projectile
category: entities
---

# Cloud Blood Projectile

This document describes the `cloud_blood.xml` entity, which defines a projectile that creates a cloud of blood particles.

## Core Entity Properties

*   **`name`**: `$projectile_default` (This is a base projectile definition, likely inherited by other projectiles).
*   **`tags`**: `projectile_player` (Indicates this projectile is fired by the player).

## Projectile Component (`ProjectileComponent`)

This component governs the projectile's behavior.

| Attribute                 | Value   | Description                                                                 |
| :------------------------ | :------ | :-------------------------------------------------------------------------- |
| `_enabled`                | `1`     | Enables the projectile component.                                           |
| `lob_min`, `lob_max`      | `0.8`, `1.0` | Controls the lobbing behavior (how much it arcs).                           |
| `speed_min`, `speed_max`  | `0`, `0` | Projectile has no initial speed, suggesting it's spawned in place.          |
| `direction_random_rad`    | `0.00`  | No random direction applied.                                                |
| `on_death_explode`        | `0`     | Does not explode upon death.                                                |
| `on_death_gfx_leave_sprite` | `0`     | Does not leave a sprite upon death.                                         |
| `on_lifetime_out_explode` | `0`     | Does not explode when its lifetime ends.                                    |
| `explosion_dont_damage_shooter` | `1`     | If it were to explode, it wouldn't damage the shooter.                      |
| `on_collision_die`        | `0`     | Does not die upon collision.                                                |
| `lifetime`                | `999`   | Very long lifetime, suggesting it's managed by other components or effects. |
| `damage`                  | `0`     | Deals no direct damage.                                                     |
| `damage_every_x_frames`   | `25`    | If damage were applied, it would be every 25 frames.                        |

## Particle Emitters

This entity utilizes multiple `ParticleEmitterComponent`s to create the visual effect of a blood cloud.

### Emitter 1: `cloud_bottom.png`

*   **`emitted_material_name`**: `blood`
*   **`offset.y`**: `3`
*   **`count_min`, `count_max`**: `1`, `10`
*   **`emission_interval_min_frames`, `emission_interval_max_frames`**: `3`, `3`
*   **`image_animation_file`**: `data/particles/image_emitters/cloud_bottom.png`
*   **`create_real_particles`**: `1` (Creates actual particles that can interact with the world).

### Emitter 2: `cloud.png` (Cosmetic)

*   **`emitted_material_name`**: `blood`
*   **`x_pos_offset_min`, `x_pos_offset_max`**: `-1`, `1`
*   **`y_pos_offset_min`, `y_pos_offset_max`**: `-1`, `1`
*   **`lifetime_min`, `lifetime_max`**: `0.2`, `0.5`
*   **`emission_interval_min_frames`, `emission_interval_max_frames`**: `10`, `10`
*   **`image_animation_file`**: `data/particles/image_emitters/cloud.png`
*   **`emit_cosmetic_particles`**: `1` (Emits particles that are purely visual).
*   **`create_real_particles`**: `0` (Does not create world-interactive particles).

### Emitter 3: `cloud.png` (Real)

*   **`emitted_material_name`**: `blood`
*   **`lifetime_min`, `lifetime_max`**: `0.2`, `0.5`
*   **`emission_interval_min_frames`, `emission_interval_max_frames`**: `1`, `10`
*   **`image_animation_file`**: `data/particles/image_emitters/cloud.png`
*   **`create_real_particles`**: `1` (Creates actual particles).

### Emitter 4: `cloud_outline.png` (Cosmetic Outline)

*   **`emitted_material_name`**: `blood`
*   **`y_pos_offset_min`, `y_pos_offset_max`**: `7`, `7`
*   **`lifetime_min`, `lifetime_max`**: `0.5`, `0.8`
*   **`airflow_force`, `airflow_scale`, `airflow_time`**: `0.015`, `0.01`, `0.1` (Applies subtle airflow to particles).
*   **`emission_interval_min_frames`, `emission_interval_max_frames`**: `5`, `5`
*   **`image_animation_file`**: `data/particles/image_emitters/cloud_outline.png`
*   **`cosmetic_force_create`**: `1` (Ensures cosmetic particles are created).

### Emitter 5: `cloud_outline.png` (Longer Lasting Outline)

*   **`emitted_material_name`**: `blood`
*   **`y_pos_offset_min`, `y_pos_offset_max`**: `7`, `7`
*   **`lifetime_min`, `lifetime_max`**: `2.5`, `3.8`
*   **`airflow_force`, `airflow_scale`, `airflow_time`**: `0.15`, `0.1`, `0.1` (Applies stronger airflow).
*   **`emission_interval_min_frames`, `emission_interval_max_frames`**: `55`, `60`
*   **`image_animation_file`**: `data/particles/image_emitters/cloud_outline.png`
*   **`cosmetic_force_create`**: `0` (Standard cosmetic particle creation).

## Lifetime Component (`LifetimeComponent`)

*   **`lifetime`**: `600` (The projectile itself persists for a long duration).

## Audio Component (`AudioComponent`)

*   **`file`**: `data/audio/Desktop/projectiles.bank`
*   **`event_root`**: `player_projectiles/cloud` (Specifies the sound event for this projectile).

## Lua Component (`LuaComponent`)

*   **`script_source_file`**: `data/scripts/projectiles/cloud_position.lua` (A script likely handles the positioning and behavior of the cloud).
*   **`execute_times`**: `1` (The script is executed once).