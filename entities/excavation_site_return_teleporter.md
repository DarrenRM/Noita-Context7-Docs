---
title: Excavation Site Return Teleporter
category: entities
---

# Excavation Site Return Teleporter

This entity defines a teleporter that returns the player to a specific location within the excavation site. It is designed to be activated by liquids and features visual and audio effects.

## Key Components

### TeleportComponent
This component handles the teleportation logic.

*   `target_x_is_absolute_position`: `1` - Indicates that `target.x` is an absolute world coordinate.
*   `target_y_is_absolute_position`: `1` - Indicates that `target.y` is an absolute world coordinate.
*   `target.x`: `190` - The absolute X-coordinate to teleport to.
*   `target.y`: `3080` - The absolute Y-coordinate to teleport to.

### HitboxComponent
Defines the collision area of the teleporter.

*   `aabb_min_x`: `-15` - Minimum X-axis boundary of the hitbox.
*   `aabb_min_y`: `-15` - Minimum Y-axis boundary of the hitbox.
*   `aabb_max_x`: `15` - Maximum X-axis boundary of the hitbox.
*   `aabb_max_y`: `15` - Maximum Y-axis boundary of the hitbox.

### UIInfoComponent
Provides information for the user interface.

*   `name`: `$teleport_back` - The localized name displayed in the UI.

### LightComponent
Adds a light source to the teleporter.

*   `radius`: `255` (first component), `64` (second component) - The radius of the light.
*   `fade_out_time`: `1.5` - The time it takes for the light to fade out.
*   `r`, `g`, `b`: `64`, `100`, `255` - The RGB color values of the light (a shade of blue).
*   `offset_y`: `-16` - Vertical offset of the light source.

### ParticleEmitterComponent
Responsible for generating visual particle effects.

*   `emitted_material_name`: `spark_purple` - The material used for the emitted particles.
*   `gravity.y`: `0.0` - No vertical gravity applied to particles.
*   `lifetime_min`, `lifetime_max`: `3`, `4` - The minimum and maximum lifespan of particles in seconds.
*   `x_vel_min`, `x_vel_max`, `y_vel_min`, `y_vel_max`: `0`, `0`, `0`, `0` - Particles do not have initial velocity.
*   `count_min`, `count_max`: `115` (first component), `1` (second component) - The number of particles emitted per burst.
*   `render_on_grid`: `1` - Particles are rendered on the game grid.
*   `area_circle_radius.min`, `area_circle_radius.max`: `15` (first component), `0` to `15` (second component) - The radius of the area from which particles are emitted.
*   `cosmetic_force_create`: `1` - Ensures particles are created even if the emitter is not fully visible.
*   `collide_with_grid`: `0` - Particles do not collide with the grid.
*   `emission_interval_min_frames`, `emission_interval_max_frames`: `12`, `12` - Particles are emitted every 12 frames.
*   `emit_cosmetic_particles`: `1` - Emits cosmetic particles.
*   `velocity_always_away_from_center`: `11` (first component), `0` (second component) - Controls particle direction relative to the emitter center.

### SpriteComponent
Defines the visual appearance of the teleporter.

*   `image_file`: `data/buildings_gfx/teleport_center.xml` - The path to the sprite image file.
*   `z_index`: `1` - Controls the rendering order.
*   `additive`: `1` - Enables additive blending for the sprite, often used for glowing effects.

### AudioLoopComponent
Adds looping sound effects to the teleporter.

*   `file`: `data/audio/Desktop/misc.bank` - The audio bank containing the sound events.
*   `event_name`: `misc/teleport_loop` and `misc/teleport_emitter_loop` - The specific sound events to play.
*   `auto_play`: `1` - The sound starts playing automatically when the entity is active.

---
**Note:** The commented-out `MaterialAreaCheckerComponent` and `LuaComponent` suggest a previous or alternative implementation where the teleporter might have been powered by specific liquids. This functionality is currently inactive.