---
title: Snowcave Buried Eye Return Teleporter
category: entities
---

---

# Snowcave Buried Eye Return Teleporter

This entity defines a teleporter that returns the player to a specific location, likely within the snowcave biome. It's designed to be activated by liquids and features visual and audio effects.

## Key Components

### TeleportComponent
This is the core component responsible for the teleportation functionality.

*   **`target_x_is_absolute_position`**: `1` - Indicates that `target.x` is an absolute world coordinate.
*   **`target_y_is_absolute_position`**: `1` - Indicates that `target.y` is an absolute world coordinate.
*   **`target.x`**: `190` - The absolute X-coordinate to teleport to.
*   **`target.y`**: `3080` - The absolute Y-coordinate to teleport to.

### HitboxComponent
Defines the collision area of the teleporter.

*   **`aabb_min_x`**: `-15` - Minimum X-axis bounding box coordinate.
*   **`aabb_min_y`**: `-15` - Minimum Y-axis bounding box coordinate.
*   **`aabb_max_x`**: `15` - Maximum X-axis bounding box coordinate.
*   **`aabb_max_y`**: `15` - Maximum Y-axis bounding box coordinate.

### UIInfoComponent
Provides information for the user interface.

*   **`name`**: `$teleport_back` - The localized name displayed in the UI.

### LightComponent
Adds a light source to the teleporter. There are two instances, likely for different visual effects or layers.

*   **`radius`**: `255` (first instance), `64` (second instance) - The radius of the light.
*   **`fade_out_time`**: `1.5` - How long it takes for the light to fade out.
*   **`r`, `g`, `b`**: `64`, `100`, `255` - The RGB color of the light (a shade of blue).
*   **`offset_y`**: `-16` - Vertical offset of the light source.

### ParticleEmitterComponent
Responsible for generating visual particle effects. Two instances are present, likely for different particle behaviors.

*   **`emitted_material_name`**: `spark_purple` - The material of the particles to emit.
*   **`gravity.y`**: `0.0` - No vertical gravity applied to particles.
*   **`lifetime_min`, `lifetime_max`**: `3`, `4` - The minimum and maximum lifespan of particles in seconds.
*   **`x_vel_min`, `x_vel_max`, `y_vel_min`, `y_vel_max`**: `0` - Particles are emitted with no initial velocity.
*   **`count_min`, `count_max`**: `115` (first instance), `1` (second instance) - The number of particles emitted per burst.
*   **`area_circle_radius.min`, `area_circle_radius.max`**: `15` (first instance), `0`, `15` (second instance) - The radius of the emission area.
*   **`emission_interval_min_frames`, `emission_interval_max_frames`**: `12` - The interval between particle emissions in frames.
*   **`velocity_always_away_from_center`**: `11` (first instance), `0` (second instance) - Controls particle behavior relative to the emitter's center.

### SpriteComponent
Defines the visual appearance of the teleporter.

*   **`image_file`**: `data/buildings_gfx/teleport_center.xml` - The path to the sprite's image file.
*   **`z_index`**: `1` - Controls the rendering order.
*   **`additive`**: `1` - Enables additive blending for the sprite.

### AudioLoopComponent
Adds looping sound effects to the teleporter.

*   **`file`**: `data/audio/Desktop/misc.bank` - The audio bank file.
*   **`event_name`**: `misc/teleport_loop` and `misc/teleport_emitter_loop` - The specific audio events to play.
*   **`auto_play`**: `1` - The sound effect starts automatically.

### LuaComponent
Executes a Lua script for additional logic.

*   **`script_source_file`**: `data/scripts/buildings/teleport_snowcave_buried_eye_return.lua` - The path to the Lua script.
*   **`execute_every_n_frame`**: `71` - The script is executed every 71 frames.

## Disabled Components (Commented Out)

The commented-out sections suggest previous or alternative implementations related to powering the teleporter with specific liquids.

### MaterialAreaCheckerComponent
These components were likely used to detect the presence of `magic_liquid_teleportation` or `magic_liquid_unstable_teleportation` in a specific area around the teleporter.

### LuaComponent (for material checking)
This component would have been linked to the `MaterialAreaCheckerComponent` to handle success or failure conditions based on liquid detection.