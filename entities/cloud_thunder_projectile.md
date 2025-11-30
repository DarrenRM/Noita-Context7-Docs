---
title: Cloud Thunder Projectile
category: entities
---

# Cloud Thunder Projectile

This document details the configuration of the "Cloud Thunder" projectile entity in Noita, primarily focusing on its visual effects and projectile behavior.

## Core Entity Properties

*   **`name`**: `$projectile_default` (This indicates it inherits from a default projectile template).
*   **`tags`**: `projectile_player` (Identifies this as a projectile fired by the player).

## Base Projectile Configuration

This section inherits properties from `data/entities/base_projectile.xml`.

### `VelocityComponent`

*   **`air_friction`**: `-0.2` (Slight resistance to air movement).
*   **`gravity_y`**: `0` (No vertical gravity applied to the projectile itself).

## Projectile Component

This component defines the core behavior of the projectile.

### `ProjectileComponent`

*   **`_enabled`**: `1` (Component is active).
*   **`lob_min`**: `0.8`
*   **`lob_max`**: `1.0`
*   **`speed_min`**: `0`
*   **`speed_max`**: `0` (Projectile has no initial speed, likely relies on other components for movement).
*   **`direction_random_rad`**: `0.00` (No random deviation in direction).
*   **`on_death_explode`**: `0` (Does not explode upon death).
*   **`on_death_gfx_leave_sprite`**: `0` (Does not leave a sprite upon death).
*   **`on_lifetime_out_explode`**: `0` (Does not explode when lifetime ends).
*   **`explosion_dont_damage_shooter`**: `1` (If it were to explode, it wouldn't damage the shooter).
*   **`on_collision_die`**: `0` (Does not die upon collision).
*   **`lifetime`**: `999` (Very long lifetime, suggesting it's managed by other means).
*   **`damage`**: `0` (Deals no direct damage).
*   **`damage_every_x_frames`**: `20` (If damage were applied, it would be every 20 frames).

## Visual Effects and Particle Emitters

This nested `Entity` block contains multiple `ParticleEmitterComponent` instances responsible for the visual appearance of the "Cloud Thunder" projectile.

### `ParticleEmitterComponent` (Water Droplets)

*   **`emitted_material_name`**: `water` (Emits water particles).
*   **`offset.y`**: `3` (Slight vertical offset for emission).
*   **`emission_interval_min_frames`**: `4`
*   **`emission_interval_max_frames`**: `7` (Emits particles at a relatively frequent interval).
*   **`image_animation_file`**: `data/particles/image_emitters/cloud_bottom.png` (Uses a specific sprite for the particle animation).
*   **`create_real_particles`**: `1` (Creates actual, physical particles).

### `ParticleEmitterComponent` (Smoke - Cosmetic)

*   **`emitted_material_name`**: `smoke` (Emits smoke particles).
*   **`x_pos_offset_min`**: `-1`
*   **`x_pos_offset_max`**: `1`
*   **`y_pos_offset_min`**: `-1`
*   **`y_pos_offset_max`**: `1` (Slight random offset for smoke emission).
*   **`gravity.y`**: `0.0` (No gravity for these smoke particles).
*   **`lifetime_min`**: `0.2`
*   **`lifetime_max`**: `0.5` (Short lifespan for smoke particles).
*   **`emission_interval_min_frames`**: `10`
*   **`emission_interval_max_frames`**: `10`
*   **`image_animation_file`**: `data/particles/image_emitters/cloud.png`
*   **`emit_cosmetic_particles`**: `1` (These are purely visual effects).
*   **`create_real_particles`**: `0` (Does not create physical particles).

### `ParticleEmitterComponent` (Smoke - Real)

*   **`emitted_material_name`**: `smoke` (Emits smoke particles).
*   **`gravity.y`**: `0.0`
*   **`lifetime_min`**: `0.2`
*   **`lifetime_max`**: `0.5`
*   **`emission_interval_min_frames`**: `1`
*   **`emission_interval_max_frames`**: `10` (More dynamic emission for real smoke particles).
*   **`image_animation_file`**: `data/particles/image_emitters/cloud.png`
*   **`create_real_particles`**: `1` (Creates physical smoke particles).

### `ParticleEmitterComponent` (Red Sparks - Cosmetic)

*   **`emitted_material_name`**: `spark_red` (Emits red spark particles).
*   **`y_pos_offset_min`**: `7`
*   **`y_pos_offset_max`**: `7` (Emitted from a specific vertical position).
*   **`gravity.y`**: `0.0`
*   **`lifetime_min`**: `0.5`
*   **`lifetime_max`**: `0.8`
*   **`airflow_force`**: `0.015`
*   **`airflow_scale`**: `0.01`
*   **`airflow_time`**: `0.1` (Particles are affected by airflow).
*   **`cosmetic_force_create`**: `1` (Forces creation of cosmetic particles).
*   **`emission_interval_min_frames`**: `5`
*   **`emission_interval_max_frames`**: `5`
*   **`image_animation_file`**: `data/particles/image_emitters/cloud_outline.png`
*   **`emit_cosmetic_particles`**: `1`
*   **`create_real_particles`**: `0`

### `ParticleEmitterComponent` (Red Sparks - Real)

*   **`emitted_material_name`**: `spark_red` (Emits red spark particles).
*   **`y_pos_offset_min`**: `7`
*   **`y_pos_offset_max`**: `7`
*   **`gravity.y`**: `0.0`
*   **`lifetime_min`**: `2.5`
*   **`lifetime_max`**: `3.8` (Longer lifespan for these sparks).
*   **`airflow_force`**: `0.15`
*   **`airflow_scale`**: `0.1`
*   **`airflow_time`**: `0.1`
*   **`cosmetic_force_create`**: `0`
*   **`emission_interval_min_frames`**: `55`
*   **`emission_interval_max_frames`**: `60` (Infrequent emission).
*   **`image_animation_file`**: `data/particles/image_emitters/cloud_outline.png`
*   **`emit_cosmetic_particles`**: `1`
*   **`create_real_particles`**: `0`

## Lua Scripting

### `LuaComponent` (Rain Thunder Logic)

*   **`script_source_file`**: `data/scripts/projectiles/rain_thunder.lua` (Handles the core logic for the thunder effect).
*   **`execute_every_n_frame`**: `60` (Script logic runs every 60 frames).

## Lifetime Component

*   **`lifetime`**: `600` (Sets the overall duration of the projectile's existence).

## Audio Component

*   **`file`**: `data/audio/Desktop/projectiles.bank`
*   **`event_root`**: `player_projectiles/cloud` (Associates specific audio events with this projectile).

## Lua Component (Cloud Position)

*   **`script_source_file`**: `data/scripts/projectiles/cloud_position.lua` (Likely handles the positioning or initial spawning behavior of the cloud).
*   **`execute_times`**: `1` (This script runs only once upon entity creation).