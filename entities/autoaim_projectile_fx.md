---
title: Autoaim Projectile FX
category: entities
---

# Autoaim Projectile FX

This entity defines the visual effects for the autoaim projectile in Noita. It primarily uses a Lua component to manage its behavior and a ParticleEmitterComponent to generate visual sparks.

## Key Components

### LuaComponent

This component links the entity to a Lua script that likely handles the logic for the autoaim projectile's behavior, such as its targeting or movement.

*   **`script_source_file`**: `data/scripts/projectiles/autoaim.lua` - Specifies the Lua script responsible for the entity's functionality.
*   **`execute_every_n_frame`**: `1` - The script will execute every frame.
*   **`remove_after_executed`**: `1` - The entity will be removed after the script has executed once.

### ParticleEmitterComponent

This component is responsible for generating visual particle effects, in this case, white sparks.

*   **`_tags`**: `autoaim_fx` - A tag associated with these effects.
*   **`_enabled`**: `0` - The emitter is initially disabled.
*   **`emitted_material_name`**: `spark_white` - The material used for the emitted particles.
*   **`gravity.y`**: `50` - The vertical gravity applied to the particles.
*   **`x_vel_min`, `x_vel_max`**: `-8` to `8` - The minimum and maximum horizontal velocity of the particles.
*   **`y_vel_min`, `y_vel_max`**: `-8` to `8` - The minimum and maximum vertical velocity of the particles.
*   **`count_min`, `count_max`**: `10` to `15` - The number of particles emitted per emission.
*   **`lifetime_min`, `lifetime_max`**: `0.2` to `0.8` - The minimum and maximum lifetime of each particle in seconds.
*   **`emitter_lifetime_frames`**: `4` - The emitter will run for 4 frames.
*   **`create_real_particles`**: `0` - Indicates that these are cosmetic particles, not physical ones.
*   **`emit_cosmetic_particles`**: `1` - Enables the emission of cosmetic particles.
*   **`emission_interval_min_frames`, `emission_interval_max_frames`**: `1` - Particles are emitted every frame.
*   **`is_emitting`**: `1` - The particle emitter is active.