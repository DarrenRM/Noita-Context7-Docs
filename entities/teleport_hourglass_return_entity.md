---
title: Teleport Hourglass Return Entity
category: entities
---

# Teleport Hourglass Return Entity

This entity defines the behavior and appearance of the "return" teleportation point, often associated with the hourglass mechanic. It handles teleportation logic, visual effects, and sound.

## Key Components

### TeleportComponent
This component dictates the teleportation destination.

*   `target_x_is_absolute_position`: Set to `1` (true), meaning `target.x` is an absolute world coordinate.
*   `target_y_is_absolute_position`: Set to `1` (true), meaning `target.y` is an absolute world coordinate.
*   `target.x`: The absolute X-coordinate of the teleportation destination.
*   `target.y`: The absolute Y-coordinate of the teleportation destination.

### HitboxComponent
Defines the physical boundaries of the entity.

*   `aabb_min_x`, `aabb_min_y`: Minimum X and Y coordinates of the bounding box.
*   `aabb_max_x`, `aabb_max_y`: Maximum X and Y coordinates of the bounding box.

### UIInfoComponent
Provides information for UI elements, such as the entity's name.

*   `name`: A localization key for the entity's name (e.g., `$teleport_back`).

### LightComponent
Adds lighting effects to the entity.

*   `_enabled`: Set to `1` (true) to enable the light.
*   `radius`: The radius of the light effect.
*   `fade_out_time`: How long it takes for the light to fade out.
*   `r`, `g`, `b`: RGB color values for the light.
*   `offset_y`: Vertical offset for the light source.

### ParticleEmitterComponent
Responsible for generating visual particle effects.

*   `emitted_material_name`: The material name of the particles to emit (e.g., `spark_purple`).
*   `lifetime_min`, `lifetime_max`: The minimum and maximum lifetime of individual particles.
*   `x_vel_min`, `x_vel_max`, `y_vel_min`, `y_vel_max`: Velocity range for emitted particles.
*   `count_min`, `count_max`: The number of particles emitted per burst.
*   `render_on_grid`: Set to `1` (true) to render particles on the game grid.
*   `fade_based_on_lifetime`: Set to `1` (true) to make particles fade as their lifetime decreases.
*   `area_circle_radius.min`, `area_circle_radius.max`: The radius of the area from which particles are emitted.
*   `cosmetic_force_create`: Set to `1` (true) to ensure particles are created even if they don't interact with the environment.
*   `collide_with_grid`: Set to `0` (false) to prevent particles from colliding with the grid.
*   `airflow_force`, `airflow_time`, `airflow_scale`: Parameters controlling airflow effects on particles.
*   `emission_interval_min_frames`, `emission_interval_max_frames`: The frame interval between particle emissions.
*   `emit_cosmetic_particles`: Set to `1` (true) to emit cosmetic particles.
*   `velocity_always_away_from_center`: Controls particle velocity direction relative to the emitter center.
*   `render_back`: Set to `1` (true) to render particles behind other elements.
*   `is_emitting`: Set to `1` (true) to start particle emission.

### SpriteComponent
Defines the visual sprite for the entity.

*   `image_file`: Path to the sprite image file.
*   `offset_x`, `offset_y`: Offset for the sprite's position.
*   `z_index`: Determines the rendering order of the sprite.
*   `additive`: Set to `1` (true) for additive blending, making the sprite brighter.

### AudioLoopComponent
Plays looping sound effects.

*   `file`: Path to the sound file.
*   `event_name`: The name of the sound event to trigger.
*   `calculate_material_lowpass`: Set to `0` (false) to disable material-based lowpass filtering.
*   `auto_play`: Set to `1` (true) to automatically play the sound when the entity is active.

### LuaComponent
Attaches a Lua script to the entity for custom logic.

*   `script_source_file`: Path to the Lua script file.
*   `execute_every_n_frame`: How often the script should execute (e.g., `1` for every frame).

### Entity (for FX)
These are instances of another entity, likely used to create multiple visual effects or instances of the teleportation effect.

*   `tags`: Assigns tags to the entity (e.g., `fx`).
*   `Base file`: Specifies a base entity file to inherit properties from.