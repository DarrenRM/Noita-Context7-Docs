---
title: Accelerating Shot Projectile
category: entities
---

---

# Accelerating Shot Projectile

This entity defines a projectile that utilizes a Lua script to modify its behavior over time.

## Key Components

### LuaComponent

This component is responsible for the dynamic behavior of the projectile.

*   **`script_source_file`**: `data/scripts/projectiles/accelerating_shot.lua`
    *   Specifies the Lua script that controls the projectile's logic.
*   **`execute_every_n_frame`**: `1`
    *   Indicates that the script should be executed every single frame, allowing for continuous updates to the projectile's state.
*   **`remove_after_executed`**: `1`
    *   The projectile entity will be removed from the game world after the Lua script has finished its execution. This implies the script likely handles the projectile's lifespan and eventual destruction.