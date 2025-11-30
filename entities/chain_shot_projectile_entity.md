---
title: Chain Shot Projectile Entity
category: entities
---

# Chain Shot Projectile Entity

This entity defines the behavior and initialization of the "Chain Shot" projectile in Noita. It primarily relies on Lua scripts to manage its functionality.

## Key Components

### LuaComponent (Initialization)

This component is responsible for the initial setup and behavior of the chain shot projectile when it is first created.

*   **`script_source_file`**: `data/scripts/projectiles/chain_shot_init.lua`
    *   This script handles the initial logic for the chain shot, likely including its spawning, initial velocity, and any immediate effects.
*   **`execute_on_added`**: `1`
    *   Indicates that the associated Lua script should be executed as soon as this entity is added to the game world.
*   **`execute_every_n_frame`**: `-1`
    *   This value suggests that the script is not intended to run continuously every frame but rather on specific events (like being added or removed).

### LuaComponent (Launch/Lifecycle)

This component manages the ongoing behavior and eventual removal of the chain shot projectile.

*   **`script_source_file`**: `data/scripts/projectiles/chain_shot_launch.lua`
    *   This script likely handles the projectile's movement, its ability to chain to other targets, and any effects it applies upon hitting something or expiring.
*   **`execute_every_n_frame`**: `-1`
    *   Similar to the initialization script, this indicates event-driven execution rather than continuous frame-by-frame updates.
*   **`execute_on_removed`**: `1`
    *   This ensures that the associated Lua script is executed when the chain shot projectile is removed from the game world, allowing for cleanup or final effects.