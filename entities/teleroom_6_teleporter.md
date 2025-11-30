---
title: Teleroom 6 Teleporter
category: entities
---

# Teleroom 6 Teleporter

This entity defines a teleporter that activates when submerged in liquid. It targets a specific coordinate for teleportation and features visual and auditory effects.

## Key Components

### `TeleportComponent`

This component handles the core teleportation logic.

*   **`_tags`**: `enabled_by_liquid` - The teleporter activates when in contact with liquid.
*   **`target.x`**: `7480` - The X-coordinate of the teleportation destination.
*   **`target.y`**: `-12288` - The Y-coordinate of the teleportation destination.

### `HitboxComponent`

Defines the physical boundaries of the teleporter.

*   **`_tags`**: `enabled_by_liquid` - The hitbox is active when in contact with liquid.
*   **`aabb_min_x`**: `-15` - Minimum X-axis bounding box coordinate.
*   **`aabb_min_y`**: `-15` - Minimum Y-axis bounding box coordinate.
*   **`aabb_max_x`**: `15` - Maximum X-axis bounding box coordinate.
*   **`aabb_max_y`**: `15` - Maximum Y-axis bounding box coordinate.

### `LightComponent`

Adds a visual glow effect to the teleporter. There are two instances, likely for different visual layers or intensities.

*   **`_tags`**: `enabled_by_liquid` - The light is active when in contact with liquid.
*   **`_enabled`**: `1` - The light is enabled by default.
*   **`radius`**: `255` (first instance), `64` (second instance) - The radius of the light effect.
*   **`fade_out_time`**: `1.5` - The time it takes for the light to fade out.
*   **`r`, `g`, `b`**: `64`, `100`, `255` - The RGB color values of the light (a shade of blue).
*   **`offset_y`**: `-16` - Vertical offset for the light source.

### `SpriteParticleEmitterComponent`

Emits swirling sprite particles for visual flair.

*   **`_tags`**: `enabled_by_liquid` - Particles are emitted when in contact with liquid.
*   **`sprite_file`**: `data/particles/redwhirl_$[1-8].png` - Specifies the sprite sheet for the particles.
*   **`lifetime`**: `1.5` - Duration each particle exists.
*   **`color`**: `r="1" g="1" b="1" a="0.75"` - Initial color and alpha of particles.
*   **`color_change`**: `a="-0.8"` - Alpha decreases over the particle's lifetime.
*   **`angular_velocity`**: `7.5` - Speed of particle rotation.
*   **`scale_velocity`**: `1.0075` - How the particle scale changes over time.
*   **`emission_interval_min_frames`, `emission_interval_max_frames`**: `2`, `4` - Controls the rate of particle emission.
*   **`count_min`, `count_max`**: `1`, `1` - Number of particles emitted per interval.
*   **`randomize_position`, `randomize_velocity`, `randomize_lifetime`, `randomize_angular_velocity`, `randomize_rotation`**: Various ranges for adding variation to emitted particles.

### `ParticleEmitterComponent` (Two instances)

These components emit "spark\_red" material particles.

*   **`_tags`**: `enabled_by_liquid` - Particles are emitted when in contact with liquid.
*   **`emitted_material_name`**: `spark_red` - The material of the particles being emitted.
*   **`gravity.y`**: `0.0` - No vertical gravity applied to particles.
*   **`lifetime_min`, `lifetime_max`**: `3`, `4` - Duration particles exist.
*   **`count_min`, `count_max`**: `75`, `115` (first instance), `1`, `1` (second instance) - Controls the number of particles emitted.
*   **`area_circle_radius.min`, `area_circle_radius.max`**: `15`, `15` (first instance), `0`, `15` (second instance) - Defines the emission area.
*   **`airflow_force`, `airflow_time`, `airflow_scale`**: `0.051`, `1.01`, `0.03` - Parameters related to airflow influencing particles.
*   **`emission_interval_min_frames`, `emission_interval_max_frames`**: `12`, `12` - Controls the rate of particle emission.
*   **`velocity_always_away_from_center`**: `11` (first instance), `0` (second instance) - Influences particle velocity direction.

### `LuaComponent`

Links the entity to a Lua script for custom behavior.

*   **`script_source_file`**: `data/scripts/buildings/teleroom.lua` - The path to the script file.
*   **`execute_every_n_frame`**: `50` - The script will execute every 50 frames.

### `AudioLoopComponent` (Two instances)

Plays looping audio effects related to teleportation.

*   **`_tags`**: `enabled_by_liquid` - Audio plays when in contact with liquid.
*   **`file`**: `data/audio/Desktop/misc.bank` - The audio bank containing the sound events.
*   **`event_name`**: `misc/teleport_end_loop`, `misc/teleport_end_emitter_loop` - The specific audio events to play.
*   **`auto_play_if_enabled`**: `1` - The audio will automatically play if the component is enabled.
*   **`play_on_component_enable`**: `1` - The audio will play when the component is enabled.