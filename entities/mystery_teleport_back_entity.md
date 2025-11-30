---
title: Mystery Teleport Back Entity
category: entities
---

---

# Mystery Teleport Back Entity

This entity represents a teleportation pad that sends the player to a specific, fixed location. It's primarily used for returning to a designated area.

## Key Components

### TeleportComponent
This component defines the teleportation behavior.

*   **`target_x_is_absolute_position`**: `1` (True) - The `target.x` value is an absolute world coordinate.
*   **`target_y_is_absolute_position`**: `1` (True) - The `target.y` value is an absolute world coordinate.
*   **`target.x`**: `764` - The absolute X-coordinate to teleport to.
*   **`target.y`**: `-814` - The absolute Y-coordinate to teleport to.

### HitboxComponent
Defines the collision area of the entity.

*   **`aabb_min_x`**: `-15`
*   **`aabb_min_y`**: `-15`
*   **`aabb_max_x`**: `15`
*   **`aabb_max_y`**: `15`

### UIInfoComponent
Provides information for the game's UI.

*   **`name`**: `$teleport_mystery_back` - The internal name, likely used for localization.

### LightComponent (x2)
These components add visual lighting effects to the entity.

*   **`radius`**: `255` (first component), `64` (second component) - The range of the light.
*   **`fade_out_time`**: `1.5` - How long the light takes to fade.
*   **`r`, `g`, `b`**: `64`, `100`, `255` - Defines the blueish color of the light.
*   **`offset_y`**: `-16` - Positions the light slightly below the entity's center.

### SpriteParticleEmitterComponent
Manages the visual particle effects surrounding the teleport pad.

*   **`sprite_file`**: `data/particles/redwhirl_$[1-8].png` - Uses a sequence of sprites for a swirling effect.
*   **`lifetime`**: `1.5` - Duration of each particle.
*   **`color.a`**: `0.75` - Initial transparency of particles.
*   **`color_change.a`**: `-0.8` - Particles fade out quickly.
*   **`angular_velocity`**: `7.5` - Particles rotate.
*   **`scale_velocity.x`, `scale_velocity.y`**: `1.0075` - Particles grow slightly over time.
*   **`emission_interval_min_frames`, `emission_interval_max_frames`**: `2`, `4` - Controls the rate of particle emission.
*   **`count_min`, `count_max`**: `1`, `1` - Emits one particle at a time.
*   **`randomize_position`, `randomize_velocity`, `randomize_lifetime`, `randomize_angular_velocity`, `randomize_rotation`**: Various settings to give particles a dynamic and varied appearance.

### AudioLoopComponent (x2)
These components play looping sound effects associated with the teleportation.

*   **`file`**: `data/audio/Desktop/misc.bank` - The audio bank containing the sounds.
*   **`event_name`**: `misc/teleport_loop` and `misc/teleport_emitter_loop` - Specific sound events to trigger.
*   **`auto_play`**: `1` (True) - The sounds start playing automatically when the entity is active.

### LuaComponent
Links the entity to a Lua script for custom logic.

*   **`script_portal_teleport_used`**: `data/scripts/buildings/mystery_teleport_back.lua` - The path to the Lua script that handles the teleportation logic when activated.
*   **`execute_every_n_frame`**: `-1` - Indicates the script is likely triggered by an event rather than a regular frame update.