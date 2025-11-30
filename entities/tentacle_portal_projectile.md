---
title: Tentacle Portal Projectile
category: entities
---

# Tentacle Portal Projectile

This document details the `tentacle_portal.xml` entity, which defines a player projectile in Noita. This projectile functions as a portal that teleports the player to a fixed location.

## Key Components

### TeleportComponent
This component handles the teleportation logic.

*   `_enabled`: Controls whether the teleportation is active (set to `0` in this configuration, suggesting it might be controlled by other components or scripts).
*   `target_x_is_absolute_position`: If `1`, `target.x` and `target.y` are absolute world coordinates.
*   `target.x`: The absolute X-coordinate for the teleport destination.
*   `target.y`: The absolute Y-coordinate for the teleport destination.

### HitboxComponent
Defines the collision area of the projectile.

*   `aabb_min_x`, `aabb_min_y`: Minimum X and Y coordinates for the Axis-Aligned Bounding Box (AABB).
*   `aabb_max_x`, `aabb_max_y`: Maximum X and Y coordinates for the AABB.

### UIInfoComponent
Provides information for the user interface.

*   `name`: The display name of the action associated with this projectile (e.g., "$action_tentacle_portal").

### LightComponent
Adds lighting effects to the projectile.

*   `_enabled`: Controls if the light is active.
*   `radius`: The radius of the light effect.
*   `fade_out_time`: How long it takes for the light to fade out.
*   `r`, `g`, `b`: RGB color values for the light.
*   `offset_y`: Vertical offset for the light source.

There are two `LightComponent` instances, likely for different visual effects or layering.

### SpriteParticleEmitterComponent
Responsible for generating visual particle effects.

*   `sprite_file`: The texture file for the particles.
*   `sprite_centered`: Whether the sprite is centered.
*   `delay`: Delay before particle emission starts.
*   `lifetime`: Duration of the particle effect.
*   `color.r`, `color.g`, `color.b`, `color.a`: Initial color and alpha of particles.
*   `color_change.r`, `color_change.g`, `color_change.b`, `color_change.a`: How the color and alpha change over the particle's lifetime.
*   `velocity.x`, `velocity.y`: Initial velocity of particles.
*   `gravity.x`, `gravity.y`: Gravity applied to particles.
*   `velocity_slowdown`: How quickly particles lose velocity.
*   `rotation`: Initial rotation of particles.
*   `angular_velocity`: How fast particles rotate.
*   `render_back`: Whether particles render behind other objects.
*   `use_velocity_as_rotation`: If `1`, particle rotation follows its velocity.
*   `scale.x`, `scale.y`: Initial scale of particles.
*   `scale_velocity.x`, `scale_velocity.y`: How particle scale changes over time.
*   `emission_interval_min_frames`, `emission_interval_max_frames`: Controls the timing between particle emissions.
*   `count_min`, `count_max`: The number of particles emitted per interval.
*   `randomize_position.*`: Randomizes the emission position of particles.
*   `randomize_velocity.*`: Randomizes the initial velocity of particles.
*   `randomize_lifetime.*`: Randomizes the lifetime of individual particles.
*   `randomize_angular_velocity.*`: Randomizes the angular velocity of particles.
*   `randomize_rotation.*`: Randomizes the initial rotation of particles.

### LuaComponent
Links to a Lua script for custom logic.

*   `script_source_file`: The path to the Lua script (`data/scripts/projectiles/tentacle_portal.lua`).
*   `execute_every_n_frame`: How often the Lua script is executed.

### LifetimeComponent
Determines how long the projectile exists.

*   `lifetime`: The total lifetime of the projectile in frames.

### Base Entity (`data/entities/base_projectile.xml`)
Inherits properties from the base projectile entity.

*   **VelocityComponent**:
    *   `gravity_y`: Gravity applied in the Y direction (set to `0` for no gravity).
    *   `air_friction`: Friction applied in the air (set to `0` for no air friction).
    *   `mass`: The mass of the projectile.

### AudioComponent
Handles sound effects for the projectile.

*   `file`: The audio bank file.
*   `event_root`: The root event name for projectile sounds.
*   `set_latest_event_position`: If `1`, the sound event's position is set to the projectile's position.

### AudioLoopComponent
Manages looping sound effects.

*   `file`: The audio bank file.
*   `event_name`: The name of the looping sound event.
*   `auto_play`: If `1`, the sound starts playing automatically.