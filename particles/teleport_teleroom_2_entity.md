---
title: Teleport Teleroom 2 Entity
category: data/entities
---

# Teleport Teleroom 2 Entity

This entity defines a teleportation pad that functions as a teleroom. It is activated by liquid and triggers a teleportation event to a specific target location.

## Key Components

### TeleportComponent
This component handles the core teleportation logic.

*   **`_tags`**: `enabled_by_liquid` - The teleport is activated when submerged in liquid.
*   **`target.x`**: `-17920` - The X-coordinate of the teleportation destination.
*   **`target.y`**: `-7408` - The Y-coordinate of the teleportation destination.

### HitboxComponent
Defines the physical boundaries of the teleport pad.

*   **`_tags`**: `enabled_by_liquid` - The hitbox is active when submerged in liquid.
*   **`aabb_min_x`**: `-15` - Minimum X-axis boundary.
*   **`aabb_min_y`**: `-15` - Minimum Y-axis boundary.
*   **`aabb_max_x`**: `15` - Maximum X-axis boundary.
*   **`aabb_max_y`**: `15` - Maximum Y-axis boundary.

### LightComponent
Adds visual lighting effects to the teleport pad. There are two instances, likely for different visual layers or intensities.

*   **`_tags`**: `enabled_by_liquid` - Lighting is active when submerged in liquid.
*   **`_enabled`**: `1` - The component is enabled by default.
*   **`radius`**: `255` (first instance), `64` (second instance) - The radius of the light effect.
*   **`fade_out_time`**: `1.5` - The time it takes for the light to fade out.
*   **`r`, `g`, `b`**: `64`, `100`, `255` - The RGB color values of the light (a shade of blue).
*   **`offset_y`**: `-16` - Vertical offset for the light source.

### SpriteParticleEmitterComponent
Responsible for emitting swirling sprite particles around the teleport pad.

*   **`_tags`**: `enabled_by_liquid` - Particle emission is active when submerged in liquid.
*   **`sprite_file`**: `data/particles/redwhirl_$[1-8].png` - The sprite sheet used for the particles.
*   **`lifetime`**: `1.5` - Duration of each particle.
*   **`color.r`, `color.g`, `color.b`, `color.a`**: `1`, `1`, `1`, `0.75` - Initial color and alpha of particles.
*   **`color_change.a`**: `-0.8` - Alpha decreases over the particle's lifetime.
*   **`angular_velocity`**: `7.5` - Speed of particle rotation.
*   **`scale_velocity.x`, `scale_velocity.y`**: `1.0075` - Particles slightly grow over time.
*   **`emission_interval_min_frames`, `emission_interval_max_frames`**: `2`, `4` - Controls the rate of particle emission.
*   **`count_min`, `count_max`**: `1`, `1` - Number of particles emitted per interval.
*   **`randomize_position`, `randomize_velocity`, `randomize_lifetime`, `randomize_angular_velocity`, `randomize_rotation`**: Various parameters to add variation to emitted particles.

### ParticleEmitterComponent (x2)
These components emit "spark\_red" particles, contributing to the visual effect of the teleport.

*   **`_tags`**: `enabled_by_liquid` - Particle emission is active when submerged in liquid.
*   **`emitted_material_name`**: `spark_red` - The type of material to emit.
*   **`gravity.y`**: `0.0` - Particles are not affected by gravity.
*   **`lifetime_min`, `lifetime_max`**: `3`, `4` - Duration of emitted particles.
*   **`count_min`, `count_max`**: `75`, `115` (first instance), `1`, `1` (second instance) - Controls the number of particles emitted.
*   **`area_circle_radius.min`, `area_circle_radius.max`**: `15`, `15` (first instance), `0`, `15` (second instance) - Defines the emission area.
*   **`cosmetic_force_create`**: `1` - Particles are purely cosmetic.
*   **`collide_with_grid`**: `0` - Particles do not collide with the game grid.
*   **`airflow_force`, `airflow_time`, `airflow_scale`**: Parameters related to airflow influence on particles.
*   **`emission_interval_min_frames`, `emission_interval_max_frames`**: `12`, `12` - Controls the rate of particle emission.
*   **`emit_cosmetic_particles`**: `1` - Ensures particles are cosmetic.
*   **`velocity_always_away_from_center`**: `11` (first instance), `0` (second instance) - Controls particle velocity direction.
*   **`render_back`**: `1` - Particles are rendered behind other elements.
*   **`is_emitting`**: `1` - The emitter is active.

### LuaComponent
This component links the entity to a Lua script for custom behavior.

*   **`script_source_file`**: `data/scripts/buildings/teleroom.lua` - The path to the associated Lua script.
*   **`execute_every_n_frame`**: `50` - The script will execute every 50 frames.

### AudioLoopComponent (x2)
These components handle looping audio effects associated with the teleportation.

*   **`_tags`**: `enabled_by_liquid` - Audio is active when submerged in liquid.
*   **`file`**: `data/audio/Desktop/misc.bank` - The audio bank containing the sound events.
*   **`event_name`**: `misc/teleport_end_loop` (first instance), `misc/teleport_end_emitter_loop` (second instance) - The specific audio event to play.
*   **`auto_play_if_enabled`**: `1` - The audio will automatically play if the component is enabled.
*   **`play_on_component_enable`**: `1` - The audio will play when the component is enabled.