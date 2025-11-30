---
title: Snowcave Buried Eye Teleporter
category: entities
---

---

# Snowcave Buried Eye Teleporter

This entity defines a special teleporter found in the Snowcave biome, visually represented as a buried eye. It utilizes specific materials to activate and teleports the player to a fixed location.

## Key Components

### TeleportComponent
This component handles the core teleportation logic.

*   `target_x_is_absolute_position`: `1` (Indicates the target X coordinate is an absolute world position).
*   `target_y_is_absolute_position`: `1` (Indicates the target Y coordinate is an absolute world position).
*   `target.x`: `3895` (The absolute X coordinate to teleport to).
*   `target.y`: `4510` (The absolute Y coordinate to teleport to).

### HitboxComponent
Defines the collision area for the teleporter.

*   `aabb_min_x`: `-15`
*   `aabb_min_y`: `-15`
*   `aabb_max_x`: `15`
*   `aabb_max_y`: `15`

### UIInfoComponent
Provides information for UI elements, such as the name displayed to the player.

*   `name`: `$teleport_generic` (Likely a localization key for "Teleporter").

### LightComponent
Adds visual lighting effects to the teleporter.

*   `radius`: `255` (Primary light radius).
*   `fade_out_time`: `1.5`
*   `r`, `g`, `b`: `64`, `100`, `255` (Blueish light color).
*   `offset_y`: `-16` (Positions the light slightly below the center).
*   A second `LightComponent` with a smaller `radius` (`64`) provides a secondary glow.

### ParticleEmitterComponent
Responsible for generating visual particle effects.

*   `emitted_material_name`: `spark_purple` (The type of particle emitted).
*   `gravity.y`: `0.0` (Particles are not affected by gravity).
*   `lifetime_min`/`max`: `3`/`4` (Duration of particles).
*   `count_min`/`max`: `115`/`115` (Number of particles emitted in a burst).
*   `area_circle_radius.min`/`max`: `15`/`15` (Emission area).
*   `emission_interval_min_frames`/`max_frames`: `12`/`12` (Frequency of emission).
*   `velocity_always_away_from_center`: `11` (Particles are pushed outwards from the center).
*   A second `ParticleEmitterComponent` with `velocity_always_away_from_center="0"` and a smaller `area_circle_radius` (`0`/`15`) creates a different particle effect.

### SpriteComponent
Defines the visual appearance of the teleporter.

*   `image_file`: `data/buildings_gfx/teleport_center.xml` (The sprite asset used).
*   `additive`: `1` (Enables additive blending for a glowing effect).

### AudioLoopComponent
Manages sound effects for the teleporter.

*   `file`: `data/audio/Desktop/misc.bank`
*   `event_name`: `misc/teleport_loop` and `misc/teleport_emitter_loop` (Specific sound events).
*   `play_on_component_enable`: `1` (Sound plays when the component is active).

### MaterialAreaCheckerComponent
These components detect specific materials in the vicinity to activate the teleporter.

*   **First Component:**
    *   `area_aabb.min_x`/`max_x`: `-2`/`2`
    *   `area_aabb.min_y`/`max_y`: `98`/`102`
    *   `material`: `magic_liquid_teleportation`
    *   `material2`: `magic_liquid_unstable_teleportation`
    *   `look_for_failure`: `1` (Checks for the absence of the required liquid).
*   **Second Component:**
    *   `area_aabb.min_x`/`max_x`: `-1`/`1`
    *   `area_aabb.min_y`/`max_y`: `99`/`101`
    *   `material`: `magic_liquid_teleportation`
    *   `material2`: `magic_liquid_unstable_teleportation`
    *   `look_for_failure`: `0` (Checks for the presence of the required liquid).

### LuaComponent
Links to Lua scripts that handle custom logic.

*   `script_material_area_checker_failed`: `data/scripts/buildings/teleport_liquid_check.lua`
*   `script_material_area_checker_success`: `data/scripts/buildings/teleport_liquid_check.lua`
*   `script_portal_teleport_used`: `data/scripts/buildings/teleport_snowcave_buried_eye.lua` (This script likely handles the actual teleportation event).