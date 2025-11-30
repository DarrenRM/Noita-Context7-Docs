---
title: Teleport Teleroom 5
category: data/entities
---

# Teleport Teleroom 5

This entity defines a specific type of teleportation pad, likely intended for use in a "teleroom" environment within Noita. It utilizes a combination of components to handle teleportation logic, visual effects, and sound.

## Key Components and Attributes

### TeleportComponent

This is the core component responsible for the teleportation functionality.

*   **`_tags="enabled_by_liquid"`**: This tag indicates that the component's functionality is activated or influenced by the presence of liquid.
*   **`target.x="10240"`**: The X-coordinate of the teleportation destination.
*   **`target.y="0"`**: The Y-coordinate of the teleportation destination.

### HitboxComponent

Defines the physical boundaries of the teleport pad.

*   **`_tags="enabled_by_liquid"`**: Similar to `TeleportComponent`, its behavior might be linked to liquid presence.
*   **`aabb_min_x="-15"`, `aabb_min_y="-15"`, `aabb_max_x="15"`, `aabb_max_y="15"`**: These define a square bounding box centered around the entity's origin, with a size of 30x30 units.

### LightComponent (x2)

These components create visual lighting effects around the teleport pad.

*   **`_tags="enabled_by_liquid"`**: Lighting effects are likely tied to liquid interactions.
*   **`_enabled="1"`**: The light is enabled by default.
*   **`radius`**: Controls the range of the light. The first has a large radius (255), the second a smaller one (64).
*   **`fade_out_time="1.5"`**: The duration in seconds over which the light fades out.
*   **`r="64"`, `g="100"`, `b="255"`**: Defines the color of the light as a shade of blue.
*   **`offset_y="-16"`**: Shifts the light source downwards by 16 units.

### SpriteParticleEmitterComponent

This component generates swirling particle effects around the teleport pad.

*   **`_tags="enabled_by_liquid"`**: Particle emission is linked to liquid.
*   **`sprite_file="data/particles/redwhirl_$[1-8].png"`**: Specifies the sprite files used for the particles, suggesting a set of 8 rotating whirl sprites.
*   **`lifetime="1.5"`**: The duration each particle exists.
*   **`color.a="0.75"`**: Initial transparency of the particles.
*   **`color_change.a="-0.8"`**: Particles fade out over their lifetime.
*   **`angular_velocity="7.5"`**: Controls the rotation speed of the particles.
*   **`scale_velocity.x="1.0075"`, `scale_velocity.y="1.0075"`**: Particles slightly grow over time.
*   **`emission_interval_min_frames="2"`, `emission_interval_max_frames="4"`**: Controls the rate at which particles are emitted.
*   **`randomize_position`, `randomize_velocity`, `randomize_lifetime`, `randomize_angular_velocity`, `randomize_rotation`**: These attributes introduce variation in particle behavior, making the effect less uniform.

### ParticleEmitterComponent (x2)

These components emit "spark\_red" particles, contributing to the visual flair of the teleport pad.

*   **`_tags="enabled_by_liquid"`**: Particle emission is linked to liquid.
*   **`emitted_material_name="spark_red"`**: The type of particle material to emit.
*   **`gravity.y="0.0"`**: Particles are not affected by gravity.
*   **`lifetime_min="3"`, `lifetime_max="4"`**: The duration particles exist.
*   **`count_min`, `count_max`**: The number of particles emitted per interval. The first has a higher count (75-115), the second a single particle (1).
*   **`area_circle_radius.min`, `area_circle_radius.max`**: Defines the area from which particles are emitted.
*   **`cosmetic_force_create="1"`**: Ensures particles are created even if they don't interact with physics.
*   **`airflow_force`, `airflow_time`, `airflow_scale`**: These suggest some form of subtle air current influence on the particles.
*   **`emission_interval_min_frames="12"`, `emission_interval_max_frames="12"`**: Particles are emitted at a consistent rate.
*   **`velocity_always_away_from_center="11"`**: In the first emitter, particles are pushed outwards from the center. This is set to "0" in the second, suggesting a different emission pattern.

### LuaComponent

This component integrates custom Lua scripting for the teleportation logic.

*   **`script_source_file="data/scripts/buildings/teleroom.lua"`**: Specifies the path to the Lua script that governs the entity's behavior.
*   **`execute_every_n_frame="50"`**: The script will be executed every 50 frames.

### AudioLoopComponent (x2)

These components handle looping sound effects associated with the teleportation process.

*   **`_tags="enabled_by_liquid"`**: Sound playback is linked to liquid.
*   **`file="data/audio/Desktop/misc.bank"`**: The audio bank containing the sound events.
*   **`event_name`**: Specifies the particular sound event to play. The two components use `"misc/teleport_end_loop"` and `"misc/teleport_end_emitter_loop"`.
*   **`auto_play="0"`**: The sound does not play automatically on entity spawn.
*   **`auto_play_if_enabled="1"`**: The sound will play if the component is enabled.
*   **`play_on_component_enable="1"`**: The sound will play when this component is enabled.