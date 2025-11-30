---
title: Teleport Teleroom 4
category: entities
---

# Teleport Teleroom 4

This entity defines a teleportation pad that transports the player to a specific location when activated. It's designed to be powered by "teleportium" liquid.

## Key Components

### TeleportComponent
This component handles the core teleportation logic.

*   **`target.x`**: The X-coordinate of the teleportation destination.
*   **`target.y`**: The Y-coordinate of the teleportation destination.

### HitboxComponent
Defines the physical area of the teleport pad.

*   **`aabb_min_x`**, **`aabb_min_y`**: Minimum X and Y coordinates of the bounding box.
*   **`aabb_max_x`**, **`aabb_max_y`**: Maximum X and Y coordinates of the bounding box.

### LightComponent
Adds visual lighting effects to the teleport pad.

*   **`radius`**: The radius of the light effect.
*   **`fade_out_time`**: How long it takes for the light to fade out.
*   **`r`**, **`g`**, **`b`**: RGB color values for the light.
*   **`offset_y`**: Vertical offset for the light source.

### SpriteParticleEmitterComponent
Emits swirling particles for visual flair.

*   **`sprite_file`**: The sprite sheet used for the particles.
*   **`lifetime`**: Duration of each particle.
*   **`color`**: Initial color of the particles.
*   **`color_change`**: How the color changes over the particle's lifetime.
*   **`angular_velocity`**: Speed at which particles rotate.
*   **`scale_velocity`**: How the particle's scale changes over time.
*   **`emission_interval_min_frames`**, **`emission_interval_max_frames`**: Controls the rate of particle emission.
*   **`count_min`**, **`count_max`**: Number of particles emitted per burst.
*   **`randomize_position`**: Range for randomizing particle spawn positions.
*   **`randomize_velocity`**: Range for randomizing particle velocities.
*   **`randomize_lifetime`**: Range for randomizing particle lifetimes.
*   **`randomize_angular_velocity`**: Range for randomizing particle angular velocities.
*   **`randomize_rotation`**: Range for randomizing particle rotations.

### ParticleEmitterComponent (x2)
These components emit "spark\_red" particles to enhance the visual effect.

*   **`emitted_material_name`**: The material of the particles being emitted.
*   **`lifetime_min`**, **`lifetime_max`**: Duration of emitted particles.
*   **`count_min`**, **`count_max`**: Number of particles emitted per interval.
*   **`area_circle_radius.min`**, **`area_circle_radius.max`**: Defines the emission area.
*   **`cosmetic_force_create`**: Ensures particles are created even if not colliding.
*   **`airflow_force`**, **`airflow_time`**, **`airflow_scale`**: Parameters for airflow effects on particles.
*   **`emission_interval_min_frames`**, **`emission_interval_max_frames`**: Controls particle emission rate.
*   **`velocity_always_away_from_center`**: (First instance) Makes particles move away from the center.
*   **`velocity_always_away_from_center`**: (Second instance) Set to 0, allowing for different particle behavior.

### LuaComponent
Links the entity to a Lua script for custom behavior.

*   **`script_source_file`**: Path to the Lua script that controls the entity's logic.
*   **`execute_every_n_frame`**: How often the script is executed.

### AudioLoopComponent (x2)
Plays looping audio effects associated with the teleportation.

*   **`file`**: The audio bank file.
*   **`event_name`**: The specific audio event to play.
*   **`auto_play_if_enabled`**: Whether the sound should play automatically when the component is enabled.
*   **`play_on_component_enable`**: Triggers playback when the component is enabled.