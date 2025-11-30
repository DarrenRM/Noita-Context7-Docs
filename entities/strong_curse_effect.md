---
title: Strong Curse Effect
category: entities
---

# Strong Curse Effect

This entity defines the behavior and visual representation of a "strong curse" effect in Noita. It's primarily used to apply a damaging debuff over time.

## Core Components

### LuaComponent (Primary Effect)

This component links the entity to a Lua script that handles the curse's main logic, such as damage application.

*   **`script_source_file`**: `data/scripts/projectiles/curse.lua` - The script responsible for the curse's active effects.
*   **`execute_every_n_frame`**: `30` - The script logic will run every 30 frames.

### VariableStorageComponent (Damage Value)

This component stores a numerical value associated with the curse, likely representing its damage potency.

*   **`_tags`**: `effect_curse_damage` - A tag to identify this specific variable.
*   **`value_float`**: `0.32` - The numerical value, likely representing damage per tick or a multiplier.

### LuaComponent (End Effect)

This component links to a script that executes when the curse effect is removed or expires.

*   **`script_source_file`**: `data/scripts/projectiles/curse_end.lua` - The script for handling the curse's termination.
*   **`execute_every_n_frame`**: `-1` - This script does not execute on a frame interval.
*   **`execute_on_removed`**: `1` - The script will execute when the entity is removed.

### LifetimeComponent

This component defines how long the curse effect will persist.

*   **`_tags`**: `effect_curse_lifetime` - A tag to identify this specific component.
*   **`lifetime`**: `300` - The curse will last for 300 frames.

### SpriteParticleEmitterComponent (Visuals)

This component generates visual particles to represent the curse effect.

*   **`sprite_file`**: `data/particles/creepy.xml` - Uses particles defined in `creepy.xml`.
*   **`delay`**: `0` - Particles start emitting immediately.
*   **`lifetime`**: `0` - Particles have no inherent lifetime set by the emitter (likely managed by the particle definition itself).
*   **`render_back`**: `1` - Particles are rendered behind other elements.
*   **`color.r`, `color.g`, `color.b`, `color.a`**: `1, 1, 1, 0.4` - Initial color is white with 40% opacity.
*   **`color_change.a`**: `-1` - The alpha (opacity) of the particles decreases over time.
*   **`emission_interval_min_frames`, `emission_interval_max_frames`**: `30` - Emits one particle every 30 frames.
*   **`count_min`, `count_max`**: `1` - Emits a single particle per emission interval.
*   **`randomize_rotation.min`, `randomize_rotation.max`**: `-3.1415` to `3.1415` - Particles have random initial rotations.
*   **`randomize_angular_velocity.min`, `randomize_angular_velocity.max`**: `-8.3415` to `8.3415` - Particles have random initial rotational speeds.
*   **`randomize_position.min_x`, `randomize_position.max_x`, `randomize_position.min_y`, `randomize_position.max_y`**: `-2` to `2` - Particles are emitted within a small radius around the entity.
*   **`randomize_velocity.min_x`, `randomize_velocity.max_x`, `randomize_velocity.min_y`, `randomize_velocity.max_y`**: `-8` to `8` - Particles have random initial velocities.