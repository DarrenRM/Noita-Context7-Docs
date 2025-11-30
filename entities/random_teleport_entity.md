---
title: Random Teleport Entity
category: entities
---

# Random Teleport Entity

This entity defines a functional teleportation point that is activated by a script. It includes visual and audio components to indicate its presence and functionality.

## Core Components

### TeleportComponent
This component handles the teleportation logic.

*   `_enabled`: Set to `0` by default, indicating it's controlled by script.
*   `_tags`: `enabled_by_script` signifies that its activation is managed externally.
*   `target_x_is_absolute_position`: `1` means the `target.x` is an absolute world coordinate.
*   `target_y_is_absolute_position`: `1` means the `target.y` is an absolute world coordinate.
*   `target.x`: The absolute X-coordinate to teleport to (e.g., `210`).
*   `target.y`: The absolute Y-coordinate to teleport to (e.g., `-80`).

### HitboxComponent
Defines the collision area for the entity.

*   `_enabled`: Set to `0` by default, controlled by script.
*   `_tags`: `enabled_by_script` for script-based activation.
*   `aabb_min_x`, `aabb_min_y`: Minimum bounding box coordinates (e.g., `-15`, `-15`).
*   `aabb_max_x`, `aabb_max_y`: Maximum bounding box coordinates (e.g., `15`, `15`).

### LuaComponent
Links the entity to a Lua script for custom behavior.

*   `script_source_file`: Specifies the Lua script to execute (e.g., `data/scripts/streaming_integration/scripts/portal_random.lua`).
*   `remove_after_executed`: Set to `1`, meaning the Lua script will be removed after it runs.

### LifetimeComponent
Determines how long the entity persists.

*   `lifetime`: The duration in seconds before the entity is removed (e.g., `1800` for 30 minutes).

## Visual Components

### UIInfoComponent
Provides information for UI elements.

*   `name`: A localization key for the entity's name (e.g., `$streamingevent_portal_random`).

### LightComponent
Adds lighting effects to the entity.

*   **Primary Light:**
    *   `_enabled`: `1` (always on).
    *   `radius`: `255` (large radius).
    *   `fade_out_time`: `1.5` seconds.
    *   `r`, `g`, `b`: Color values (e.g., `64`, `100`, `255` for a blueish hue).
    *   `offset_y`: `-16` (vertical offset).
*   **Secondary Light:**
    *   `_enabled`: `1` (always on).
    *   `radius`: `64` (smaller radius).
    *   `fade_out_time`: `1.5` seconds.
    *   `r`, `g`, `b`: Color values (e.g., `255`, `255`, `255` for white).
    *   `offset_y`: `-16` (vertical offset).

### ParticleEmitterComponent
Generates visual particle effects.

*   **Emitter 1 (Dense Sparks):**
    *   `emitted_material_name`: `spark_white`.
    *   `gravity.y`: `0.0` (no gravity).
    *   `lifetime_min`, `lifetime_max`: `3` to `4` seconds.
    *   `x_vel_min`, `x_vel_max`, `y_vel_min`, `y_vel_max`: `0` (no initial velocity).
    *   `count_min`, `count_max`: `115` (high particle count).
    *   `render_on_grid`: `1` (renders on the game grid).
    *   `fade_based_on_lifetime`: `0` (no fading based on lifetime).
    *   `area_circle_radius.min`, `area_circle_radius.max`: `15` (emits from a circular area).
    *   `cosmetic_force_create`: `1` (forces creation of cosmetic particles).
    *   `collide_with_grid`: `0` (particles don't collide with the grid).
    *   `airflow_force`, `airflow_time`, `airflow_scale`: Controls airflow interaction.
    *   `emission_interval_min_frames`, `emission_interval_max_frames`: `12` (emission rate).
    *   `emit_cosmetic_particles`: `1`.
    *   `velocity_always_away_from_center`: `11` (particles move away from the center).
    *   `render_back`: `1`.
    *   `is_emitting`: `1`.
*   **Emitter 2 (Sparse Sparks):**
    *   `emitted_material_name`: `spark_white`.
    *   `gravity.y`: `0.0`.
    *   `lifetime_min`, `lifetime_max`: `3` to `4` seconds.
    *   `x_vel_min`, `x_vel_max`, `y_vel_min`, `y_vel_max`: `0`.
    *   `count_min`, `count_max`: `1` (low particle count).
    *   `render_on_grid`: `1`.
    *   `fade_based_on_lifetime`: `1` (fades based on lifetime).
    *   `area_circle_radius.min`, `area_circle_radius.max`: `0` to `15`.
    *   `cosmetic_force_create`: `1`.
    *   `collide_with_grid`: `0`.
    *   `airflow_force`, `airflow_time`, `airflow_scale`: Controls airflow interaction.
    *   `emission_interval_min_frames`, `emission_interval_max_frames`: `12`.
    *   `emit_cosmetic_particles`: `1`.
    *   `velocity_always_away_from_center`: `0`.
    *   `render_back`: `1`.
    *   `is_emitting`: `1`.

### SpriteComponent
Defines the visual sprite for the entity.

*   `image_file`: `data/buildings_gfx/teleport_center.xml`.
*   `offset_x`, `offset_y`: `0` (no offset).
*   `z_index`: `1` (rendering layer).
*   `additive`: `1` (uses additive blending).

## Audio Components

### AudioLoopComponent
Plays looping sound effects.

*   **Teleport Loop:**
    *   `file`: `data/audio/Desktop/misc.bank`.
    *   `event_name`: `misc/teleport_loop`.
    *   `calculate_material_lowpass`: `0`.
    *   `auto_play`: `1`.
*   **Teleport Emitter Loop:**
    *   `file`: `data/audio/Desktop/misc.bank`.
    *   `event_name`: `misc/teleport_emitter_loop`.
    *   `calculate_material_lowpass`: `0`.
    *   `auto_play`: `1`.