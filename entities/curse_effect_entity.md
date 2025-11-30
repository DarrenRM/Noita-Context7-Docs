---
title: Curse Effect Entity
category: entities
---

# Curse Effect Entity

This document details the `effect_CURSE` entity, which represents the curse effect in Noita. It's primarily managed by Lua scripts and utilizes particle effects to visually represent its presence.

## Core Components

### LuaComponent (Primary Logic)

This component handles the core functionality of the curse effect.

*   **`script_source_file`**: `data/scripts/projectiles/curse.lua`
    *   This script dictates how the curse behaves, including its application and ongoing effects.
*   **`execute_every_n_frame`**: `30`
    *   The script logic associated with this component will run every 30 frames.

### LuaComponent (End Logic)

This component handles the cleanup or finalization of the curse effect.

*   **`script_source_file`**: `data/scripts/projectiles/curse_end.lua`
    *   This script is executed when the curse effect is removed or expires.
*   **`execute_every_n_frame`**: `-1`
    *   This indicates the script does not execute on a frame-by-frame basis.
*   **`execute_on_removed`**: `1`
    *   The script will execute once when the entity is removed.

### VariableStorageComponent (Damage Value)

This component stores a specific variable related to the curse's damage.

*   **`_tags`**: `effect_curse_damage`
    *   A tag used to identify this specific variable.
*   **`name`**: `effect_curse_damage`
    *   The name of the variable.
*   **`value_float`**: `0.08`
    *   The float value representing the damage contribution of the curse.

### LifetimeComponent

This component defines how long the curse effect persists.

*   **`_tags`**: `effect_curse_lifetime`
    *   A tag used to identify this lifetime component.
*   **`lifetime`**: `300`
    *   The curse effect will last for 300 frames.

### SpriteParticleEmitterComponent (Visual Effect)

This component generates visual particles to represent the curse.

*   **`sprite_file`**: `data/particles/creepy.xml`
    *   Specifies the particle definition to use for the visual effect.
*   **`delay`**: `0`
    *   Particles start emitting immediately.
*   **`lifetime`**: `0`
    *   Particles have no inherent lifetime limit from this setting.
*   **`render_back`**: `1`
    *   Particles are rendered behind other elements.
*   **`color.r`**, **`color.g`**, **`color.b`**, **`color.a`**: `1`, `1`, `1`, `0.4`
    *   Initial color of the particles (white with 40% opacity).
*   **`color_change.r`**, **`color_change.g`**, **`color_change.b`**, **`color_change.a`**: `0`, `0`, `0`, `-1`
    *   The alpha component of the particles will decrease over time, causing them to fade out.
*   **`emission_interval_min_frames`**, **`emission_interval_max_frames`**: `30`, `30`
    *   Particles are emitted every 30 frames.
*   **`count_min`**, **`count_max`**: `1`, `1`
    *   One particle is emitted per emission interval.
*   **`randomize_rotation.min`**, **`randomize_rotation.max`**: `-3.1415`, `3.1415`
    *   Particles are emitted with a random rotation between -π and π radians.
*   **`randomize_angular_velocity.min`**, **`randomize_angular_velocity.max`**: `-8.3415`, `8.3415`
    *   Particles are emitted with a random angular velocity.
*   **`randomize_position.min_x`**, **`randomize_position.max_x`**, **`randomize_position.min_y`**, **`randomize_position.max_y`**: `-2`, `2`, `-2`, `2`
    *   Particles are emitted within a 4x4 pixel area around the entity's origin.
*   **`randomize_velocity.min_x`**, **`randomize_velocity.max_x`**, **`randomize_velocity.min_y`**, **`randomize_velocity.max_y`**: `-8`, `8`, `-8`, `8`
    *   Particles are emitted with random velocities in both X and Y directions.