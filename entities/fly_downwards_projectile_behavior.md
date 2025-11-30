---
title: Fly Downwards Projectile Behavior
category: entities
---

---

# Fly Downwards Projectile Behavior

This entity defines a projectile that will fly downwards. It's primarily controlled by a Lua script.

## Key Components

### LuaComponent

This component attaches a Lua script to the entity, dictating its behavior.

*   **`script_source_file`**: `data/scripts/projectiles/fly_downwards.lua`
    *   This specifies the Lua script that controls the projectile's movement and actions.
*   **`execute_every_n_frame`**: `20`
    *   The script will be executed every 20 frames. This controls the frequency of the projectile's downward movement updates.
*   **`remove_after_executed`**: `1`
    *   The projectile will be removed from the game world after the script has been executed once. This implies the projectile has a single, defined downward trajectory and then disappears.