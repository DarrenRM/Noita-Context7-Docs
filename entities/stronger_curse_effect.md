---
title: Stronger Curse Effect
category: entities
---

# Stronger Curse Effect

This entity defines a stronger version of the curse effect in Noita. It's primarily used to apply a debuff that damages the player over time and visually represents this curse with particles.

## Key Components

### LuaComponent (Curse Logic)

This component executes the core logic for the curse effect.

*   **`script_source_file`**: `data/scripts/projectiles/curse.lua` - This script handles the ongoing damage and effects of the curse.
*   **`execute_every_n_frame`**: `30` - The curse logic is updated every 30 frames.

### VariableStorageComponent (Damage Value)

This component stores a float value representing the damage multiplier or intensity of the curse.

*   **`_tags`**: `effect_curse_damage` - Identifies this component as storing the curse damage value.
*   **`value_float`**: `0.64` - The specific value for this stronger curse, likely a multiplier for base curse damage.

### LuaComponent (Curse End Logic)

This component handles the cleanup and termination of the curse effect.

*   **`script_source_file`**: `data/scripts/projectiles/curse_end.lua` - This script is executed when the curse effect is removed.
*   **`execute_every_n_frame`**: `-1` - This indicates the script doesn't run on a frame interval.
*   **`execute_on_removed`**: `1` - The script will execute when the entity is removed.

### LifetimeComponent (Curse Duration)

This component defines how long the curse effect will persist.

*   **`_tags`**: `effect_curse_lifetime` - Identifies this component as storing the curse lifetime.
*   **`lifetime`**: `300` - The curse will last for 300 frames.

### SpriteParticleEmitterComponent (Visual Effect)

This component is responsible for generating visual particles to represent the curse.

*   **`sprite_file`**: `data/particles/creepy.xml` - Uses the "creepy" particle effect.
*   **`delay`**: `0` - Particles start emitting immediately.
*   **`lifetime`**: `0` - Particles have no specific lifetime set here, likely managed by the particle definition itself.
*   **`render_back`**: `1` - Renders particles behind other elements.
*   **`color.r`, `color.g`, `color.b`, `color.a`**: `1, 1, 1, 0.4` - Initial color is white with 40% opacity.
*   **`color_change.a`**: `-1` - The alpha (opacity) of the particles decreases over time, causing them to fade out.
*   **`emission_interval_min_frames`, `emission_interval_max_frames`**: `30` - Emits one particle every 30 frames.
*   **`count_min`, `count_max`**: `1` - Emits a single particle per emission.
*   **`randomize_rotation`, `randomize_angular_velocity`**: Applies random rotation and angular velocity to particles for a more dynamic effect.
*   **`randomize_position`**: Particles are emitted within a small radius around the entity's origin.
*   **`randomize_velocity`**: Particles are given a random initial velocity in X and Y directions.