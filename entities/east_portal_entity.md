---
title: East Portal Entity
category: entities
---

# East Portal Entity

This entity defines the behavior and appearance of an "East Portal" in Noita, primarily used for teleportation and visual effects.

## Core Components

### TeleportComponent
Handles the teleportation functionality.

*   `_enabled`: Controls if the component is active.
*   `_tags`: Script-driven enabling.
*   `target_x_is_absolute_position`: If `1`, `target.x` is an absolute world coordinate.
*   `target_y_is_absolute_position`: If `1`, `target.y` is an absolute world coordinate.
*   `target.x`: The X-coordinate of the teleport destination.
*   `target.y`: The Y-coordinate of the teleport destination.

### HitboxComponent
Defines the collision area of the portal.

*   `_enabled`: Controls if the component is active.
*   `_tags`: Script-driven enabling.
*   `aabb_min_x`, `aabb_min_y`: Minimum X and Y coordinates of the bounding box.
*   `aabb_max_x`, `aabb_max_y`: Maximum X and Y coordinates of the bounding box.

### LuaComponent
Links the entity to its scripting logic.

*   `script_source_file`: Path to the Lua script that controls the portal's behavior (`data/scripts/streaming_integration/scripts/portal_east.lua`).
*   `remove_after_executed`: If `1`, the Lua script is removed after execution.

### LifetimeComponent
Determines how long the portal persists.

*   `lifetime`: The duration in seconds before the entity is destroyed (set to 1800 seconds, or 30 minutes).

## Visual Components

### UIInfoComponent
Provides information for UI elements, such as tooltips.

*   `name`: The display name for the UI, localized by `$streamingevent_portal_east`.

### LightComponent
Adds light sources to the portal for visual effect.

*   **Primary Light:**
    *   `_enabled`: `1` (active).
    *   `radius`: `255` (large radius).
    *   `fade_out_time`: `1.5` seconds.
    *   `r`, `g`, `b`: Color values (64, 100, 255 - a bluish hue).
    *   `offset_y`: `-16` (slight vertical offset).
*   **Secondary Light:**
    *   `_enabled`: `1` (active).
    *   `radius`: `64` (smaller radius).
    *   `fade_out_time`: `1.5` seconds.
    *   `r`, `g`, `b`: Color values (255, 30, 30 - a reddish hue).
    *   `offset_y`: `-16` (slight vertical offset).

### ParticleEmitterComponent
Generates visual particle effects.

*   **Emitter 1 (Dense Sparks):**
    *   `emitted_material_name`: `spark_red`.
    *   `lifetime_min`, `lifetime_max`: `3` to `4` seconds.
    *   `count_min`, `count_max`: `115` particles per emission.
    *   `area_circle_radius.min`, `area_circle_radius.max`: `15` (emits from a circular area).
    *   `emission_interval_min_frames`, `emission_interval_max_frames`: `12` frames.
    *   `velocity_always_away_from_center`: `11` (particles are pushed outwards).
*   **Emitter 2 (Fewer Sparks):**
    *   `emitted_material_name`: `spark_red`.
    *   `lifetime_min`, `lifetime_max`: `3` to `4` seconds.
    *   `count_min`, `count_max`: `1` particle per emission.
    *   `area_circle_radius.min`, `area_circle_radius.max`: `0` to `15` (emits from a circular area).
    *   `emission_interval_min_frames`, `emission_interval_max_frames`: `12` frames.
    *   `fade_based_on_lifetime`: `1` (particles fade out over time).
    *   `velocity_always_away_from_center`: `0` (less directional force).

### SpriteComponent
Defines the visual sprite for the portal.

*   `image_file`: `data/buildings_gfx/teleport_center.xml` (uses a pre-defined teleport graphic).
*   `z_index`: `1` (layering).
*   `additive`: `1` (uses additive blending for a glowing effect).

## Audio Components

### AudioLoopComponent
Plays looping sound effects.

*   **Teleport Loop:**
    *   `file`: `data/audio/Desktop/misc.bank`.
    *   `event_name`: `misc/teleport_loop`.
    *   `auto_play`: `1` (starts automatically).
*   **Teleport Emitter Loop:**
    *   `file`: `data/audio/Desktop/misc.bank`.
    *   `event_name`: `misc/teleport_emitter_loop`.
    *   `auto_play`: `1` (starts automatically).